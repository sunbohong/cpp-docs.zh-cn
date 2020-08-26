---
title: /HIGHENTROPYVA
ms.date: 06/12/2018
f1_keywords:
- /HIGHENTROPYVA
helpviewer_keywords:
- HIGHENTROPYVA editbin option
- -HIGHENTROPYVA editbin option
- /HIGHENTROPYVA editbin option
ms.assetid: ef4b7c63-440d-40ca-b39d-edefb3217505
ms.openlocfilehash: 80e34a3f57974e1af6afb65196697cce9aa344b1
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88834994"
---
# <a name="highentropyva"></a>/HIGHENTROPYVA

指定可执行映像是否支持高熵 64 位地址空间布局随机化 (ASLR)。

## <a name="syntax"></a>语法

> **`/HIGHENTROPYVA`**[**`:NO`**]

## <a name="remarks"></a>注解

此选项修改 *可执行图像* 文件的标头 (例如， *`.dll`* 或 *`.exe`* 文件) ，以指示支持64位地址 ASLR。 若要获得效果，请在可执行文件和它所依赖的所有模块上都设置选项。 然后，支持64位 ASLR 的操作系统可在加载时使用随机64位虚拟地址将可执行映像的段变基。 更大的地址空间使攻击者更难猜到特定内存区域的位置。

默认情况下，链接器将启用 **`/HIGHENTROPYVA`** 64 位可执行文件映像。 此选项需要 [`/DYNAMICBASE`](dynamicbase.md) 和 [`/LARGEADDRESSAWARE`](largeaddressaware.md) ，这在默认情况下也可用于64位映像。 **`/HIGHENTROPYVA`** 不适用于32位可执行文件映像，其中的选项会被忽略。 若要显式禁用此选项，请使用 **`/HIGHENTROPYVA:NO`** 。

## <a name="see-also"></a>请参阅

[EDITBIN 选项](editbin-options.md)\
[`/DYNAMICBASE`](dynamicbase.md)\
[`/LARGEADDRESSAWARE`](largeaddressaware.md)\
[Windows ISV 软件安全防御](/previous-versions/bb430720(v=msdn.10))
