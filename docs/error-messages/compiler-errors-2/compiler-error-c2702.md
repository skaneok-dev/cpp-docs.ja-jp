---
title: コンパイラ エラー C2702
ms.date: 11/04/2016
f1_keywords:
- C2702
helpviewer_keywords:
- C2702
ms.assetid: 6def15d4-9a8d-43e7-ae35-42d7cb57c27e
ms.openlocfilehash: 1353e16d1bfc0999a9efe7a2a3a8d80a50b41f15
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50553713"
---
# <a name="compiler-error-c2702"></a>コンパイラ エラー C2702

_ _except は終了ブロック内では表示されない場合があります。

例外ハンドラー (`__try`/`__except`) 内にネストすることはできません、`__finally`ブロックします。

次の例では、C2702 が生成されます。

```
// C2702.cpp
// processor: x86 IPF
int Counter;
int main() {
   __try {}
   __finally {
      __try {}   // C2702
      __except( Counter ) {}   // C2702
   }
}
```