---
title: /Za、/Ze (言語拡張機能の無効化)
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCCLWCECompilerTool.DisableLanguageExtensions
- /za
- /ze
- VC.Project.VCCLCompilerTool.DisableLanguageExtensions
helpviewer_keywords:
- -Za compiler option [C++]
- Za compiler option [C++]
- language extensions, disabling in compiler
- -Ze compiler option [C++]
- language extensions
- enable language extensions
- /Za compiler option [C++]
- /Ze compiler option [C++]
- Disable Language Extensions compiler option
- Ze compiler option [C++]
ms.assetid: 65e49258-7161-4289-a176-7c5c0656b1a2
ms.openlocfilehash: a3d25f71739f9948f2c0237efbaeaf8fa89f2114
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549722"
---
# <a name="za-ze-disable-language-extensions"></a>/Za、/Ze (言語拡張機能の無効化)

**/Za**コンパイラ オプションは、ANSI C89 または ISO C 11 と互換性がない言語コンストラクトに対してエラーを生成します。 **/Ze**コンパイラ オプションは、既定では、Microsoft の拡張機能を使用します。

## <a name="syntax"></a>構文

```
/Za
/Ze
```

## <a name="remarks"></a>Remarks

> [!NOTE]
>  **/Ze**オプションは、その動作は既定で非推奨とされます。 使用することをお勧めします。、 [/Zc (準拠)](../../build/reference/zc-conformance.md)コンパイラ オプションを特定の言語拡張機能を制御します。 非推奨のコンパイラ オプションの一覧は、次を参照してください。、**非推奨とされた削除済みのコンパイラ オプション**セクション[Compiler Options Listed by Category](../../build/reference/compiler-options-listed-by-category.md)します。

Visual C コンパイラでは、さまざまな ANSI C89、ISO C99、または ISO C 標準で指定された値以上の機能を提供します。 これらの機能は、C および C++ に Microsoft 拡張機能として総称されます。 これらの拡張機能は既定では、使用可能でない場合に、 **/Za**オプションを指定します。 特定の拡張機能の詳細については、次を参照してください。 [C および C++ の Microsoft 拡張機能](../../build/reference/microsoft-extensions-to-c-and-cpp.md)します。

指定することで、言語拡張機能を無効にすることをお勧め、 **/Za**他の環境にプログラムを移植する予定の場合はオプションです。 ときに **/Za**を指定すると、コンパイラは、Microsoft の単純な識別子としてのキーワードの拡張し、その他の Microsoft 拡張機能を無効にし、自動的に定義されます、 `__STDC__` C プログラムの定義済みマクロがあります。

他のコンパイラ オプション併用 **/Za**コンパイラは標準への準拠、方法に影響を与えることができます。

特定の標準に準拠した動作の設定を指定する方法は、次を参照してください。、 [/Zc](../../build/reference/zc-conformance.md)コンパイラ オプション。

Visual C の準拠の問題の詳細については、次を参照してください。[非標準動作](../../cpp/nonstandard-behavior.md)します。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>Visual Studio 開発環境でこのコンパイラ オプションを設定するには

1. プロジェクトの **[プロパティ ページ]** ダイアログ ボックスを開きます。 詳細については、「[プロジェクトのプロパティの操作](../../ide/working-with-project-properties.md)」を参照してください。

1. ナビゲーション ウィンドウで、**構成プロパティ**、 **C/C++**、**言語**します。

1. 変更、**言語拡張機能を無効にする**プロパティ。

### <a name="to-set-this-compiler-option-programmatically"></a>このコンパイラ オプションをコードから設定するには

- 以下を参照してください。<xref:Microsoft.VisualStudio.VCProjectEngine.VCCLCompilerTool.DisableLanguageExtensions%2A>

## <a name="see-also"></a>関連項目

[コンパイラ オプション](../../build/reference/compiler-options.md)<br/>
[コンパイラ オプションの設定](../../build/reference/setting-compiler-options.md)<br/>
[/Zc (準拠)](../../build/reference/zc-conformance.md)
