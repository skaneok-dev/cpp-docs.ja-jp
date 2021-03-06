---
title: 文字列変換マクロ
ms.date: 11/04/2016
f1_keywords:
- atlconv/ATL::DEVMODEA2W
- atlconv/ATL::TEXTMETRICA2W
- atlconv/ATL::DEVMODEOLE2T
- atlconv/ATL::TEXTMETRICOLE2T
- atlconv/ATL::DEVMODET2OLE
- atlconv/ATL::TEXTMETRICT2OLE
- atlconv/ATL::DEVMODEW2A
- atlconv/ATL::TEXTMETRICW2A
ms.assetid: 2ff7c0b6-2bde-45fe-897f-6128e18e0c27
ms.openlocfilehash: 1cad89fe065c0827169a22cc9699b677323d8594
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544522"
---
# <a name="string-conversion-macros"></a>文字列変換マクロ

これらのマクロは、文字列の変換機能を提供します。

##  <a name="atl_and_mfc_string_conversion_macros"></a>  ATL と MFC 文字列変換マクロ

ここで説明する文字列変換マクロは、ATL と MFC の両方に対して有効です。 MFC 文字列変換の詳細については、次を参照してください。 [TN059: を使用して MFC の MBCS または Unicode 変換マクロ](../../mfc/tn059-using-mfc-mbcs-unicode-conversion-macros.md)と[MFC マクロとグローバル](../../mfc/reference/mfc-macros-and-globals.md)します。

##  <a name="devmode_and_textmetric_string_conversion_macros"></a>  DEVMODE と受け取る文字列変換マクロ

これらのマクロのコピーを作成する、 [DEVMODE](/windows/desktop/api/wingdi/ns-wingdi-_devicemodea)または[受け取る](/windows/desktop/api/wingdi/ns-wingdi-tagtextmetrica)構造体であり、新しい構造内の文字列を新しい文字列型に変換します。 マクロは、新しい構造のスタックにメモリを割り当てるし、新しい構造体へのポインターを返します。

```cpp
MACRONAME( address_of_structure )
```

### <a name="remarks"></a>Remarks

例えば:

[!code-cpp[NVC_ATL_Utilities#128](../../atl/codesnippet/cpp/string-conversion-macros_1.cpp)]

および

[!code-cpp[NVC_ATL_Utilities#129](../../atl/codesnippet/cpp/string-conversion-macros_2.cpp)]

マクロ名、ソース構造体で文字列型が左側 (など**A**) 右側の送信先構造で、文字列型であり (たとえば、 **W**)。 **A** LPSTR、略**OLE** LPOLESTR、略**T** LPTSTR、略と**W** LPWSTR を意味します。

DEVMODEA2W がそのため、コピー、 `DEVMODE` LPSTR を含む構造体の文字列に、 `DEVMODE` LPWSTR 文字列、TEXTMETRICOLE2T コピーによる構造体、 `TEXTMETRIC` LPOLESTR を含む構造体の文字列に、 `TEXTMETRIC` LPTSTR の文字列による構造体であり。

2 つの文字列に変換、`DEVMODE`構造体は、デバイス名 (`dmDeviceName`) と形式名 (`dmFormName`)。 `DEVMODE`文字列変換マクロも構造体のサイズを更新 (`dmSize`)。

4 つの文字列に変換、`TEXTMETRIC`構造体は、最初の文字 (`tmFirstChar`)、最後の文字 (`tmLastChar`)、既定の文字 (`tmDefaultChar`)、および改行文字 (`tmBreakChar`)。

動作、`DEVMODE`と`TEXTMETRIC`文字列変換マクロは、存在する場合、コンパイラ ディレクティブを有効になってに依存します。 ソースの型とターゲットの型が同じである場合、変換は実行されません。 コンパイラ ディレクティブ**T**と**OLE**次のようにします。

|有効なコンパイラ ディレクティブ|T の変更後|OLE の変更後|
|----------------------------------|---------------|-----------------|
|none|**A**|**W**|
|**\_UNICODE**|**W**|**W**|
|**OLE2ANSI**|**A**|**A**|
|**\_UNICODE**と**は、OLE2ANSI**|**W**|**A**|

次の表、`DEVMODE`と`TEXTMETRIC`文字列変換マクロ。

|||
|-|-|
|DEVMODEA2W|TEXTMETRICA2W|
|DEVMODEOLE2T|TEXTMETRICOLE2T|
|DEVMODET2OLE|TEXTMETRICT2OLE|
|DEVMODEW2A|TEXTMETRICW2A|

## <a name="see-also"></a>関連項目

[[マクロ]](../../atl/reference/atl-macros.md)
