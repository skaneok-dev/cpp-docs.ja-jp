---
title: IWorkerThreadClient インターフェイス
ms.date: 11/04/2016
f1_keywords:
- IWorkerThreadClient
- ATLUTIL/ATL::IWorkerThreadClient
- ATLUTIL/ATL::CloseHandle
- ATLUTIL/ATL::Execute
helpviewer_keywords:
- IWorkerThreadClient interface
ms.assetid: 56f4a2f5-007e-4a33-9e20-05187629f715
ms.openlocfilehash: 22ea136dd91a514ff10e13cd02b796565b7b0307
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50523636"
---
# <a name="iworkerthreadclient-interface"></a>IWorkerThreadClient インターフェイス

`IWorkerThreadClient` クライアントによって実装されるインターフェイスは、 [CWorkerThread](../../atl/reference/cworkerthread-class.md)クラス。

> [!IMPORTANT]
>  このクラスとそのメンバーは、Windows ランタイムで実行するアプリケーションでは使用できません。

## <a name="syntax"></a>構文

```
__interface IWorkerThreadClient
```

## <a name="members"></a>メンバー

### <a name="methods"></a>メソッド

|||
|-|-|
|[CloseHandle](#closehandle)|このオブジェクトに関連付けられたハンドルを終了するには、このメソッドを実装します。|
|[Execute](#execute)|このオブジェクトに関連付けられたハンドルがシグナル状態コードを実行するには、このメソッドを実装します。|

## <a name="remarks"></a>Remarks

シグナル状態になるハンドルへの応答でワーカー スレッドで実行する必要があるコードがある場合は、このインターフェイスを実装します。

## <a name="requirements"></a>必要条件

**ヘッダー:** atlutil.h

##  <a name="closehandle"></a>  IWorkerThreadClient::CloseHandle

このオブジェクトに関連付けられたハンドルを終了するには、このメソッドを実装します。

```
HRESULT CloseHandle(HANDLE  hHandle);
```

### <a name="parameters"></a>パラメーター

*hHandle*<br/>
終了するハンドル。

### <a name="return-value"></a>戻り値

成功した場合、またはエラー発生時のエラー HRESULT が S_OK を返します。

### <a name="remarks"></a>Remarks

このメソッドに渡されたハンドルが既に関連付けられているこのオブジェクトへの呼び出しによって[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)します。

### <a name="example"></a>例

次のコードの単純な実装を示しています。`IWorkerThreadClient::CloseHandle`します。

[!code-cpp[NVC_ATL_Utilities#135](../../atl/codesnippet/cpp/iworkerthreadclient-interface_1.cpp)]

##  <a name="execute"></a>  IWorkerThreadClient::Execute

このオブジェクトに関連付けられたハンドルがシグナル状態コードを実行するには、このメソッドを実装します。

```
HRESULT Execute(DWORD_PTR dwParam, HANDLE hObject);
```

### <a name="parameters"></a>パラメーター

*について*<br/>
ユーザー パラメーター。

*hObject*<br/>
このハンドルがシグナル状態になります。

### <a name="return-value"></a>戻り値

成功した場合、またはエラー発生時のエラー HRESULT が S_OK を返します。

### <a name="remarks"></a>Remarks

このメソッドに渡された DWORD/ポインター、ハンドルがへの呼び出しでこのオブジェクトに既に関連付け[CWorkerThread::AddHandle](../../atl/reference/cworkerthread-class.md#addhandle)します。

### <a name="example"></a>例

次のコードの単純な実装を示しています。`IWorkerThreadClient::Execute`します。

[!code-cpp[NVC_ATL_Utilities#136](../../atl/codesnippet/cpp/iworkerthreadclient-interface_2.cpp)]

## <a name="see-also"></a>関連項目

[クラス](../../atl/reference/atl-classes.md)<br/>
[CWorkerThread クラス](../../atl/reference/cworkerthread-class.md)
