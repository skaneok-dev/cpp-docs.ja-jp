---
title: /INTEGRITYCHECK
ms.date: 12/28/2017
f1_keywords:
- /INTEGRITYCHECK
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
ms.openlocfilehash: b3f6622e3628db53c363b239c59accd94f708ab0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 10/31/2018
ms.locfileid: "50617272"
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

読み込み時にバイナリ イメージのデジタル署名を確認する必要があることを指定します。

> **/INTEGRITYCHECK****[: NO]**

## <a name="remarks"></a>Remarks

DLL ファイルまたは実行可能ファイルのヘッダーで、このオプションは、Windows でイメージを読み込むために、メモリ マネージャーによるデジタル署名の確認を必要とするフラグを設定します。 Windows Vista 以前の Windows は、このフラグを無視します。 このオプションは、カーネル モード コードを実装する 64 ビット DLL には設定する必要があり、またすべてのデバイス ドライバーに推奨されます。 詳細については、次を参照してください。[カーネル モード コード署名要件](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-)します。

## <a name="see-also"></a>関連項目

[EDITBIN オプション](../../build/reference/editbin-options.md)
