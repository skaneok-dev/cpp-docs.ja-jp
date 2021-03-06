---
title: /CLRHEADER
ms.date: 11/04/2016
f1_keywords:
- /CLRHEADER
helpviewer_keywords:
- -CLRHEADER dumpbin option
- /CLRHEADER dumpbin option
- CLRHEADER dumpbin option
ms.assetid: cf73424f-4541-47e2-b94e-69b95266ef2a
ms.openlocfilehash: e35cf79cdaa10c9632e1c588e2b49f45cfbef283
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51330854"
---
# <a name="clrheader"></a>/CLRHEADER

CLR に固有の情報を表示します。

## <a name="syntax"></a>構文

> /CLRHEADER*ファイル*

### <a name="arguments"></a>引数

*file*<br/>
ビルドされたイメージ ファイル[/clr](../../build/reference/clr-common-language-runtime-compilation.md)します。

## <a name="remarks"></a>Remarks

**/CLRHEADER**マネージ プログラムで使用される .NET ヘッダーに関する情報が表示されます。 出力は、ヘッダーのセクションでは、.NET のヘッダーのバイト単位での位置やサイズを示します。

のみ、 [/HEADERS](../../build/reference/headers.md) DUMPBIN オプションがで生成されたファイルで使用できる、 [/GL](../../build/reference/gl-whole-program-optimization.md)コンパイラ オプション。

ときに **/CLRHEADER**使用は/clr でコンパイルされたファイルがあります、 **clr ヘッダー:** dumpbin 出力セクション。 値**フラグ**/clr オプションが使用されたことを示します。

- 0 -/clr (イメージは、ネイティブ コードを含めることができます)。

共通言語ランタイムのイメージをビルドしたかどうかもプログラムで確認できます。  詳細については、次を参照してください。[方法: イメージがネイティブ モードまたは CLR であるか判断](../../dotnet/how-to-determine-if-an-image-is-native-or-clr.md)します。

**/Clr: 純粋な**と **/clr:safe**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。 「純粋」または「安全」にする必要があるコードを移植する必要があるC#します。

## <a name="see-also"></a>関連項目

- [DUMPBIN オプション](../../build/reference/dumpbin-options.md)
