---
title: /Qfast_transcendentals (超越関数高速化の強制)
ms.date: 11/04/2016
f1_keywords:
- /Qfast_transcendentals
helpviewer_keywords:
- /Qfast_transcendentals
- Force Fast Transcendentals
ms.assetid: 4de24bd1-38e6-49d4-9a05-04c9937d24ac
ms.openlocfilehash: 512e658cf546e77bff6d58465932d2f830541521
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50666129"
---
# <a name="qfasttranscendentals-force-fast-transcendentals"></a>/Qfast_transcendentals (超越関数高速化の強制)

超越関数のインライン コードを生成します。

## <a name="syntax"></a>構文

```
/Qfast_transcendentals
```

## <a name="remarks"></a>Remarks

このコンパイラ オプションでは、実行速度を向上させるために、インライン コードに変換する超越関数を強制します。 このオプションとペアになっている場合にのみ有効 **/fp: 除く**または **/fp: 正確な**します。 超越関数のインライン コードを生成する 既定の動作では既に **/fp:fast**します。

このオプションは互換性がありません **/fp: 厳密な**します。 参照してください[/fp (浮動小数点の動作の指定)](../../build/reference/fp-specify-floating-point-behavior.md)浮動小数点コンパイラ オプションの詳細についてはします。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境において、このコンパイラ オプションを設定する方法

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. **[追加のオプション]** ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[/Q オプション (低水準の操作)](../../build/reference/q-options-low-level-operations.md)<br/>
[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)