---
title: A.1 単純ループの並列実行
ms.date: 11/04/2016
ms.assetid: b8aaacae-b20d-4b16-a540-54ccbf09582b
ms.openlocfilehash: 5bd9a9c8b1d226c67f7e9031a547e551fae3407b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50558939"
---
# <a name="a1---executing-a-simple-loop-in-parallel"></a>A.1 単純ループの並列実行

次の例では、単純なループを使用して、並列化する方法、`parallel for`ディレクティブ ([セクション 2.5.1](../../parallel/openmp/2-5-1-parallel-for-construct.md) [16] ページ)。 ループの反復変数は既定では、プライベートなは、明示的に private 句で指定する必要はありませんが。

```
#pragma omp parallel for
    for (i=1; i<n; i++)
        b[i] = (a[i] + a[i-1]) / 2.0;
```