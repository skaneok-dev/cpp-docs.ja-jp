---
title: Null ステートメント (C)
ms.date: 11/04/2016
helpviewer_keywords:
- semicolon, C null statement
- expressions [C++], null
- null statement
- null values, expressions
ms.assetid: 72576ce6-26d0-4379-be65-fee522088790
ms.openlocfilehash: bee044049ed14796a97edc62bbb180ab19700564
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503052"
---
# <a name="null-statement-c"></a>Null ステートメント (C)

"null ステートメント" はセミコロンのみを含むステートメントで、ステートメントが使用できるあらゆる場所に配置できます。 null ステートメントが実行されても、何も処理されません。 null ステートメントのコーディング方法は次のとおりです。

## <a name="syntax"></a>構文

> **;**

## <a name="remarks"></a>コメント

**do**、**for**、**if**、`while` などのステートメントでは、ステートメント本体に実行可能なステートメントを記述する必要があります。 null ステートメントは、実質的なステートメント本体が不要な場合にこの構文の要件を満たします。

null ステートメントは、他の C ステートメントと同様、前にラベルを付けることができます。 ステートメントではない項目 (複合ステートメントの右中かっこ (}) など) にラベルを付けるには、null ステートメントにラベルを付け、それを項目の直前に挿入して同じ効果を得ることができます。

null ステートメントの例を次に示します。

```C
for ( i = 0; i < 10; line[i++] = 0 )
     ;
```

この例では、**for** ステートメントのループ式 `line[i++] = 0` によって、`line` の最初の 10 要素を 0 に初期化します。 それ以上のステートメントが不要であるため、ステートメント本体には null ステートメントを使用します。

## <a name="see-also"></a>参照

[ステートメント](../c-language/statements-c.md)