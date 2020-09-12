---
title: '/Zc：预处理器 (启用预处理器一致性模式) '
description: 使用/Zc：预处理器编译器选项来启用对标准相容预处理器的编译器支持。
ms.date: 09/10/2020
f1_keywords:
- preprocessor
- /Zc:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /Zc:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: 356434e4892966b9a9304021dd5d8770dcc2f8b1
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90043172"
---
# <a name="zcpreprocessor-enable-preprocessor-conformance-mode"></a>`/Zc:preprocessor` (启用预处理器一致性模式) 

此选项可启用符合 C99 和 c + + 11 及更高版本标准的基于令牌的预处理器。 有关详细信息，请参阅 [MSVC new 预处理器概述](../../preprocessor/preprocessor-experimental-overview.md)。

## <a name="syntax"></a>语法

> **`/Zc:preprocessor`**[**-**]

## <a name="remarks"></a>备注

使用 **`/Zc:preprocessor`** 编译器选项启用相容预处理器。 您可以使用 **`/Zc:preprocessor-`** 选项显式指定传统 (不符合) 预处理器。

**`/Zc:preprocessor`** 从 Visual Studio 2019 版本16.5 开始，可以使用选项。 Visual Studio 2017 版本15.8 中的 Visual Studio 版本中提供了之前的、不完整的新预处理器选项版本。 有关详细信息，请参阅 [`/experimental:preprocessor`](experimental-preprocessor.md)。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. 修改 " **附加选项** " 属性以包含 *`/Zc:preprocessor`* ，然后选择 **"确定"**。

## <a name="see-also"></a>另请参阅

[/Zc（一致性）](zc-conformance.md)
