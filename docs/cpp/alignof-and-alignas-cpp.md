---
title: alignof と alignas (C++)
ms.date: 11/04/2016
ms.assetid: 1d18aa8a-9621-4fb5-86e5-4cc86d5187f4
ms.openlocfilehash: e5d023d7969764bdd36030a508abdd94068e48b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50493653"
---
# <a name="alignof-and-alignas-c"></a>alignof と alignas (C++)

**Alignas**型指定子は変数およびユーザー定義型のカスタムの配置を指定する移植可能で、C++ の標準的な方法です。 **Alignof**演算子は、指定した型または変数の配置を取得する標準的な移植可能な方法でも同様にします。

## <a name="example"></a>例

使用することができます**alignas**クラス、スタックまたは共用体、または個々 のメンバー。 ときに複数**alignas**指定子が検出された場合、コンパイラは、最も厳密なもの、(最大値を含む 1 つ) を選択します。

```cpp
// alignas_alignof.cpp
// compile with: cl /EHsc alignas_alignof.cpp
#include <iostream>

struct alignas(16) Bar
{
    int i;       // 4 bytes
    int n;      // 4 bytes
    alignas(4) char arr[3];
    short s;          // 2 bytes
};

int main()
{
    std::cout << alignof(Bar) << std::endl; // output: 16
}
```

## <a name="see-also"></a>関連項目

[アラインメント](../cpp/alignment-cpp-declarations.md)