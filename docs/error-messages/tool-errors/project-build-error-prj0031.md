---
title: プロジェクト ビルド エラー PRJ0031
ms.date: 11/04/2016
f1_keywords:
- PRJ0031
helpviewer_keywords:
- PRJ0031
ms.assetid: b42435c6-e570-4f8e-9ad5-12a7ea69ccb2
ms.openlocfilehash: e5edae0c1b7464e4a3a5e9523332ce956d0dcf92
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50648592"
---
# <a name="project-build-error-prj0031"></a>プロジェクト ビルド エラー PRJ0031

カスタム ビルドの 'Outputs' プロパティは、'macro_expansion' をファイル 'file' に含まれている 'macro' 評価を出すのステップします。

ファイルのカスタム ビルド ステップでは、おそらくマクロ評価の問題により、不正な出力がありました。 このエラーにあるパス形式が正しくない、文字またはファイル パスでは無効な文字の組み合わせを含むもします。

このエラーを解決するのには、マクロを修正するか、パスの指定を修正します。 パスには、プロジェクト ディレクトリからの絶対パスを指定します。