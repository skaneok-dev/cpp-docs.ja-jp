---
title: コントロールの選択
ms.date: 11/04/2016
helpviewer_keywords:
- Dialog Editor [C++], selecting controls
- dominant controls
- dialog box controls [C++], selecting in editor
- controls [C++], selecting
- size, controls
- controls [C++], dominant
ms.assetid: 27f05450-4550-4229-9f4c-2c9e06365596
ms.openlocfilehash: ccef63ae6388f376c4be96a34f2857fcedde0ea9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50637100"
---
# <a name="selecting-controls"></a>コントロールの選択

サイズにコントロールを選択、配置、移動、コピー、または削除したり、および必要な操作を実行します。 ほとんどの場合でサイズ変更と配置ツールを使用する 1 つ以上のコントロールを選択する必要があります、[ダイアログ エディター ツールバー](../windows/showing-or-hiding-the-dialog-editor-toolbar.md)します。

コントロールが選択されている、影付きの枠が周囲で実線 (アクティブ) または中空 (非アクティブ) を二乗「サイズ変更ハンドル、」小さいときに選択境界線が表示されます。 複数のコントロールを選択すると、主要なコントロールが実線のサイズ変更ハンドル。その他のすべての選択コントロールでは、白抜きのサイズ変更ハンドルがあります。

複数のコントロールの配置またはサイズ変更するとき、**ダイアログ**エディターは「主要なコントロール」を使用して、他のコントロールのサイズや配置の方法を決定します。 既定では、主要なコントロールは、選択されている最初のコントロールは。

- [複数のコントロールの選択](../windows/selecting-multiple-controls.md)

- [最も優先度の高いコントロールの指定](../windows/specifying-the-dominant-control.md)

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[ダイアログ ボックスのコントロール](../windows/controls-in-dialog-boxes.md)<br/>
[コントロール](../mfc/controls-mfc.md)