---
title: コンパイラの警告 (レベル 1) C4399
ms.date: 11/04/2016
f1_keywords:
- C4399
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
ms.openlocfilehash: 56fe0f314142d873fc02136bc2c3fe65e71f4dda
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50544067"
---
# <a name="compiler-warning-level-1-c4399"></a>コンパイラの警告 (レベル 1) C4399

> '*シンボル*': は/clr でコンパイルされたときに、プロセスごとのシンボルをマークしない必要があります: 純粋な

## <a name="remarks"></a>Remarks

**/Clr: 純粋な**コンパイラ オプションは Visual Studio 2015 で非推奨とされ、Visual Studio 2017 でサポートされていません。

ネイティブ イメージまたはネイティブ モードと CLR コンストラクトを使用してイメージからのデータを純粋なイメージにインポートすることはできません。 この警告を解決するには、使用してコンパイル **/clr** (いない **/clr: 純粋な**) を削除または`__declspec(dllimport)`します。

## <a name="example"></a>例

次の例では、C4399 が生成されます。

```cpp
// C4399.cpp
// compile with: /clr:pure /doc /W1 /c
__declspec(dllimport) __declspec(process) extern const int i;   // C4399
```