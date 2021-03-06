---
title: _variant_t::SetString
ms.date: 11/04/2016
f1_keywords:
- _variant_t::SetString
helpviewer_keywords:
- SetString method [C++]
ms.assetid: 816b08e5-6830-46ca-b3d7-7689308b3be3
ms.openlocfilehash: d07e995be0ecd99974356a7516e7c4deee677637
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50628242"
---
# <a name="varianttsetstring"></a>_variant_t::SetString

**Microsoft 固有の仕様**

この `_variant_t` オブジェクトに文字列を代入します。

## <a name="syntax"></a>構文

```
void SetString(const char* pSrc);
```

#### <a name="parameters"></a>パラメーター

*pSrc*<br/>
文字列へのポインター。

## <a name="remarks"></a>Remarks

ANSI 文字列を Unicode `BSTR` 文字列に変換し、この `_variant_t` オブジェクトに割り当てます。

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[_variant_t クラス](../cpp/variant-t-class.md)