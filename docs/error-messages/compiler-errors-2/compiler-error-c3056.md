---
title: コンパイラ エラー C3056
ms.date: 11/04/2016
f1_keywords:
- C3056
helpviewer_keywords:
- C3056
ms.assetid: 9500173d-870b-49b3-8e88-0ee93586d19a
ms.openlocfilehash: d33aa6679c6dc68b7f1a62e75aff6fadc65dc7bd
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50447412"
---
# <a name="compiler-error-c3056"></a>コンパイラ エラー C3056

'symbol': シンボルは、'threadprivate' ディレクティブと同じスコープに存在しません

[threadprivate](../../parallel/openmp/reference/threadprivate.md) 句で使用されるシンボルは `threadprivate` 句と同じスコープである必要があります。

次の例では C3056 が生成されます。

```
// C3056.cpp
// compile with: /openmp
int x, y;
void test() {
   #pragma omp threadprivate(x, y)   // C3056
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```

考えられる解決方法:

```
// C3056b.cpp
// compile with: /openmp /LD
int x, y;
#pragma omp threadprivate(x, y)
void test() {
   #pragma omp parallel copyin(x, y)
   {
      x = y;
   }
}
```