---
title: ATL アプリケーションの再配布
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, redistributing
- redistributing ATL
- redistributing OLE DB templates
- OLE DB templates, redistributing
ms.assetid: 9a696b22-2345-43ec-826b-be7cb8cfd676
ms.openlocfilehash: 183363f7e69fc6d14ce3f9e681992e774b198928
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50517105"
---
# <a name="redistributing-an-atl-application"></a>ATL アプリケーションの再配布

Visual Studio 2012 以降の Active Template Library (ATL) はヘッダーのみのライブラリです。 ATL プロジェクトには、ATL オプションへの動的リンクはありません。 再配布可能 ATL ライブラリは必要ありません。

ATL 実行可能アプリケーションを再配布する場合は、次のコマンドを実行して、.exe ファイルとそのすべてのコントロールを登録する必要があります。

```
filename /regserver
```

`filename` は実行可能ファイルの名前です。

Visual Studio 2010 では、MinDependency または MinSize 構成用に ATL プロジェクトをビルドできます。 MinDependency 構成は、**[全般]** プロパティ ページの **[ATL の使用]** プロパティを **[ATL に静的にリンク]** に設定し、**[コード生成]** プロパティ ページ ([C/C++] フォルダー) の **[ランタイム タイブラリ]** プロパティを **[マルチスレッド (/MT)]** に設定した場合です。

MinSize 構成は、**[全般]** プロパティ ページの **[ATL の使用]** プロパティを **[ATL に動的にリンク]** に設定し、**[コード生成]** プロパティ ページ ([C/C++] フォルダー) の **[ランタイム タイブラリ]** プロパティを **[マルチスレッド DLL (/MD)]** に設定した場合です。

MinSize を使用すると、出力ファイルは可能な範囲で最小になりますが、ターゲット コンピューターに ATL100.dll と Msvcr100.dll (**[マルチスレッド DLL (/MD)]** オプションを選択した場合) が必要になります。 すべての ATL 機能を使用できるようにするために、ATL100.dll をターゲット コンピューターに登録する必要があります。 ATL100.dll には ANSI および Unicode エクスポートが含まれています。

ATL または OLE DB テンプレート プロジェクトを MinDependency ターゲット用にビルドした場合、ターゲット コンピューターへの ATL100.dll のインストールと登録は不要ですが、プログラム イメージが大きくなります。

ATL 実行可能アプリケーションを再配布する場合は、次のコマンドを実行して、.exe ファイルとそのすべてのコントロールを登録する必要があります。

```
filename /regserver
```

`filename` は実行可能ファイルの名前です。

## <a name="see-also"></a>参照

[Visual C++ ファイルの再配布](../ide/redistributing-visual-cpp-files.md)