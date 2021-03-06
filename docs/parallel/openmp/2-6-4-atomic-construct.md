---
title: 2.6.4 atomic コンストラクト
ms.date: 11/04/2016
ms.assetid: e4232ef1-4058-42ce-9de0-0ca788312aba
ms.openlocfilehash: 1f477a59ef475fda9bd0daeeb4edac18a3eeedb9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50677657"
---
# <a name="264-atomic-construct"></a>2.6.4 atomic コンストラクト

`atomic`ディレクティブでは、複数の可能性が公開することではなく特定のメモリ位置が、アトミックに更新されたことにより、同時スレッドを作成します。 構文、`atomic`ディレクティブを次に示します。

```
#pragma omp atomic new-lineexpression-stmt
```

式ステートメントは、次の形式のいずれかが必要です。

*x binop*= *expr*

x++

++x

x--

--x

上記の式。

- *x*スカラー型の左辺値式を指定します。

- *expr* 、スカラー型の式で指定されたオブジェクトを参照しない*x*します。

- `binop` オーバー ロードされた演算子ではないとの 1 つは、+、 \*、-、/、&、^、 &#124;、<\<、または >> します。

実装で定義された実装がすべてを置換するかどうか`atomic`ディレクティブを**重要な**ディレクティブが同じ一意*名前*、`atomic`ディレクティブ許可は、最適化を向上します。 多くの場合、ハードウェアの手順については、最小限のオーバーヘッドでアトミックな更新プログラムを実行することができます。

負荷とで指定されたオブジェクトのストアのみ*x*がアトミック; の評価*expr*アトミックではありません。 競合状態を避けるためには、並列の場所のすべての更新プログラムで保護する必要があります、`atomic`競合状態の認識されているもの以外のディレクティブ。

制限は、`atomic`ディレクティブは、次のとおり。

- プログラム全体で x 記憶域の場所へのすべての分割不可能な参照は、互換性のある型である必要があります。

## <a name="examples"></a>次に例を示します。

```
extern float a[], *p = a, b;
/* Protect against races among multiple updates. */
#pragma omp atomic
a[index[i]] += b;
/* Protect against races with updates through a. */
#pragma omp atomic
p[i] -= 1.0f;

extern union {int n; float x;} u;
/* ERROR - References through incompatible types. */
#pragma omp atomic
u.n++;
#pragma omp atomic
u.x -= 1.0f;
```