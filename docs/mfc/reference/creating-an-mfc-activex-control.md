---
title: MFC ActiveX コントロールの作成
ms.date: 09/12/2018
f1_keywords:
- vc.appwiz.activex.project
helpviewer_keywords:
- MFC ActiveX controls [MFC], creating
- ActiveX controls [MFC], creating
ms.assetid: 8bd5a93c-d04d-414e-bb28-163fdc1c0dd5
ms.openlocfilehash: be0b4639fd42461a19db10f88ced336cd1129fb3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50633516"
---
# <a name="creating-an-mfc-activex-control"></a>MFC ActiveX コントロールの作成

ActiveX コントロール プログラムは、親アプリケーションに特定の機能を提供するモジュール プログラムです。 たとえば、ダイアログ ボックスのボタンや Web ページのツール バーなどのコントロールを作成できます。

>[!IMPORTANT]
> ActiveX は、新規の開発が使用できないレガシ テクノロジです。 詳細については、次を参照してください。 [ActiveX コントロール](../activex-controls.md)します。

MFC ActiveX コントロールを作成する最も簡単な方法が使用するには、 [MFC ActiveX コントロール ウィザード](../../mfc/reference/mfc-activex-control-wizard.md)します。

### <a name="to-create-an-mfc-activex-control-using-the-mfc-activex-control-wizard"></a>MFC ActiveX コントロール ウィザードを使用して MFC ActiveX コントロールを作成するには

1. ヘルプ トピックの「[アプリケーション ウィザードを使用したデスクトップ プロジェクトの作成](../../ide/creating-desktop-projects-by-using-application-wizards.md)」の手順に従います。

1. **新しいプロジェクト**ダイアログ ボックスで、 **MFC ActiveX コントロール**MFC ActiveX コントロール ウィザードを開く [テンプレート] ペインでアイコン。

1. 定義、[アプリケーション設定](../../mfc/reference/application-settings-mfc-activex-control-wizard.md)、[コントロール名](../../mfc/reference/control-names-mfc-activex-control-wizard.md)、および[設定を制御](../../mfc/reference/control-settings-mfc-activex-control-wizard.md)MFC ActiveX コントロール ウィザードを使用します。

    > [!NOTE]
    >  ウィザードの既定の設定を使用する場合は、この手順を省略します。

1. クリックして**完了**ウィザードを終了し、開発環境で新しいプロジェクトを開きます。

作成されたファイルを表示するには、プロジェクトを作成した後**ソリューション エクスプ ローラー**します。 ウィザードでプロジェクト用に作成されるファイルの詳細については、プロジェクトが生成する ReadMe.txt ファイルを参照してください。 ファイルの種類についての詳細については、次を参照してください。 [Visual c プロジェクトに対して作成されるファイルの種類](../../ide/file-types-created-for-visual-cpp-projects.md)します。

追加するコード ウィザードを使用するには、プロジェクトを作成した後[関数](../../ide/add-member-function-wizard.md)、[変数](../../ide/add-member-variable-wizard.md)、[イベント](../../ide/add-event-wizard.md)、[プロパティ](../../ide/names-add-property-wizard.md)と[メソッド](../../ide/add-method-wizard.md)します。 ActiveX コントロールのカスタマイズの詳細については、次を参照してください。 [MFC ActiveX コントロール](../../mfc/mfc-activex-controls.md)します。

## <a name="see-also"></a>関連項目

[コード ウィザードを使用した機能の追加](../../ide/adding-functionality-with-code-wizards-cpp.md)<br/>
[プロパティ ページ](../../ide/property-pages-visual-cpp.md)

