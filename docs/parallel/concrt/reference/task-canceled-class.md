---
title: task_canceled クラス
ms.date: 11/04/2016
f1_keywords:
- task_canceled
- CONCRT/concurrency::task_canceled
- CONCRT/concurrency::task_canceled::task_canceled
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
ms.openlocfilehash: b17050deacd1dee0c1b08ffbc4056e957884cd3a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617452"
---
# <a name="taskcanceled-class"></a>task_canceled クラス

このクラスは、現在のタスクを強制的に取り消すために PPL タスク レイヤーによってスローされる例外を表します。 によってもスローされます、`get()`メソッド[タスク](/visualstudio/extensibility/debugger/task-class-internal-members)、取り消されたタスク。

## <a name="syntax"></a>構文

```
class task_canceled : public std::exception;
```

## <a name="members"></a>メンバー

### <a name="public-constructors"></a>パブリック コンストラクター

|名前|説明|
|----------|-----------------|
|[task_canceled](#ctor)|オーバーロードされます。 `task_canceled` オブジェクトを構築します。|

## <a name="inheritance-hierarchy"></a>継承階層

`exception`

`task_canceled`

## <a name="requirements"></a>必要条件

**ヘッダー:** concrt.h

**名前空間:** concurrency

##  <a name="ctor"></a> task_canceled

`task_canceled` オブジェクトを構築します。

```
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```

### <a name="parameters"></a>パラメーター

*メッセージ (_m)*<br/>
エラーの説明メッセージ。

## <a name="see-also"></a>関連項目

[コンカレンシー名前空間](concurrency-namespace.md)
