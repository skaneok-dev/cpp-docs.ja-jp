---
title: ポインターのインクリメントとデクリメント
ms.date: 11/04/2016
helpviewer_keywords:
- incrementing pointers
- MBCS [C++], pointers
- pointers [C++], multibyte characters
- decrementing pointers
ms.assetid: 0872b4a0-e2bd-4004-8319-070efb76f2fd
ms.openlocfilehash: 1899e3153300bbfbfce068d29351de601f336b6d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567090"
---
# <a name="incrementing-and-decrementing-pointers"></a>ポインターのインクリメントとデクリメント

次のヒントを使用します。

- 先行バイト、いない後続バイトをポイントします。 末尾バイトへのポインターが、通常は安全ではありません。 通常、逆の順序ではなく、順方向に文字列をスキャンするより安全になります。

- ポインターのインクリメントまたはデクリメント関数と全体の文字を重ねると使用可能なマクロがあります。

    ```cpp
    sz1++;
    ```

   ようになります。

    ```cpp
    sz1 = _mbsinc( sz1 );
    ```

   `_mbsinc`と`_mbsdec`関数が正しくインクリメントし、デクリメントで`character`文字のサイズに関係なく、単位。

- デクリメント、次のように、文字列の先頭へのポインターが必要です。

    ```cpp
    sz2--;
    ```

   ようになります。

    ```cpp
    sz2 = _mbsdec( sz2Head, sz2 );
    ```

   または、ヘッド ポインターが、文字列で、有効な文字になります。 ように。

    ```cpp
    sz2Head < sz2
    ```

   既知の有効な先行バイトへのポインターが必要です。

- 高速の呼び出しの前の文字へのポインターを保持したい場合があります`_mbsdec`します。

## <a name="see-also"></a>関連項目

[MBCS のプログラミングについて](../text/mbcs-programming-tips.md)<br/>
[バイト インデックス](../text/byte-indices.md)