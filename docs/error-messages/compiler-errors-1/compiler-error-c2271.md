---
title: コンパイラ エラー C2271
ms.date: 11/04/2016
f1_keywords:
- C2271
helpviewer_keywords:
- C2271
ms.assetid: ea47bf57-f55d-4171-8e98-95a71d62820e
ms.openlocfilehash: 68de819ca62e117036bb415a1708afc0ecd6028c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572823"
---
# <a name="compiler-error-c2271"></a>コンパイラ エラー C2271

'operator': 新規/削除の仮引数リストの修飾子を設定することはできません

演算子 (`new`または`delete`) がメモリ モデル修飾子で宣言されています。

次の例では、C2271 が生成されます。

```
// C2271.cpp
// compile with: /c
void* operator new(size_t) const {   // C2271
// try the following line instead
// void* operator new(size_t) {
   return 0;
}

struct X {
   static void* operator new(size_t) const;   // C2271
   // try the following line instead
   // void * X::operator new(size_t) const;   // static member operator new
};
```