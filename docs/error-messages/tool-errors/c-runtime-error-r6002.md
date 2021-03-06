---
title: C ランタイム エラー R6002
ms.date: 11/04/2016
f1_keywords:
- R6002
helpviewer_keywords:
- R6002
ms.assetid: 8fbbe65a-9c43-459e-8342-e1f6d1cef7d0
ms.openlocfilehash: f8b5fe69c9fd688f4d0a181176cda247cde9ac11
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648644"
---
# <a name="c-runtime-error-r6002"></a>C ランタイム エラー R6002

浮動小数点のサポートを読み込めませんでした。

浮動小数点に必要なライブラリはリンクされませんでした。

> [!NOTE]
> アプリの実行中にこのエラー メッセージが発生した場合、アプリがシャット ダウン内部の問題があるためです。 このエラーは、いくつかの理由がありますが、多くの場合、アプリのコードの欠陥、またはアプリケーションが構築されていないため、特定のコンピューターのプロセッサを実行しようとして原因が。
>
> このエラーを解決するには、次の手順を試してみます。
>
> - 使用して、**アプリおよび機能**または**プログラムと機能**ページで、**コントロール パネルの **を修復またはプログラムを再インストールします。
> - 確認**Windows Update**で、**コントロール パネルの **ソフトウェアの更新。
> - アプリの更新バージョンを確認します。 問題が解決しない場合は、アプリのベンダーにお問い合わせください。

**プログラマのための情報**

このエラーは、浮動小数点ライブラリがリンクされていないアプリで発生することができます。 これらの原因のいずれかを確認します。

- 書式指定文字列を`printf_s`または`scanf_s`関数には、浮動小数点の書式指定が含まれているし、プログラムは、任意の浮動小数点値または変数がありませんでした。 この問題を解決するには、浮動小数点形式の仕様に対応する浮動小数点引数を使用して、またはプログラムで浮動小数点の割り当てを別の場所で実行します。 これにより、読み込まれる浮動小数点のサポート。

- コンパイラでは、必要な場合にのみ浮動小数点のサポートを読み込むことによって、プログラムのサイズを最小限に抑えます。 コンパイラでは、必要な浮動小数点のルーチンを読み込まないように浮動小数点演算または浮動小数点形式の仕様を書式指定文字列で検出することはできません。 この問題を解決するには、するには、浮動小数点の書式指定を使用して、浮動小数点引数を指定するか、浮動小数点の割り当てをプログラムで他の場所で実行します。 これにより、読み込まれる浮動小数点のサポート。

- C ライブラリは、混合言語のプログラムで、プログラムがリンクされている場合、FORTRAN ライブラリの前に指定されました。 再リンクし、最後に、C ライブラリを指定します。