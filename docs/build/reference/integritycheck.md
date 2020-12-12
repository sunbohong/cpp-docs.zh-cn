---
description: 了解详细信息：/INTEGRITYCHECK
title: /INTEGRITYCHECK
ms.date: 12/28/2017
f1_keywords:
- /INTEGRITYCHECK
helpviewer_keywords:
- -INTEGRITYCHECK editbin options
- /INTEGRITYCHECK editbin options
- INTEGRITYCHECK editbin options
ms.openlocfilehash: b1ea8275bdb356febcf18a2a55b6ab718d8eea96
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199657"
---
# <a name="integritycheck"></a>/INTEGRITYCHECK

指定必须在加载时检查二进制文件的数字签名。

> **/INTEGRITYCHECK**[**： NO**]

## <a name="remarks"></a>备注

在 DLL 文件或可执行文件的标头中，此选项将设置一个标志，该标志需要由内存管理器在 Windows 中加载图像时进行数字签名检查。 Windows Vista 之前的 Windows 版本忽略此标志。 必须为实现内核模式代码的64位 Dll 设置此选项，并且建议将其用于所有设备驱动程序。 有关详细信息，请参阅 [内核模式代码签名要求](/windows-hardware/drivers/install/kernel-mode-code-signing-requirements--windows-vista-and-later-)。

## <a name="see-also"></a>请参阅

[EDITBIN 选项](editbin-options.md)
