---
title: '/experimental：预处理器 (启用预处理器一致性模式) '
description: 使用/experimental：预处理器编译器选项启用标准相容预处理器的实验性编译器支持。
ms.date: 09/10/2020
f1_keywords:
- preprocessor
- /experimental:preprocessor
helpviewer_keywords:
- preprocessor conformance
- /experimental:preprocessor
- Enable preprocessor conformance mode
ms.openlocfilehash: 9a98289434e7154d2ec8b8753d990876a8218acf
ms.sourcegitcommit: 6280a4c629de0f638ebc2edd446de2a9b11f0406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2020
ms.locfileid: "90042090"
---
# <a name="experimentalpreprocessor-enable-preprocessor-conformance-mode"></a>`/experimental:preprocessor` (启用预处理器一致性模式) 

此选项在 Visual Studio 2019 版本16.5 中开始过时，并由 [`/Zc:preprocessor`](zc-preprocessor.md) 编译器选项替换。 **`/experimental:preprocessor`** 启用与 c + + 11 标准（包括 C99 预处理器功能）更为严格的试验性的基于令牌的预处理器。 有关详细信息，请参阅 [MSVC new 预处理器概述](../../preprocessor/preprocessor-experimental-overview.md)。

## <a name="syntax"></a>语法

> **`/experimental:preprocessor`**\[**`-`**]

## <a name="remarks"></a>备注

使用 **`/experimental:preprocessor`** 编译器选项启用试验性一致的预处理器。 可以使用 **`/experimental:preprocessor-`** 选项显式指定传统预处理器。

**`/experimental:preprocessor`** 从 Visual Studio 2017 版本15.8 开始，可以使用选项。 从 Visual Studio 2019 版本16.5 开始，新的预处理器完成，并在 [`/Zc:preprocessor`](zc-preprocessor.md) 编译器选项下可用。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 选择 "**配置属性**" "  >  **c/c + +**  >  **命令行**" 属性页。

1. 修改 " **附加选项** " 属性以包含 *`/experimental:preprocessor`* ，然后选择 **"确定"**。

## <a name="see-also"></a>另请参阅

[/Zc（一致性）](zc-conformance.md)
