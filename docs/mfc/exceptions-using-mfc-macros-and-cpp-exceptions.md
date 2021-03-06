---
title: '例外処理 : MFC マクロと C++ 例外機構の使用'
ms.date: 11/04/2016
helpviewer_keywords:
- exception objects [MFC]
- memory leaks [MFC], exception object not deleted
- exception handling [MFC], MFC
- try-catch exception handling [MFC], mixing MFC macros and C++ keywords
- exception objects [MFC], deleting
- exceptions [MFC], MFC macros vs. C++ keywords
- catch blocks [MFC], mixed
- exception handling [MFC], mixed-language
- nested try blocks [MFC]
- catch blocks [MFC], explicitly deleting code in
- try-catch exception handling [MFC], nested try blocks
- heap corruption [MFC]
- nested catch blocks [MFC]
ms.assetid: d664a83d-879b-44d4-bdf0-029f0aca69e9
ms.openlocfilehash: 021f80f71a3921ed10b07f481ff7b7ce934d9f7a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443382"
---
# <a name="exceptions-using-mfc-macros-and-c-exceptions"></a>例外処理 : MFC マクロと C++ 例外機構の使用

この記事では、MFC の例外処理マクロと C++ 例外処理のキーワードの両方を使用するコードの記述に関する考慮事項について説明します。

ここでは、次のトピックについて説明します。

- [例外のキーワードとマクロの混在](#_core_mixing_exception_keywords_and_macros)

- [Try catch ブロック内でのブロック](#_core_try_blocks_inside_catch_blocks)

##  <a name="_core_mixing_exception_keywords_and_macros"></a> 例外のキーワードとマクロの混在

MFC 例外マクロと同じプログラム内での C++ 例外のキーワードを混在させることができます。 ただし、マクロは、例外オブジェクトを自動的に削除、有効範囲外に出ると、例外処理キーワードを使用して、コードは実行されませんので、同じブロック内の C++ 例外のキーワードを持つ MFC マクロを混ぜることはできません。 詳細については、この記事を参照してください。[例外。 例外のキャッチと削除](../mfc/exceptions-catching-and-deleting-exceptions.md)します。

マクロとキーワードの主な違いでは、例外がスコープ外になる、マクロがそのキャッチされた例外を「自動的に」削除することです。 キーワードを使用してコードを削除しません。catch ブロックでキャッチされた例外を明示的に削除する必要があります。 マクロと C++ 例外のキーワードまたは、メモリ リークが発生する例外オブジェクトを削除できなかった場合、ヒープの破損、例外が 2 回削除されるとします。

次のコードでは、例外ポインターなどが無効になります。

[!code-cpp[NVC_MFCExceptions#10](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_1.cpp)]

問題は、 `e` 「内部」から実行が成功したときに削除**キャッチ**ブロックします。 使用して、 **THROW_LAST**マクロの代わりに、**スロー**ステートメントが発生、「外部」**キャッチ**ブロックが有効なポインターを受け取る。

[!code-cpp[NVC_MFCExceptions#11](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_2.cpp)]

##  <a name="_core_try_blocks_inside_catch_blocks"></a> Try Catch ブロック内でのブロック

内から現在の例外を再スローすることはできません、**お試しください**ブロック内にある、**キャッチ**ブロックします。 次の例では、有効です。

[!code-cpp[NVC_MFCExceptions#12](../mfc/codesnippet/cpp/exceptions-using-mfc-macros-and-cpp-exceptions_3.cpp)]

詳細については、次を参照してください。[例外。 例外の内容の調査](../mfc/exceptions-examining-exception-contents.md)します。

## <a name="see-also"></a>関連項目

[例外処理](../mfc/exception-handling-in-mfc.md)

