---
title: /HIGHENTROPYVA（支持 64 位 ASLR）
ms.date: 06/12/2018
ms.assetid: fe35f9f7-d28e-4694-9aeb-a79db06168e0
ms.openlocfilehash: ead296b1bd31171fb1a187685f407f6a0cf8a74c
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835020"
---
# <a name="highentropyva-support-64-bit-aslr"></a>/HIGHENTROPYVA（支持 64 位 ASLR）

指定可执行映像是否支持高熵 64 位地址空间布局随机化 (ASLR)。

## <a name="syntax"></a>语法

> **`/HIGHENTROPYVA`**[**`:NO`**]

## <a name="remarks"></a>注解

**`/HIGHENTROPYVA`** 修改 *可执行图像* 文件的标头 (例如， *`.dll`* 或 *`.exe`* 文件) ，以指示 ASLR 是否可以使用整个64位地址空间。  若要获得效果，请在可执行文件和它所依赖的所有模块上都设置选项。 然后，支持64位 ASLR 的操作系统可在加载时使用64位随机虚拟地址来变基可执行映像的段。 更大的地址空间使攻击者更难猜到特定内存区域的位置。

默认情况下， **`/HIGHENTROPYVA`** 为64位可执行文件映像启用。 此选项要求 [`/LARGEADDRESSAWARE`](largeaddressaware-handle-large-addresses.md) 在默认情况下为64位映像启用此选项。 **`/HIGHENTROPYVA`** 不适用于32位可执行文件映像，链接器忽略该选项。 若要显式禁用此选项，请使用 **`/HIGHENTROPYVA:NO`** 。

**`/HIGHENTROPYVA`** 若要在加载时产生效果， [`/DYNAMICBASE`](dynamicbase-use-address-space-layout-randomization.md) 还必须启用。 **`/DYNAMICBASE`** 默认情况下启用，并且在 Windows Vista 和更高版本的操作系统中启用 ASLR 时需要。 Windows 的早期版本忽略此标志。

### <a name="to-set-this-linker-option-in-visual-studio"></a>在 Visual Studio 中设置此链接器选项

1. 打开项目“属性页” **** 对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**  >  **链接器**  >  **命令行**" 属性页。

1. 在 " **其他选项**" 中，输入 `/HIGHENTROPYVA` 或 `/HIGHENTROPYVA:NO` 。

## <a name="see-also"></a>另请参阅

- [MSVC 链接器参考](linking.md)
- [MSVC 链接器选项](linker-options.md)
- [`/DYNAMICBASE`](dynamicbase-use-address-space-layout-randomization.md)
- [`/LARGEADDRESSAWARE`](largeaddressaware-handle-large-addresses.md)
- [Windows ISV 软件安全防御](/previous-versions/bb430720(v=msdn.10))
