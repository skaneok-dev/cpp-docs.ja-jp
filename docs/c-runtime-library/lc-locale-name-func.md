---
title: ___lc_locale_name_func
ms.date: 11/04/2016
apiname:
- ___lc_locale_name_func
apilocation:
- msvcrt.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
apitype: DLLExport
f1_keywords:
- ___lc_locale_name_func
helpviewer_keywords:
- ___lc_locale_name_func
ms.assetid: ef858308-872e-43de-95e0-9b1b4084343e
ms.openlocfilehash: 17724fe5335ba54d7e32ed7851b6a35b132b1086
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: HT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50639843"
---
# <a name="lclocalenamefunc"></a>___lc_locale_name_func

内部 CRT 関数。 スレッドの現在のロケール名を取得します。

## <a name="syntax"></a>構文

```cpp
wchar_t** ___lc_locale_name_func(void);
```

## <a name="return-value"></a>戻り値

スレッドの現在のロケール名を含む文字列へのポインター。

## <a name="remarks"></a>コメント

`___lc_locale_name_func` は、CRT データのスレッド ローカル ストレージから現在のロケール名を取得するために、他の CRT 関数によって使用される内部 CRT 関数です。 この情報は、[_get_current_locale](../c-runtime-library/reference/get-current-locale.md) 関数または [setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md) 関数を使用して取得することもできます。

内部 CRT 関数は実装固有であり、各リリースでの変更の対象です。 コード内では使用しないことをお勧めします。

## <a name="requirements"></a>必要条件

|ルーチンによって返される値|必須ヘッダー|
|-------------|---------------------|
|`___lc_locale_name_func`|crt\src\setlocal.h|

## <a name="see-also"></a>参照

[_get_current_locale](../c-runtime-library/reference/get-current-locale.md)<br/>
[setlocale、_wsetlocale](../c-runtime-library/reference/setlocale-wsetlocale.md)<br/>
[_create_locale、_wcreate_locale](../c-runtime-library/reference/create-locale-wcreate-locale.md)<br/>
[_free_locale](../c-runtime-library/reference/free-locale.md)