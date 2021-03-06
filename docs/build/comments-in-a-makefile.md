---
title: メイクファイルのコメント
ms.date: 11/04/2016
helpviewer_keywords:
- makefiles, comments
ms.assetid: 76fd9e3d-5966-47f4-a091-c9e80b232b49
ms.openlocfilehash: 91fb9001378973c86ffaaf7fd841e3c679444ef9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50625850"
---
# <a name="comments-in-a-makefile"></a>メイクファイルのコメント

シャープ記号付きのコメントの前 (#)。 NMAKE では、次の改行文字にシャープ記号からのテキストは無視されます。 次に例を示します。

```
# Comment on line by itself
OPTIONS = /MAP  # Comment on macro definition line

all.exe : one.obj two.obj  # Comment on dependency line
    link one.obj two.obj
# Comment in commands block
#   copy *.obj \objects  # Command turned into comment
    copy one.exe \release

.obj.exe:  # Comment on inference rule line
    link $<

my.exe : my.obj ; link my.obj  # Err: cannot comment this
# Error: # must be the first character
.obj.exe: ; link $<  # Error: cannot comment this
```

リテラルの番号記号を指定する前にカレット (**^**)、次のようにします。

```
DEF = ^#define  #Macro for a C preprocessing directive
```

## <a name="see-also"></a>関連項目

[メイクファイルの内容](../build/contents-of-a-makefile.md)