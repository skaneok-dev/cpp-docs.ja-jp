---
title: OLE DB サービスの有効化と無効化
ms.date: 10/29/2018
helpviewer_keywords:
- OLE DB services [OLE DB], enabling and disabling
- service providers [OLE DB]
ms.assetid: 445f97eb-32a8-41c2-ad26-1169f78a074f
ms.openlocfilehash: c5eaff8b3b37096eeca8777b6ba8bb91e01d7cd2
ms.sourcegitcommit: 943c792fdabf01c98c31465f23949a829eab9aad
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/07/2018
ms.locfileid: "51265205"
---
# <a name="enabling-and-disabling-ole-db-services"></a>OLE DB サービスの有効化と無効化

OLE DB サービス コンポーネント マネージャーは、コンシューマーが要求された拡張機能を満たすために、個々 のサービス コンポーネントを使用する可能性があるかどうかを決定する、プロバイダーによってサポートされるプロパティにコンシューマーによって指定されたプロパティを比較します。 たとえば、アプリケーションがスクロール可能なカーソルを要求プロバイダーでは、順方向専用カーソルのみがサポート、サービスのコンポーネント マネージャーは、スクロール可能な機能を提供するのにクライアント カーソル エンジンのサービス コンポーネントを使用します。 アプリケーションがプロバイダーの行セットでは、既定でサポートされる拡張機能に依存して、アプリケーションは、機能、機能が表示されないことクライアントによって返される行セットに対して要求するプロパティに明示的に設定しない場合カーソル エンジン。 相互運用できるように、アプリケーションが常にプロパティを設定の拡張機能を明示的に要求するために必要な場合。

場合によっては、プロバイダーの特性を推測する既存のアプリケーションでうまく機能する個々 の OLE DB サービスを無効にする必要があります。 OLE DB サービスでは、個々 のサービス、または接続-接続によってごとに 1 つのプロバイダーを使用してすべてのアプリケーションまたはすべてのサービスを無効にする機能を提供します。

## <a name="see-also"></a>関連項目

[OLE DB リソース プールとサービス](../../data/oledb/ole-db-resource-pooling-and-services.md)