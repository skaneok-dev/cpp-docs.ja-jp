---
title: no_dual_interfaces
ms.date: 11/04/2016
f1_keywords:
- no_dual_interfaces
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
ms.openlocfilehash: d76fe3ce6bea4c3895da9d8b40d69852f912824e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50466730"
---
# <a name="nodualinterfaces"></a>no_dual_interfaces
**C++ 固有の仕様**

コンパイラがデュアル インターフェイス メソッドのラッパー関数を生成する方法を変更します。

## <a name="syntax"></a>構文

```
no_dual_interfaces
```

## <a name="remarks"></a>Remarks

通常、ラッパーは、そのインターフェイスの仮想関数テーブルからメソッドを呼び出します。 **No_dual_interfaces**、ラッパーを呼び出す代わりに`IDispatch::Invoke`メソッドを呼び出します。

**END C 固有の仕様**

## <a name="see-also"></a>関連項目

[#import の属性](../preprocessor/hash-import-attributes-cpp.md)<br/>
[#import ディレクティブ](../preprocessor/hash-import-directive-cpp.md)