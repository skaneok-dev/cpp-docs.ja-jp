---
title: 以前のランタイム バージョンでの C++ /clr アプリケーションの実行
ms.date: 11/04/2016
helpviewer_keywords:
- applications [C++], runtime version specified
- versions [C++]
- app.config files, runtime version specified
- compatibility [C++], runtime version specified
- backward compatibility [C++], runtime version specified
- application deployment [C++], runtime version specified
- common language runtime [C++], version specified
- deploying applications [C++], runtime version specified
ms.assetid: 940171b7-6937-4b14-8e87-c199e23f4f2e
ms.openlocfilehash: effcda9de1cb1005855f5752060dc61e28dcebf4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50581520"
---
# <a name="running-a-c-clr-application-on-a-previous-runtime-version"></a>以前のランタイム バージョンでの C++ /clr アプリケーションの実行

特に指定されていない限り、C++ .NET Framework アプリケーションは、コンパイラがアプリケーションをビルドするのに使用した共通言語ランタイム (CLR) バージョン上で実行されるようビルドされています。 ただし、ランタイムの 1 つのバージョン用にビルドされた .exe アプリケーションを、必要な機能がある他の任意のバージョン上で実行することは可能です。

これを行うには、ランタイムのバージョン情報を含む app.config ファイルを `supportedRuntime` タグに指定します。

実行時の app.config ファイルは、*filename.ext*.config という名前形式である必要があります。ここで、*filename.ext* は、アプリケーションを開始する実行可能ファイルであり、実行可能ファイルと同じディレクトリに存在している必要があります。 たとえば、アプリケーション名が TestApp.exe である場合、app.config ファイルの名前は TestApp.exe.config になります。

2 つ以上ランタイム バージョンを指定し、複数のランタイム バージョンがインストールされているコンピューターでアプリケーションを実行した場合、アプリケーションでは、config ファイルで指定されてインストールされている最初のバージョンが使用されます。

## <a name="see-also"></a>参照

[デスクトップ アプリケーションの配置](../ide/deploying-native-desktop-applications-visual-cpp.md)