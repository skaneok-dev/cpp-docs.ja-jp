---
title: フレーム ウィンドウ スタイル (C++)
ms.date: 11/04/2016
helpviewer_keywords:
- window styles [MFC]
- PreCreateWindow method, setting window styles
- windows [MFC], MFC
- frame windows [MFC], styles
- MFC, frame windows
- styles [MFC], windows
ms.assetid: fc5058c1-eec8-48d8-9f76-3fc01cfa53f7
ms.openlocfilehash: 01eb593e6a7c896b3c6e4acf9f753b73a346e3e7
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50510748"
---
# <a name="frame-window-styles-c"></a>フレーム ウィンドウ スタイル (C++)

フレームワークのフレーム ウィンドウは、ほとんどのプログラムに適していますが、高度な関数を使用してさらに高い柔軟性を得ることができます、 [PreCreateWindow](../mfc/reference/cwnd-class.md#precreatewindow)と MFC のグローバル関数[AfxRegisterWndClass](../mfc/reference/application-information-and-management.md#afxregisterwndclass). `PreCreateWindow` メンバー関数は、`CWnd`します。

適用する場合、 **WS_HSCROLL**と**WS_VSCROLL**メイン フレーム ウィンドウ スタイル、代わりに適用されるため、 **MDICLIENT**ウィンドウをスクロールすると、ように**MDICLIENT**領域。

場合、ウィンドウの**FWS_ADDTOTITLE**スタイル ビットが設定されます (これには、既定では)、ビューのドキュメント、ビューの名前に基づいて、ウィンドウのタイトル バーに表示するタイトルをフレーム ウィンドウに指示します。

## <a name="what-do-you-want-to-know-more-about"></a>方法については、するして操作を行います

- [MDI 子ウィンドウ (クイック ウォッチ) の管理](../mfc/managing-mdi-child-windows.md)MDI 子ウィンドウを含む MDI フレーム ウィンドウ

- [MFC で作成したウィンドウのスタイルを変更します。](../mfc/changing-the-styles-of-a-window-created-by-mfc.md)

- [ウィンドウ スタイル](../mfc/reference/styles-used-by-mfc.md#window-styles)

## <a name="see-also"></a>関連項目

[フレーム ウィンドウ](../mfc/frame-windows.md)

