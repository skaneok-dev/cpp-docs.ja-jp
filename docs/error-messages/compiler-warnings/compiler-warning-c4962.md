---
title: コンパイラの警告 C4962
ms.date: 11/04/2016
f1_keywords:
- C4962
helpviewer_keywords:
- C4962
ms.assetid: 62b156fe-04e5-4a6e-9339-6ab148185f87
ms.openlocfilehash: e3f7b715da3774d8289fdd526cf1fa0b5bdddba6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50585316"
---
# <a name="compiler-warning-c4962"></a>コンパイラの警告 C4962

'function' : 最適化によってプロファイル データに矛盾が生じたため、ガイド付き最適化のプロファイルを無効にします。

関数のカウント (プロファイル) データの信頼性が低かったため、この関数は /LTCG:PGO を指定してコンパイルされませんでした。 その関数の信頼性の低いプロファイル データを格納している .pgc ファイルを再生成するためにプロファイリングを再実行します。

既定では、この警告はオフに設定されています。 詳細については、「 [Compiler Warnings That Are Off by Default](../../preprocessor/compiler-warnings-that-are-off-by-default.md)」を参照してください。