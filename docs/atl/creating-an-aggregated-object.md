---
title: 集約オブジェクトの作成
ms.date: 11/04/2016
helpviewer_keywords:
- aggregation [C++], creating aggregated objects
- aggregate objects [C++], creating
ms.assetid: fc29d7aa-fd53-4276-9c2f-37379f71b179
ms.openlocfilehash: 5c655b8ced7738b30bf13d088cfadf11b5c65ef0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50449856"
---
# <a name="creating-an-aggregated-object"></a>集約オブジェクトの作成

集計デリゲート`IUnknown`、外側のオブジェクトへのポインターを提供する呼び出し`IUnknown`を内部オブジェクト。

## <a name="to-create-an-aggregated-object"></a>集約オブジェクトを作成するには

1. 追加、`IUnknown`クラスへのポインター オブジェクトをコンス トラクターで NULL に初期化します。

1. オーバーライド[finalconstruct 関数](../atl/reference/ccomobjectrootex-class.md#finalconstruct)集計を作成します。

1. 使用して、`IUnknown`の 2 番目のパラメーターとして、手順 1. で定義されているポインター、[で定義](reference/com-interface-entry-macros.md#com_interface_entry_aggregate)マクロ。

1. オーバーライド[FinalRelease](../atl/reference/ccomobjectrootex-class.md#finalrelease)を解放する、`IUnknown`ポインター。

> [!NOTE]
> 使用して中に集計されたオブジェクトのインターフェイスを解放するかどうかは`FinalConstruct`、追加する必要があります、[アグリゲート](reference/aggregation-and-class-factory-macros.md#declare_protect_final_construct)クラスのオブジェクトの定義にマクロ。

## <a name="see-also"></a>関連項目

[ATL COM オブジェクトの基礎](../atl/fundamentals-of-atl-com-objects.md)

