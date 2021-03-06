---
title: リンカ ツール エラー LNK1168
ms.date: 11/04/2016
f1_keywords:
- LNK1168
helpviewer_keywords:
- LNK1168
ms.assetid: 97ead151-fd99-46fe-9a1d-7e84dc0b8cc8
ms.openlocfilehash: d18aacd23a7ce9ed49f12a62f8358bb6d668c778
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622119"
---
# <a name="linker-tools-error-lnk1168"></a>リンカ ツール エラー LNK1168

書き込みモードで 'filename' を開けません。

リンカーは `filename` に書き込むことができません。 ファイルが使用中で、そのファイル ハンドルが別のプロセスによってロックされている可能性があります。または、ファイルに対する書き込みアクセス許可、あるいはファイルが配置されているディレクトリやネットワーク共有に対する書き込みアクセス許可がない可能性があります。 このエラーは多くの場合、一時的な原因となった — たとえば、ウイルス対策プログラムによってロックが保持されているファイルの検索インデックス作成プロセスは、または Visual Studio のビルド システムによって保持されているロックを解放するときに遅延。

この問題を解決するには、`filename` ファイル ハンドルがロックされていないこと、およびファイルに対する書き込みアクセス許可があることを確認します。 実行可能ファイルの場合は、そのファイルが実行されていないことを確認します。

Windows SysInternals ユーティリティを使用して[処理](http://technet.microsoft.com/sysinternals/bb896655.aspx)または[Process Explorer](http://technet.microsoft.com/sysinternals/bb896653)のどのプロセスがファイルのハンドルのロックを判断する`filename`します。 また、プロセス エクスプローラーを使用して、開いているファイル ハンドルのロックを解除することもできます。 これらのユーティリティの使用方法については、そのユーティリティに付属のヘルプ ファイルを参照してください。

ファイルがウイルス対策プログラムによってロックされている場合、この問題を解決するには、ウイルス対策プログラムによる自動スキャンの対象からビルド出力ディレクトリを除外します。 ウイルス対策スキャナーは、多くの場合、ファイル システムで新しいファイルを作成することにより実行され、スキャンの実行中は、このスキャナーによりファイルがロックされます。 特定のディレクトリをスキャン対象から除外する方法の詳細については、ウイルス対策プログラムのドキュメントを参照してください。

ファイルが検索インデックス作成サービスによってロックされている場合、この問題を解決するには、自動インデックス作成の対象からビルド出力ディレクトリを除外します。 詳細については、インデックス作成サービスのドキュメントを参照してください。 Windows 検索インデックス作成サービスを変更する**インデックスのオプション**、Windows で**コントロール パネルの **します。 詳細については、次を参照してください。[を向上させる Windows 検索インデックスを使用する: よく寄せられる質問](http://windows.microsoft.com/windows/improve-windows-searches-using-index-faq#1TC=windows-7)します。

ビルド処理で実行可能ファイルを上書きできない場合、そのファイルは、ファイル エクスプローラーによってロックされている可能性があります。 場合、**アプリケーション エクスペリエンス**サービスが無効で、長時間にわたって実行可能ファイルのハンドルのロックをファイル エクスプ ローラー保持可能性があります。 この問題を解決するには実行**services.msc**を開き、**プロパティ**の ダイアログ ボックス、**アプリケーション エクスペリエンス**サービス。 変更、**スタートアップの種類**から**無効**に**手動**します。
