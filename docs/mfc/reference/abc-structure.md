---
title: ABC 構造体
ms.date: 11/04/2016
f1_keywords:
- ABC
helpviewer_keywords:
- ABC structure [MFC]
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
ms.openlocfilehash: f899a84ddbe5ca3ec3abd4dff135a585aa61eaa9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549566"
---
# <a name="abc-structure"></a>ABC 構造体

`ABC`構造には、TrueType フォントの文字の幅が含まれています。

## <a name="syntax"></a>構文

```
typedef struct _ABC { /* abc */
    int abcA;
    UINT abcB;
    int abcC;
} ABC;
```

#### <a name="parameters"></a>パラメーター

*abcA*<br/>
文字の A の間隔を指定します。 A の間隔は、文字のグリフを描画する前に、現在の位置に追加する距離です。

*abcB*<br/>
文字の B の間隔を指定します。 B の間隔は、文字のグリフの描画の部分の幅です。

*abcC*<br/>
C の文字の間隔を指定します。 C の間隔は、文字のグリフの右側に空白文字を提供する現在の位置に追加する距離です。

## <a name="remarks"></a>Remarks

文字の幅の合計は、A、B、および C のスペースの合計です。 A または C 領域のいずれかをスペーシングまたはオーバー ハングを示す負にすることができます。

## <a name="requirements"></a>必要条件

**ヘッダー:** wingdi.h

## <a name="see-also"></a>関連項目

[構造体、スタイル、コールバック関数とメッセージ マップ](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDC::GetCharABCWidths](../../mfc/reference/cdc-class.md#getcharabcwidths)

