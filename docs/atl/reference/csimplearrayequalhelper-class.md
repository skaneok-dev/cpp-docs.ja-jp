---
title: CSimpleArrayEqualHelper クラス
ms.date: 11/04/2016
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
ms.openlocfilehash: e677a5d12918649597db9614b965118f8d6b7da6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50656224"
---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper クラス

このクラスのヘルパーは、 [CSimpleArray](../../atl/reference/csimplearray-class.md)クラス。

## <a name="syntax"></a>構文

```
template <class T>
class CSimpleArrayEqualHelper
```

#### <a name="parameters"></a>パラメーター

*T*<br/>
派生クラスです。

## <a name="members"></a>メンバー

### <a name="public-methods"></a>パブリック メソッド

|名前|説明|
|----------|-----------------|
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(静的)2 つのテスト`CSimpleArray`object 要素が等しいかどうか。|

## <a name="remarks"></a>Remarks

この特性クラスを補足するため、`CSimpleArray`クラス。 格納されている 2 つの要素を比較するためにメソッドを提供しますが、`CSimpleArray`オブジェクト。 既定では、要素を比較するを使用して**operator=()** 配列には、独自の等値演算子の複合データ型が含まれています、このクラスをオーバーライドする必要があります。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlsimpcoll.h

##  <a name="isequal"></a>  CSimpleArrayEqualHelper::IsEqual

2 つのテスト`CSimpleArray`object 要素が等しいかどうか。

```
static bool IsEqual(
    const T& t1,
    const T& t2);
```

### <a name="parameters"></a>パラメーター

*T1*<br/>
T 型のオブジェクト

*T2*<br/>
T 型のオブジェクト

### <a name="return-value"></a>戻り値

要素が false でそれ以外の場合、等しい場合は true を返します。

## <a name="see-also"></a>関連項目

[CSimpleArray クラス](../../atl/reference/csimplearray-class.md)<br/>
[CSimpleArrayEqualHelperFalse クラス](../../atl/reference/csimplearrayequalhelperfalse-class.md)<br/>
[クラスの概要](../../atl/atl-class-overview.md)
