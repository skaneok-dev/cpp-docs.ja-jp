---
title: '方法: リソースを作成する (C++)'
ms.date: 11/04/2016
helpviewer_keywords:
- toolbars [C++], resources
- resource toolbars
- resources [C++], creating
ms.assetid: aad44914-9145-45a3-a7d8-9de89b366716
ms.openlocfilehash: 75f7f722b354e60b86abdeb9a3f9a01469aefcf8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50513695"
---
# <a name="how-to-create-a-resource"></a>方法: リソースを作成する

> [!NOTE]
> **リソース ビュー**は Express edition でサポートされていません。

### <a name="to-create-a-new-resource-in-resource-view"></a>リソース ビューでリソースを新規作成するには

1. .Rc ファイルに重点を置いて[リソース ビュー](../windows/resource-view-window.md)、 をクリックして、**編集**メニュー選択**リソースの追加**(で .rc ファイルを右クリックしてまたは**リソース ビュー**選択**リソースの追加**ショートカット メニューから)。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. [[リソースの追加] ダイアログ ボックス](../windows/add-resource-dialog-box.md)で、プロジェクトに追加するリソースを選択します。

### <a name="to-create-a-new-resource-in-solution-explorer"></a>ソリューション エクスプローラーでリソースを新規作成するには

1. **ソリューション エクスプローラー**でプロジェクト フォルダーを右クリックし、ショートカット メニューの **[追加]**、 **[リソースの追加]** の順にクリックします。

   プロジェクトに .rc ファイルがない場合は、この手順で作成されます。 その後、この手順を繰り返すと、特定のリソースの種類を新しい .rc ファイルに追加できます。

2. [[リソースの追加] ダイアログ ボックス](../windows/add-resource-dialog-box.md)で、プロジェクトに追加するリソースを選択します。

### <a name="to-create-a-new-resource-in-class-view"></a>クラス ビューでリソースを新規作成するには

1. [クラス ビュー](/visualstudio/ide/viewing-the-structure-of-code)クラスを右クリックして選択**追加**、 をクリックし、**リソースの追加**ショートカット メニューから。

2. [[リソースの追加] ダイアログ ボックス](../windows/add-resource-dialog-box.md)で、プロジェクトに追加するリソースを選択します。

### <a name="to-create-a-new-resource-from-the-project-menu"></a>[プロジェクト] メニューからリソースを新規作成するには

1. **[プロジェクト]** メニューの **[リソースの追加]** を選択します。

新しいリソースを作成するときに Visual C 一意の名前を割り当てる、たとえば、`IDD_Dialog1`します。 関連するリソース エディターまたは [プロパティ ウィンドウ](/visualstudio/ide/reference/properties-window)でリソースのプロパティを編集することによって、このリソース ID をカスタマイズできます。

リソースは、新しい既定のリソース (テンプレートに基づいていないリソース) として作成するか、または [テンプレート](../windows/how-to-use-resource-templates.md)の後でパターン化されるリソースとして作成できます。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[リソース ファイル](../windows/resource-files-visual-studio.md)<br/>
[リソース エディター](../windows/resource-editors.md)<br/>
[Add Resource Dialog Box](../windows/add-resource-dialog-box.md)