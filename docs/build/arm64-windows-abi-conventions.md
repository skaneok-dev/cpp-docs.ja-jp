---
title: ARM64 ABI 規則の概要
ms.date: 07/11/2018
ms.openlocfilehash: c5c928dcb77729f5b79433d3be1b552664a0d211
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599785"
---
# <a name="overview-of-arm64-abi-conventions"></a>ARM64 ABI 規則の概要

基本的な ABI の Windows のコンパイル時と、ほとんどの 64 ビット モード (ARMv8 またはそれ以降のアーキテクチャ) の ARM プロセッサで実行は、ARM の標準 AArch64 EABI に従います。 この記事には、いくつかの主な前提条件と、EABI で記載するものとからの変更が強調表示されます。 32 ビットの ABI の詳細については、次を参照してください。[概要の ARM ABI 規則](overview-of-arm-abi-conventions.md)します。 標準の ARM EABI の詳細については、次を参照してください。[アプリケーション バイナリ インターフェイス (ABI)、ARM アーキテクチャ用](http://infocenter.arm.com/help/index.jsp?topic=/com.arm.doc.subset.swdev.abi/index.html)(外部リンク)。

## <a name="definitions"></a>定義

64 ビットのサポートの導入に伴い、ARM にはいくつかの用語が定義されています。

- **AArch32** – 従来の 32 ビット命令セットを Thumb モードでの実行を含む、ARM によって定義されるアーキテクチャ (ISA)。
- **AArch64** – 新しい 64 ビット命令は、ARM によって定義されるアーキテクチャ (ISA) を設定します。
- **ARMv7** –「7 生成」の仕様 ARM ハードウェアは、のみ AArch32 のサポートが含まれます。 これは、ARM 用の Windows の最初のバージョンがサポートされている ARM ハードウェアのバージョンです。
- **ARMv8** –「1/8/2009 生成」の仕様 ARM ハードウェアは、AArch32 と AArch64 の両方のサポートが含まれています。

これらの定義だけでなく Windows で使用してこれらの用語。

- **ARM** – 32 ビット ARM アーキテクチャ (AArch32) を参照します。 これは、WoA (ARM 上の Windows) と呼ばれます。
- **ARM32** ARM と同じ – 上記; わかりやすくするためには、このドキュメントで使用します。
- **ARM64** – 64 ビット ARM アーキテクチャ (AArch64) を参照します。 WoA64 ようなものはありません。

最後に、データ型を指す場合は、ARM から次の定義が参照されます。

- **Short ベクター** – これは、SIMD で直接表現するデータ型しますつまり、8 または 16 バイトの分、1、2、4、または 8 バイトの各要素を使用できる場所のサイズ (8 または 16 バイト) に配置された要素のベクター。
- **(同種浮動小数点が集計です) HFA** – これは、2 ~ 4 同一浮動小数点メンバー (浮動小数点数または double) を持つデータ型
- **HVA の同種 Short ベクター集計**– これは、同一の Short ベクター メンバーを 2 ~ 4 でのデータ型

## <a name="base-requirements"></a>基本的な要件

ARM64 の Windows 版は、ARMv8 で実行されていること、またはそれ以降のアーキテクチャを常時を統制します。 両方の浮動小数点と NEON サポートはハードウェアであると見なされます。

ARMv8 仕様で AArch32 アプリケーションの完全にサポートできますが、Windows (つまり、WOW64 のなしのプランなど) の ARM64 バージョンで既存の ARM32 アプリケーションの実行をサポートする予定は現在はありません。 これは今後、再評価によって異なりますが、現在の作業と想定します。

ARMv8 仕様は、AArch32 と AArch64 の両方の新しい省略可能な暗号と CRC ヘルパー オペコードを説明します。 これらのサポートは、現在省略可、ただし推奨です。 このオペコードに基づいてを活用したいコードでは、存在のランタイム チェックを実行する必要があります。

## <a name="endianness"></a>エンディアン

ARM32 として、ARM64 の Windows での Windows のバージョンは、リトル エンディアン モードで実行します。 エンディアンの切り替えは、AArch64 でカーネル モードをサポートせずにできるようを適用しやすくなりますを実現が困難です。

## <a name="alignment"></a>アラインメント

ARM64 で実行されている Windows では、不整合へのアクセスを透過的に処理する CPU ハードウェアを使用できます。 AArch32 から改善、このサポートようになりましたもは (複数の単語へのアクセスを含む) のすべての整数アクセス用と浮動小数点にアクセスできます。

ただし、キャッシュされていない (デバイス) のメモリへのアクセスもする必要があります常に揃えます。 つまり、読み取り/書き込みにずれているデータ、キャッシュされていないメモリからそれを再生する必要がある時に呼び出されるコードがある場合モ ノの安全なアクセスはすべてが揃っていることを確認します。

## <a name="integer-registers"></a>整数レジスタ

AArch64 アーキテクチャには、32 の整数レジスタ、以下の集計がサポートされています。

|登録|Volatile?|ロール|
|-|-|-|
x0|Volatile|最初のパラメーター/1、登録する結果を登録します。
x1 x7|Volatile|パラメーター/スクラッチ レジスタ 2 ~ 8
x8 x15|Volatile|スクラッチ レジスタ
x16 x17|Volatile|内部プロシージャ呼び出しスクラッチ レジスタ
x18|非 volatile|プラットフォームの登録: カーネル モードでのポイントを KPCR を現在のプロセッサユーザー モードで TEB をポイントします。
x19 x28|非 volatile|スクラッチ レジスタ
x29/fp|非 volatile|フレーム ポインター
x30/lr|非 volatile|リンク レジスタ

各レジスタは、(x0 x30) を使用して完全な 64 ビット値、または (w0 w30) を使用して 32 ビット値としてアクセスできます。 32 ビット操作ゼロ拡張、その結果最大で 64 ビット。

パラメーターのレジスタの使用方法の詳細については、セクションを渡すパラメーターを参照してください。

AArch32 とは異なり、PC と SP がインデックス付きのレジスタをいてアクセス方法に制限されていますので注意してください。 X31 がないことに注意してくださいでは、(エンコーディングは、特別な目的で使用) を登録します。

(X29) フレーム ポインターの使用は、ETW とその他のサービスで使用される高速スタック ウォーク互換性のための必要があります。 以前 {x29、30 x} をポイントする必要がありますが、スタック上のペア。

## <a name="floating-pointsimd-registers"></a>浮動小数点または SIMD レジスタ

AArch64 アーキテクチャには、次に示します 32 の浮動小数点または SIMD レジスタもサポートしています。

登録|Volatile?|ロール
|-|-|-|
v0|Volatile|最初のパラメーター/1、登録する結果を登録します。
v1 v7|Volatile|パラメーター/ゼロは、2 ~ 8 を登録します。
v8 v15|非 volatile|スクラッチ レジスタ (下位の 64 ビットのみが非揮発性メモ)
v16 v31|Volatile|スクラッチ レジスタ

各レジスタは、(h0-h31) を使用して、16 ビット値として、または (b0 b31) を使用して、8 ビット値としてでは s0-s31) (32 ビット値として d0-d31) (64 ビット値 (v0 v31 または q0 q31) 経由で完全な 128 ビット値としてアクセスできます。 128 ビット未満のアクセスは、完全な 128 ビット レジスタの下位ビットのみにアクセスし、それ以外の場合に指定されていない場合は、残りのビットを変更します。 (これは、小規模なレジスタが大容量のレジスタの上に保持されて AArch32 から大幅に異なることに注意してください)。

データ レジスタに加えて、浮動小数点制御レジスタ (FPCR) には、その中のさまざまなビット フィールドで特定の要件があります。

Bits|説明|Volatile?|ロール
|-|-|-|-|
26|AHP|非揮発性|代替の半制度制御
25|DN|非揮発性|既定の NaN モード制御
24|FZ|非 volatile|Flush-to-zero モード制御
23-22|RMode|非 volatile|丸めモード制御
15,12 8|IDE/IXE など|非揮発性|例外トラップ イネーブル ビット。常に 0 であること

## <a name="system-registers"></a>システムのレジスタ

AArch32 などは、AArch64 仕様は、次の 3 つシステムによって制御された「スレッド ID」レジスタ次のように使用される割り当てを提供します。

登録|ロール
|-|-|
TPIDR_EL0|予約されています。
TPIDRRO_EL0|現在のプロセッサの CPU 数が含まれています
TPIDR_EL1|現在のプロセッサの KPCR 構造へのポインター

## <a name="floating-point-exceptions"></a>浮動小数点例外

IEEE 浮動小数点例外のサポートは、AArch64 システムでは省略可能です。 ハードウェアの浮動小数点例外がプロセッサ バリアントでは、Windows カーネルがサイレント モードで例外をキャッチし、暗黙的に FPCR レジスタに無効にします。 これはプロセッサ バリアントで正規化された動作を確保する (それ以外の場合、コードで開発されたプラットフォーム例外処理のサポートがありますそれ自体のサポートを備えたプラットフォームで実行されているときに予期しない例外を取得せず)。

## <a name="parameter-passing"></a>パラメーター渡し

非可変個引数関数では、Windows の ABI はパラメーターの引き渡し ARM で指定された規則に従います。 これらの規則は、AArch64 アーキテクチャのプロシージャ呼び出し標準から直接抜粋します。

### <a name="stage-a--initialization"></a>ステージ A: 初期化

この段階では、引数の処理を開始する前に 1 回だけ実行されます。

1. [次へ] 汎用登録番号 (NGRN) は、0 に設定されます。

1. [次へ] の SIMD と浮動小数点登録番号 (NSRN) は、0 に設定されます。

1. [次へ] のスタック引数アドレス (NSAA) は、現在のスタック ポインター値 (SP) に設定されます。

### <a name="stage-b--pre-padding-and-extension-of-arguments"></a>ステージ B – 前のパディングと引数の拡張機能

各引数の一覧で、次の一覧から最初の一致する規則が適用されます。 変更されていないルール一致、引数を使用場合、します。

1. 引数の型が、呼び出し元と呼び出し先の両方で、サイズを静的に決定できない複合型の場合は、引数がメモリにコピーされ、引数は、コピーへのポインターによって置き換えられます。 (C および C++ でこのような型はありませんが、他の言語または言語拡張機能に存在する。)

1. 引数の型が、HFA または、HVA としている場合、引数が使用される変更されていません。

1. 引数の型が複合型を 16 バイトを超える場合は、引数は、呼び出し元によって割り当てられたメモリにコピーし、引数は、コピーへのポインターによって置き換えられます。

1. 引数の型が複合型の場合、引数のサイズは、最も近い 8 バイトの倍数に切り上げられます。

### <a name="stage-c--assignment-of-arguments-to-registers-and-stack"></a>ステージ C: レジスタおよびスタックへの引数の割り当て

各引数の一覧で、次の規則は、引数が割り当てられるまでさらに適用されます。 引数がレジスタに割り当てられているときに、レジスタの未使用ビットに値が指定されません。 引数はスタックのスロットに割り当てられたときに、未使用の埋め込みバイトには値が指定されません。

1. 引数が必要な場合は、半分-を使用して場合、シングル、ダブルクリックまたはクアッド単精度浮動小数点または Short ベクター型と、NSRN が 8 未満、引数がレジスタ v [NSRN] の最下位ビットに割り当てられているし。 NSRN は 1 ずつインクリメントされます。 引数が割り当てられましたようになりました。

1. 引数が、HFA または HVA、十分な未割り当て SIMD と浮動小数点レジスタ (NSRN + メンバー ≤ 8 の数) がある場合は、引数が SIMD して浮動小数点を登録します (HFA または HVA のメンバーごとの 1 つ登録) に割り当てられます。 NSRN が使用されるレジスタの数でインクリメントされます。 引数が割り当てられましたようになりました。

1. HFA、または、HVA 引数の場合、NSRN が 8 に設定されているし、引数のサイズが 8 バイトの倍数に切り上げられます。

1. NSAA が丸められますクアッド単精度浮動小数点または Short ベクターの型引数が、HFA、HVA の場合最大 8 または引数の型の自然なアラインメントのうち、大きい方。

1. 引数が半分または単精度浮動小数点型の場合、引数のサイズは 8 バイトに設定します。 効果は、引数があるまるでにコピーされて、64 ビット レジスタの最下位ビットと残りのビットが指定されていない値が入力します。

1. 引数が、HFA の場合、HVA、半分の単一の 2 またはクアッド単精度浮動小数点または Short ベクター型、し、引数が調整された NSAA でメモリにコピーされます。 NSAA が引数のサイズだけインクリメントされます。 引数が割り当てられましたようになりました。

1. 引数が、整数型またはポインター型の場合は、引数のサイズは 8 バイトと、NGRN に等しいまたはそれよりも小さい 8 未満で、[NGRN] x 内の最下位ビットに引数をコピーです。 NGRN は 1 ずつインクリメントされます。 引数が割り当てられましたようになりました。

1. 引数がある、配置が 16 の場合、NGRN は、次の偶数値に切り上げられます。

1. 引数は x にコピーされている場合は、引数が整数型、引数のサイズは 16 におよび、NGRN 7 より小さいは、[NGRN] および [NGRN + 1] です。 x [NGRN] のみ、低いアドレス指定された倍のワードの引数のメモリ表現が格納されます。 NGRN は 2 でインクリメントされます。 引数が割り当てられましたようになりました。

1. 引数が複合型の引数のダブル ワードのサイズがマイナス NGRN、8 個を超えるしかどうか、引数が連続の汎用レジスタにコピーされます [NGRN] x で開始します。 (任意、レジスタの未使用の要素の内容が指定されていないメモリからの連続するレジスタの読み込み LDR 命令の適切なシーケンスでダブル ワード境界のアドレスからのレジスタに読み込まれた場合と同様に、引数が渡されますこの標準によって)。 NGRN が使用されるレジスタの数でインクリメントされます。 引数が割り当てられましたようになりました。

1. NGRN は 8 に設定されます。

1. 最大 NSAA が丸められます 8 または引数の型の自然なアラインメントのうち、大きい方.

1. 引数が複合型の場合、引数は、調整された NSAA でメモリにコピーされます。 NSAA が引数のサイズだけインクリメントされます。 引数が割り当てられましたようになりました。

1. 引数のサイズが 8 バイト未満の場合、引数のサイズは 8 バイトに設定します。 64 ビット レジスタの最下位ビットを残りのビットが指定されていない値が入力引数がコピーされたかのようになります。

1. 引数は、調整された NSAA でメモリにコピーされます。 NSAA が引数のサイズだけインクリメントされます。 引数が割り当てられましたようになりました。

### <a name="addendum-variadic-functions"></a>補遺: 可変個引数関数

可変個の引数を受け取る関数の処理は異なりますよりも、上記とは、次のように。

1. すべての合成は同じ; 扱われますHFAs または Hva の特別な処理がありません。

1. SIMD と浮動小数点レジスタは使用されません。

実質的にこれは、次の規則を場所スタックの最初の 64 バイトが x0 x7 に読み込まれ、残りのスタック引数は通常、虚数部のスタックへの引数を割り当てる C.12–C.15 に相当します。

## <a name="return-values"></a>戻り値

X0 では、整数値が返されます。 必要に応じて s0、d0/v0 では、浮動小数点値が返されます。

戻り値のレジスタを使用して渡すことはできません、呼び出し元のための十分なサイズとアラインメント結果を保持するメモリ ブロックを確保する必要があります。 メモリ ブロックのアドレスは非 POD 型の x8 POD 型、または x0 (または $これが渡された場合に、x0、x1) で機能する追加の引数として渡されるものと。 呼び出し先は、サブルーチン (x8 に格納されている値を保持するために、呼び出し先がポッド以外、このバッファーのアドレスを要求する必要がありますも返されません x0 で呼び出し先によってはあります) の実行中に、任意の時点の結果のメモリ ブロックを変更できます。

## <a name="stack"></a>Stack

次の ARM によって定め ABI、スタックは、特定でアライン 16 バイトを維持する必要があります。 AArch64 には、SP 相対読み込みまたは格納は、SP に 16 バイトではないときにエラーが揃えスタック配置を生成するハードウェアの機能が含まれています。 Windows は、常に有効になっているこの機能を実行します。

関数 4 k またはスタックの価値が複数の割り当てをする必要があります前の最後のページが順番に接して、コードを確認しないことができます"leap 経由で"Windows を使用して、スタックを展開するガード ページのことを確認します。 通常これは、`__chkstk`ヘルパーで、スタック割り当ての合計で 16 x8 で割った値を渡すカスタム呼び出し規約。

## <a name="red-zone"></a>赤のゾーン

現在のスタック ポインターのすぐ下の 16 バイトの領域は、分析用に予約し、動的シナリオを修正します。 これにより、2 つのレジスタに格納するを挿入する慎重に生成されたコード (sp、# 16) し、一時的にそれらを任意の目的に使用します。 Windows カーネルでは、例外または割り込みが実行された場合、ユーザーとカーネル モードでそれらの 16 バイトは上書きされないことを保証します。

## <a name="kernel-stack"></a>カーネル スタック

Windows での既定のカーネル モード スタックは、6 つのページ (24 k) です。 カーネル モードでスタック バッファーの大きなを持つ関数への特別な注意してください。 タイミングの割り込みは、ごくわずかなヘッドルームででしたし、スタック パニック バグチェックを作成します。

## <a name="stack-walking"></a>スタック ウォーク

フレーム ポインターが有効になっている Windows 内のコードがコンパイルされる ([/Oy-](../build/reference/oy-frame-pointer-omission.md)) 高速スタック ウォークを有効にします。 この結果は x29 (fp) は、{fp、lr} には、チェーン内で次のリンクを一般的に指しているスタックと戻り値のアドレスでは、前のフレームへのポインターを示すペア。 サード パーティのコードはフレーム ポインターを強化されたプロファイリングおよびトレースするためにも有効にすることをお勧めします。

## <a name="exception-unwinding"></a>例外アンワインド

アンワインド コードを使用して、例外処理中にアンワインドが支援します。 アンワインド コードへのバックアップの準備に関数のプロローグの効果を元に戻すことができるように、抽象化でプロローグおよびエピローグの操作を記述する実行可能ファイルの .xdata セクションに格納されるバイトのシーケンスは、呼び出し元のスタック フレーム。 アンワインド コードの詳細については、次を参照してください。 [ARM64 例外処理](arm64-exception-handling.md)します。

ARM EABI では、アンワインド コードを活用して例外アンワインド モデルも指定します。 ただし、表示された仕様はアンワインドがプロローグまたは関数のエピローグの途中で、PC である場合を処理する必要があります Windows では十分ではありません。

使用して動的関数テーブルを動的に生成されるコードを説明する必要があります`RtlAddFunctionTable`生成されたコードが例外処理に参加できるように、関数を関連付けられているとします。

## <a name="cycle-counter"></a>サイクル カウンター

サイクルをサポートするために必要なすべての ARMv8 Cpu レジスタのカウンターします。 これは、任意の例外のレベル (ユーザー モードを含む) で読めるように Windows を構成する 64 ビット レジスタです。 特別な PMCCNTR_EL0 経由でアクセスできるアセンブリのコードで MSR オペコードを使用して登録します。 または`_ReadStatusReg`C と C++ コードで組み込み。

サイクル カウンターをここでは、真のサイクル カウンター、されません実時間、およびため、カウント周波数はプロセッサ周波数で異なります。 サイクル カウンターの頻度を把握する必要がありますと思われる場合は、サイクル カウンターを使用していない必要があります。 使用する必要があります、ウォール クロック時間を測定する代わりに、`QueryPerformanceCounter`します。

## <a name="see-also"></a>関連項目

[Visual C++ の ARM への移行に関する一般的な問題](../build/common-visual-cpp-arm-migration-issues.md)<br/>
[ARM64 例外処理](../build/arm64-exception-handling.md)
