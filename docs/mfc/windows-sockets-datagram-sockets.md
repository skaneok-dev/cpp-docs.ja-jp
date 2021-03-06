---
title: 'Windows ソケット : データグラム ソケット'
ms.date: 11/04/2016
helpviewer_keywords:
- sockets [MFC], datagram
- Windows Sockets [MFC], bi-directional data flow
- datagram sockets [MFC]
- Windows Sockets [MFC], datagram
- sockets [MFC], bi-directional data flow
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
ms.openlocfilehash: 886409d4072a77244cff415c6f0a6a3f533e42d4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50462128"
---
# <a name="windows-sockets-datagram-sockets"></a>Windows ソケット : データグラム ソケット

この記事では、データグラム ソケットでは、使用できる 2 つの Windows ソケット型のいずれかについて説明します。 (その他の型は、[ストリーム ソケット](../mfc/windows-sockets-stream-sockets.md))。

データグラム ソケットをシーケンス処理または重複しないことが保証される双方向データ フローをサポートします。 データグラムが信頼性保証はされませんも受信に失敗したことができます。 データグラム データが到着順不同のおよび場合によって重複が、レコードが、受信側のサイズが内部制限よりも小さい場合に限り、データ内のレコードの境界を保持します。 シーケンス処理と信頼性の管理を担当します。 (信頼性はローカル エリア ネットワーク (LAN) で適切になる傾向がありますが以下でワイド エリア ネットワーク (WAN)、インターネットなど)。

データグラムは「コネクションレス」、つまり、明示的な接続は確立されません。指定したソケットにデータグラム メッセージを送信して、指定したソケットからメッセージを受信できます。

データグラム ソケットの例は、同期されているネットワーク上のシステム クロックを維持するアプリケーションです。 これは、データグラム ソケットで少なくとも一部の設定の追加機能を示しています。 大量のネットワーク アドレスにメッセージをブロードキャストします。

データグラム ソケットは、データのレコード指向ストリーム ソケットよりも優れていますが。 データグラム ソケットの詳細については、Windows SDK で利用できる Windows ソケット仕様を参照してください。

## <a name="see-also"></a>関連項目

[MFC における Windows ソケット](../mfc/windows-sockets-in-mfc.md)<br/>
[Windows ソケット: 予備知識](../mfc/windows-sockets-background.md)

