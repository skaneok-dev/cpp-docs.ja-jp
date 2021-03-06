---
title: バージョン情報ブロック (C++) の削除
ms.date: 11/04/2016
f1_keywords:
- vc.editors.version
helpviewer_keywords:
- blocks, deleting
- version information, deleting blocks
- resources [C++], deleting version information
ms.assetid: 4e1641eb-d5b2-4183-b273-bc5b51af1537
ms.openlocfilehash: e0bdc719e3ca3a3ffa4493f1d7c578a91733a7f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648306"
---
# <a name="deleting-a-version-information-block-c"></a>バージョン情報ブロック (C++) の削除

### <a name="to-delete-a-version-information-block"></a>バージョン情報ブロックを削除するには

1. [[リソース ビュー]](../windows/resource-view-window.md)でバージョン情報リソースのアイコンをダブルクリックして開きます。

   > [!NOTE]
   > プロジェクトに .rc ファイルがまだ含まれていない場合は、「 [リソース スクリプト ファイルの新規作成](../windows/how-to-create-a-resource-script-file.md)」を参照してください。

2. 削除するブロック ヘッダーを右クリックして、ショートカット メニューから **[バージョン情報ブロックの削除]** を選びます。

   選んだヘッダーはこのコマンドによって削除されますが、残りのバージョン情報はそのまま残ります。 操作を元に戻すことはできませんのでご注意ください。

マネージ プロジェクトにリソースを追加する方法についてを参照してください[Resources in Desktop Apps](/dotnet/framework/resources/index)で、 *.NET Framework 開発者ガイド*します。 マネージ プロジェクトにリソース ファイルを手動で追加、リソースへのアクセス、静的リソースの表示方法、およびリソース文字列のプロパティを割り当てる方法については、次を参照してください。[デスクトップ アプリのリソース ファイルの作成](/dotnet/framework/resources/creating-resource-files-for-desktop-apps)です。 管理対象アプリ内のリソースのグローバリゼーションとローカリゼーションについては、次を参照してください。 [Globalizing and Localizing .NET Framework Applications](/dotnet/standard/globalization-localization/index)します。

## <a name="requirements"></a>必要条件

Win32

## <a name="see-also"></a>関連項目

[バージョン エディター](../windows/version-information-editor.md)<br/>
[バージョン情報 (Windows)](https://msdn.microsoft.com/library/windows/desktop/ms646981.aspx)