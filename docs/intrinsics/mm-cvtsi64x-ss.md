---
title: _mm_cvtsi64x_ss
ms.date: 11/04/2016
f1_keywords:
- _mm_cvtsi64x_ss
helpviewer_keywords:
- cvtsi2ss instruction
- _mm_cvtsi64x_ss intrinsic
ms.assetid: 01e5d321-c18a-46fd-a6f6-324364514e1f
ms.openlocfilehash: 4b8d0e1a19441cd671143843ae4ac6e89bfeae50
ms.sourcegitcommit: 1819bd2ff79fba7ec172504b9a34455c70c73f10
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/09/2018
ms.locfileid: "51328943"
---
# <a name="mmcvtsi64xss"></a>_mm_cvtsi64x_ss

**Microsoft 固有の仕様**

拡張 x64 を生成します。 スカラー単精度浮動小数点値に変換する 64 ビット整数のバージョン (`cvtsi2ss`) 命令。

## <a name="syntax"></a>構文

```
__m128 _mm_cvtsi64x_ss(
   __m128 a,
   __int64 b
);
```

#### <a name="parameters"></a>パラメーター

*a*<br/>
[in]`__m128` 4 つの単精度浮動小数点値を含む構造体。

*b*<br/>
[in]浮動小数点値に変換する 64 ビット整数。

## <a name="return-value"></a>戻り値

`__m128`最初の浮動小数点値が変換の結果は、構造体。 その他の 3 つの値から変更されていないコピー`a`します。

## <a name="requirements"></a>必要条件

|組み込み|アーキテクチャ|
|---------------|------------------|
|`_mm_cvtsi64x_ss`|X64|

**ヘッダー ファイル** \<intrin.h >

## <a name="remarks"></a>Remarks

`__m128`構造体が、XMM レジスタを表し、値は、そのため、この組み込み`b`からシステム メモリ、XMM に移動するのには、登録します。

このルーチンは、組み込みとしてのみ使用できます。

## <a name="example"></a>例

```
// _mm_cvtsi64x_ss.cpp
// processor: x64

#include <intrin.h>
#include <stdio.h>

#pragma intrinsic(_mm_cvtsi64x_ss)

int main()
{
    __m128 a;
    __int64 b = 54;

    a.m128_f32[0] = 0;
    a.m128_f32[1] = 0;
    a.m128_f32[2] = 0;
    a.m128_f32[3] = 0;
    a = _mm_cvtsi64x_ss(a, b);

    printf_s( "%lf %lf %lf %lf\n",
              a.m128_f32[0], a.m128_f32[1],
              a.m128_f32[2], a.m128_f32[3] );
}
```

```Output
54.000000 0.000000 0.000000 0.000000
```

**Microsoft 固有の仕様はここまで**

## <a name="see-also"></a>関連項目

[__m128](../cpp/m128.md)<br/>
[コンパイラの組み込み](../intrinsics/compiler-intrinsics.md)