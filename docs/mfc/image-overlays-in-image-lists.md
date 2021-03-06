---
title: イメージ リストのイメージのオーバーレイ
ms.date: 11/04/2016
helpviewer_keywords:
- overlays [MFC]
- image lists [MFC], image overlays in
- CImageList class [MFC], image overlays in
ms.assetid: aaf4e1c4-cd12-42c8-9af4-1bb458889b4e
ms.openlocfilehash: dc5c28a38d3024f3d8cbd1fa8b9fe9c1c8a09f93
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50603100"
---
# <a name="image-overlays-in-image-lists"></a>イメージ リストのイメージのオーバーレイ

すべてのイメージ リスト ([CImageList](../mfc/reference/cimagelist-class.md)) オーバーレイ マスクとして使用するイメージの一覧が含まれています。 「オーバーレイ マスク」は、別のイメージの上に透過的に描画されるイメージです。 任意のイメージは、オーバーレイ マスクとして使用できます。 イメージ リストごとに最大 4 つのオーバーレイ マスクを指定することができます。

オーバーレイのリストを使用してイメージのインデックスを追加する、 [SetOverlayImage](../mfc/reference/cimagelist-class.md#setoverlayimage)メンバー関数は、イメージのインデックス、およびオーバーレイ マスクのインデックス。 マスクのオーバーレイ インデックスは 1 ベースではなく 0 から始まる、することに注意してください。

1 回の呼び出しを使用してイメージ上でオーバーレイ マスクを描画した`Draw`します。 パラメーターには、描画するイメージのインデックスとオーバーレイ マスクのインデックスが含まれます。 使用する必要があります、[から](/windows/desktop/api/commctrl/nf-commctrl-indextooverlaymask)マクロ オーバーレイ マスクのインデックスを指定します。 呼び出すときに、オーバーレイのイメージを指定することも、[もう 1 つ](../mfc/reference/cimagelist-class.md#drawindirect)メンバー関数。

## <a name="see-also"></a>関連項目

[CImageList の使い方](../mfc/using-cimagelist.md)<br/>
[コントロール](../mfc/controls-mfc.md)

