---
title: コマンド ラインの警告 D9026
ms.date: 11/04/2016
f1_keywords:
- D9026
helpviewer_keywords:
- D9026
ms.assetid: 149fe5e3-5329-4be8-b871-49dfd423aaba
ms.openlocfilehash: 3fd8d442dfabaf2f03d8b564c9fdfb1537f6ff28
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50599434"
---
# <a name="command-line-warning-d9026"></a>コマンド ラインの警告 D9026

オプションはコマンドライン全体に適用されます。

オプションは、ファイル名を指定したら、コマンドで指定されました。 オプションは、前にそのファイルに適用されました。

たとえば、コマンドで

```
CL verdi.c /G5 puccini.c
```

VERDI.c ファイルは、/G4 の既定値ではない、/G5 オプションを使用してコンパイルされます。

この動作は VERDI.c 結果として、ファイル名の前に指定されたオプションを使用してコンパイル/G4 と異なり/G5 を使用してをコンパイルするだけに適用されるいくつか以前のバージョンと異なる。