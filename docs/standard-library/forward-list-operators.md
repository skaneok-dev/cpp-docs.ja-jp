---
title: '&lt;forward_list&gt; 演算子'
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::operator!=
- forward_list/std::operator==
- forward_list/std::operatoroperator&gt;
- forward_list/std::operatoroperator&gt=;
- forward_list/std::operatoroperator&lt;
- forward_list/std::operatoroperator&lt;=
ms.assetid: 57492e09-3836-4dbc-9ae5-78ecf506c190
helpviewer_keywords:
- std::operator!= (forward_list)
- std::operator== (forward_list)
- std::operatoroperator&gt; (forward_list)
- std::operatoroperator&gt=; (forward_list)
- std::operatoroperator&lt; (forward_list)
- std::operatoroperator&lt;= (forward_list)
ms.openlocfilehash: 4126b81f61bd37a7a12e0621c323ec832c5b2ab7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605329"
---
# <a name="ltforwardlistgt-operators"></a>&lt;forward_list&gt; 演算子

||||
|-|-|-|
|[operator!=](#op_neq)|[operator&gt;](#op_gt)|[operator&gt;=](#op_gt_eq)|
|[operator&lt;](#op_lt)|[operator&lt;=](#op_lt_eq)|[operator==](#op_eq_eq)|

## <a name="op_eq_eq"></a>  operator==

演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトと等しいかどうかを調べます。

```cpp
bool operator==(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*left*|`forward_list` 型のオブジェクト。|
|*right*|`forward_list` 型のオブジェクト。|

### <a name="remarks"></a>Remarks

このテンプレート関数は、テンプレート クラス `forward_list` の 2 つのオブジェクトを比較する `operator==` をオーバーロードします。 `distance(left.begin(), end()) == distance(right.begin(),right.end()) && equal(left. begin(),left. end(),right.begin())` が返されます。

## <a name="op_neq"></a>  operator!=

演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトと等しくないかどうかを調べます。

```cpp
bool operator!=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*left*|`forward_list` 型のオブジェクト。|
|*right*|`forward_list` 型のオブジェクト。|

### <a name="return-value"></a>戻り値

リストが等しくない場合は **true**、リストが等しい場合は **false**。

### <a name="remarks"></a>Remarks

このテンプレート関数は `!(left == right)` を返します。

## <a name="op_lt"></a>  operator&lt;

演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトより小さいかどうかを調べます。

```cpp
bool operator<(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*left*|`forward_list` 型のオブジェクト。|
|*right*|`forward_list` 型のオブジェクト。|

### <a name="return-value"></a>戻り値

演算子の左辺の list が演算子の右辺の list 未満である場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

このテンプレート関数は、テンプレート クラス `forward_list` の 2 つのオブジェクトを比較する `operator<` をオーバーロードします。 `lexicographical_compare(lhs. begin(), lhs. end(), rhs.begin(), rhs.end())` が返されます。

## <a name="op_lt_eq"></a>  演算子&lt;=

演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクト以下であるかどうかを調べます。

```cpp
bool operator<=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*left*|`forward_list` 型のオブジェクト。|
|*right*|`forward_list` 型のオブジェクト。|

### <a name="return-value"></a>戻り値

演算子の左辺の list が演算子の右辺の list 以下である場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

このテンプレート関数は `!(right < left)` を返します。

## <a name="op_gt"></a>  operator&gt;

演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクトより大きいかどうかを調べます。

```cpp
bool operator>(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*left*|`forward_list` 型のオブジェクト。|
|*right*|`forward_list` 型のオブジェクト。|

### <a name="return-value"></a>戻り値

演算子の左辺の list が演算子の右辺の list より大きい場合は **true**、それ以外の場合は **false**。

### <a name="remarks"></a>Remarks

このテンプレート関数は `right < left` を返します。

## <a name="op_gt_eq"></a>  演算子&gt;=

演算子の左辺の前方リスト オブジェクトが右辺の前方リスト オブジェクト以上であるかどうかを調べます。

```cpp
bool operator>=(
    const forward_list <Type, Allocator>& left,
    const forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>パラメーター

|パラメーター|説明|
|---------------|-----------------|
|*left*|`forward_list` 型のオブジェクト。|
|*right*|`forward_list` 型のオブジェクト。|

### <a name="return-value"></a>戻り値

**true**演算子の左側にある前方リストがより大きいまたは演算子の右側にある前方リストに等しいそれ以外の場合**false**します。

### <a name="remarks"></a>Remarks

このテンプレート関数は `!(left < right)` を返します。

## <a name="see-also"></a>関連項目

[<forward_list>](../standard-library/forward-list.md)<br/>
