---
title: NMAKE の警告 U4004
ms.date: 11/04/2016
f1_keywords:
- U4004
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
ms.openlocfilehash: 882f6c98b31d23d283f5e8b32b46a46c543b1a76
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50436219"
---
# <a name="nmake-warning-u4004"></a>NMAKE の警告 U4004

ターゲット 'targetname' のルールが多すぎます

1 つ以上の記述ブロックでは、1 つのコロンを使用して、指定されたターゲットが指定されました (**:**) 区切り記号として。 NMAKE では、最初の記述ブロックのコマンドを実行し、後のブロックを無視します。

複数の依存関係で同じターゲットを指定する 2 つのコロンを使用して、(`::`) 依存関係の行ごとに、区切り文字として。