---
title: コンパイラ エラー C2014
ms.date: 11/04/2016
f1_keywords:
- C2014
helpviewer_keywords:
- C2014
ms.assetid: 231d8e9c-48c0-4027-99a3-245d186275ec
ms.openlocfilehash: 58cf9867a9e36b304ab9da79084bc01dff453892
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462661"
---
# <a name="compiler-error-c2014"></a>コンパイラ エラー C2014

プリプロセッサ コマンドは、最初の空白として起動する必要があります。

`#`プリプロセッサ ディレクティブの記号が空白でない行の最初の文字にする必要があります。

次の例では、C2014 が生成されます。

```
// C2014.cpp
int k; #include <stdio.h>   // C2014
```

考えられる解決方法:

```
// C2014b.cpp
// compile with: /c
int k;
#include <stdio.h>
```