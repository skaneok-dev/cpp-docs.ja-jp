---
title: コンパイラ エラー C3289
ms.date: 11/04/2016
f1_keywords:
- C3289
helpviewer_keywords:
- C3289
ms.assetid: 3c1c623b-7fcf-43ab-a89a-8722532a8d29
ms.openlocfilehash: 0ebb56023694b1713bfe88379d07fc621da4d43f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50622652"
---
# <a name="compiler-error-c3289"></a>コンパイラ エラー C3289

'property': trivial プロパティはインデックスできません

プロパティが正しく宣言されませんでした。 インデックス付きプロパティに対してアクセサーを定義する必要があります。 詳細については、「 [property](../../windows/property-cpp-component-extensions.md) 」を参照してください。

## <a name="example"></a>例

次の例では C3289 が生成されます。

```
// C3289.cpp
// compile with: /clr
public ref struct C {
   // user-defined simple indexer
   property int indexer1[int];   // C3289

   // user-defined indexer
   property int indexer2[int] {
      int get(int i) { return 0; }
      void set(int i, int j) {}
   }
};

int main() {
   C ^ MyC = gcnew C();
   MyC->indexer2[0] = 1;
}
```