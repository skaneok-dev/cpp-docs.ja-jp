---
title: インライン ファイルのテキストの作成
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, creating text
- NMAKE program, inline files
- text, inline file
ms.assetid: b8a332ed-8244-4ff8-89e6-029d7f659725
ms.openlocfilehash: 4989d0757e893a7bc4b0a0e8937afee18719aa4e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523106"
---
# <a name="creating-inline-file-text"></a>インライン ファイルのテキストの作成

インライン ファイルは、一時的または永続的です。

## <a name="syntax"></a>構文

```
inlinetext
.
.
.
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>Remarks

指定*inlinetext*コマンドの後に最初の行にします。 二重山かっこと終わりをマーク (<<) を別の行の先頭にします。 ファイルがすべて含まれています*inlinetext*区切り記号の角かっこの前にします。 *Inlinetext*マクロの展開との置換がしないディレクティブまたはメイクファイルのコメントを持つことができます。 スペース、タブ、および改行文字リテラルに扱われます。

一時ファイルは、セッションの間存在し、その他のコマンドで再利用することができます。 指定**保持**NMAKE セッション後にファイルを保持する閉じる山かっこの後に、名前のないファイルが生成されたファイル名でディスクに保存されます。 指定**NOKEEP**または一時ファイルのものがありません。 **保持**と**NOKEEP**小文字は区別されません。

## <a name="see-also"></a>関連項目

[メイクファイルのインライン ファイル](../build/inline-files-in-a-makefile.md)