---
title: コンパイラ エラー C2208
ms.date: 11/04/2016
f1_keywords:
- C2208
helpviewer_keywords:
- C2208
ms.assetid: 9ae704bc-bf70-45f1-8e47-0470f21edd4e
ms.openlocfilehash: 7970ba5d8d2b19bd6e330fad1879880fc5cbf32d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516945"
---
# <a name="compiler-error-c2208"></a>コンパイラ エラー C2208

'type': この型を使用して定義されているメンバーはありません

型名を解決する識別子が、集計の宣言では、いますが、コンパイラはメンバーを宣言できません。

次の例では、C2208 が生成されます。

```
// C2208.cpp
class C {
   C;   // C2208
   C(){}   // OK
};
```