---
title: "オートメーション サーバー |Microsoft ドキュメント"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Automation servers
- COM components, Automation servers
- dispatch maps [MFC], Automation servers
- servers, Automation
ms.assetid: 523fd155-51ce-4f91-b986-b74bdbdd7d92
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a33cf8113825804ac831b518e371c4150f2620ad
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/21/2017
---
# <a name="automation-servers"></a>オートメーション サーバー
オートメーションにより別のアプリケーションで実装されているオブジェクトを操作する、または操作できるようにするオブジェクトを公開する、アプリケーションのできます。 オートメーション サーバーは、他のアプリケーションを (オートメーション オブジェクトと呼ばれる) プログラミング可能なオブジェクトを公開するアプリケーション (と呼ばれる[オートメーション クライアント](../mfc/automation-clients.md))。 オートメーション サーバー、オートメーションのコンポーネントとも呼ばれます。  
  
 オートメーション オブジェクトを公開することにより、クライアントは、オブジェクトの直接アクセスして特定の手順を自動化して、サーバーの機能が使用できるようにします。 アプリケーションが他のアプリケーションに役立つ機能を備えている場合、このようにオブジェクトを公開することは有益です。 たとえば、ワード プロセッサは、他のプログラムで使用できるように、そのスペル チェック機能を公開可能性があります。 したがって、オブジェクトを公開には、他のアプリケーションの既製の機能を使用してそのアプリケーションの機能を向上させるためにベンダーができるようにします。  
  
 オートメーション オブジェクトは、外部インターフェイスとしてのプロパティとメソッドがあります。 プロパティには、オートメーション オブジェクトの属性は、という名前です。 プロパティは、C++ のクラスのデータ メンバーに似ています。 メソッドは、オートメーション オブジェクトを使用できる関数です。 メソッドは、C++ のクラスのパブリック メンバー関数に似ています。  
  
> [!NOTE]
>  プロパティは、C++ のデータ メンバーと同様には、直接アクセスすることはありません。 透過的なアクセスを提供するには、それらにアクセスするメンバー関数は取得/設定のペアでオートメーション オブジェクトで内部変数を設定します。  
  
 一般的な適切に定義されたインターフェイスを介してアプリケーションの機能を公開すると、オートメーションできるようになります、1 つ一般的なプログラミング言語での代わりに Microsoft Visual Basic と同様に、アプリケーション固有のさまざまなマクロでアプリケーションを構築するには言語。  
  
##  <a name="_core_support_for_automation_servers"></a>オートメーション サーバー用のサポート  
 Visual C と MFC フレームワークは、オートメーション サーバーの広範なサポートを提供します。 アプリケーションの機能に専念することができますので、オートメーション サーバーの作成には、オーバーヘッドの大半を処理します。  
  
 オートメーションをサポートするため、フレームワークの主要機構は、ディスパッチ マップ、宣言と OLE のメソッドとプロパティを公開するために必要な呼び出しに展開されたマクロのセットです。 典型的なディスパッチ マップは、次のようになります。  
  
 [!code-cpp[NVC_MFCAutomation#1](../mfc/codesnippet/cpp/automation-servers_1.cpp)]  
  
 プロパティ ウィンドウと クラス ビューは、ディスパッチ マップの維持に役立ちます。 Visual C では、対応する追加のクラスに新しいメソッドまたはプロパティを追加すると`DISP_FUNCTION`または`DISP_PROPERTY`マクロ、クラス名、メソッドやプロパティ、およびデータ型の外部および内部の名前を示すパラメーターを使用します。  
  
 **クラスの追加** ダイアログ ボックスは、オートメーション クラスの宣言とそのプロパティと操作の管理も簡素化します。 プロジェクトにクラスを追加するクラスの追加 ダイアログ ボックスを使用する場合は、その基本クラスを指定します。 クラスの追加 ダイアログ ボックスにコントロールを使用して、新しいクラスがオートメーションをサポートするかどうかを指定する"OLE 作成可能な"(つまり、かどうか、クラスのオブジェクト作成できます COM クライアントからの要求に基づいて) であるかどうかが表示されます、基本クラスは、オートメーションを許可している場合、および COM を使用するクライアントの外部名。  
  
 **クラスの追加** ダイアログ ボックスは、クラス宣言を作成し、OLE の機能するのに適切なマクロを含む指定しました。 また、クラスのメンバー関数の実装のスケルトン コードを追加します。  
  
 MFC アプリケーション ウィザードには、地上から、オートメーション サーバー アプリケーションの取得中に必要な手順が簡素化されます。 選択した場合、**オートメーション**のチェック ボックスを**高度な機能**ページで、アプリケーションの MFC アプリケーション ウィザードへ追加`InitInstance`関数、オートメーションを登録するために必要な呼び出しオブジェクトし、オートメーション サーバーとして、アプリケーションを実行します。  
  
### <a name="what-do-you-want-to-do"></a>どうしたいんですか  
  
-   [オートメーション クライアントについてください。](../mfc/automation-clients.md)  
  
-   [CCmdTarget クラスの詳細を表示します](../mfc/reference/ccmdtarget-class.md)  
  
-   [COleDispatchDriver のクラスの詳細を表示します](../mfc/reference/coledispatchdriver-class.md)  
  
## <a name="see-also"></a>参照  
 [オートメーション](../mfc/automation.md)   
 [MFC アプリケーション ウィザード](../mfc/reference/mfc-application-wizard.md)
