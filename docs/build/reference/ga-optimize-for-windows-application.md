---
title: /GA (Windows アプリケーションの最適化)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLCompilerTool.OptimizeForWindowsApplication
- /ga
helpviewer_keywords:
- /GA compiler option [C++]
- GA compiler option [C++]
- -GA compiler option [C++]
- Optimize for Windows compiler options
ms.assetid: be97323e-15a0-4836-862c-95980b51926a
ms.openlocfilehash: 04f8e9e19e5224c1a03ab1c7679d37b7bb8d1389
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50503325"
---
# <a name="ga-optimize-for-windows-application"></a>/GA (Windows アプリケーションの最適化)

スレッド ローカル ストレージ (TLS) の変数にアクセスするため、.exe ファイルをより効率的なコードの結果。

## <a name="syntax"></a>構文

```
/GA
```

## <a name="remarks"></a>Remarks

**/GA**で宣言されたデータへのアクセスを迅速化[_declspec](../../cpp/declspec.md) Windows ベースのプログラムにします。 このオプションが設定されている場合、 [__tls_index](/windows/desktop/ProcThread/thread-local-storage)マクロは 0 と見なされます。

使用して **/GA** DLL が不適切なコード生成になることができます。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. **[C/C++]** フォルダーをクリックします。

1. **[コマンド ライン]** プロパティ ページをクリックします。

1. **[追加のオプション]** ボックスにコンパイラ オプションを入力します。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.AdditionalOptions%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)