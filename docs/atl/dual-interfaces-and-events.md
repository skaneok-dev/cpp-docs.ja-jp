---
title: デュアル インターフェイスとイベント
ms.date: 11/04/2016
helpviewer_keywords:
- events [C++], dual interfaces
- dual interfaces, events
ms.assetid: bb382f7c-e885-4274-bf07-83f3602615d2
ms.openlocfilehash: f94e87f077846af8d61b06145f776f385051e79f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50640597"
---
# <a name="dual-interfaces-and-events"></a>デュアル インターフェイスとイベント

デュアルとしてイベント インターフェイスを設計することはできますは、さまざまな行わないような設計上の理由があります。 基本的な理由は、イベントのソースは、vtable を使用して、またはを使用して、イベントの起動でのみ`Invoke`、両方は必要ありません。 イベント ソースが vtable のダイレクト メソッドの呼び出しとしてイベントを発生させる場合、`IDispatch`メソッドは使用されず、インターフェイスが vtable の純粋なインターフェイスであったは明らかです。 呼び出しとイベント ソースがイベントを発生させるかどうか`Invoke`vtable メソッドを使用することはありませんは、インターフェイスがディスパッチ インターフェイスであったクリアします。 デュアル インターフェイスとして、イベント インターフェイスを定義する場合は、使用することはありませんが、インターフェイスの一部を実装するためにクライアントを必要とするします。

> [!NOTE]
>  この引数は一般にデュアル インターフェイスには適用されません。 実装の観点からは、デュアルは、簡単、手軽、かつ適切にサポートされているさまざまなクライアントにアクセスできるインターフェイスを実装する方法です。

さらにデュアル イベント インターフェイスを使用しない理由があります。Visual Basic も Internet Explorer をサポートしています。

## <a name="see-also"></a>関連項目

[デュアル インターフェイスと ATL](../atl/dual-interfaces-and-atl.md)

