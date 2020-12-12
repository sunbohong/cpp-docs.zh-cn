---
description: '了解详细信息：/PROFILE (性能工具探查器) '
title: /PROFILE（性能工具分析器）
ms.date: 11/04/2016
f1_keywords:
- VC.Project.VCLinkerTool.Profile
helpviewer_keywords:
- -PROFILE linker option
- /PROFILE linker option
ms.assetid: e676baa1-5063-47a3-a357-ba0d1f0d1699
ms.openlocfilehash: fb9310bb782a4b321113155f01db2228e3a46e15
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225786"
---
# <a name="profile-performance-tools-profiler"></a>/PROFILE（性能工具分析器）

生成一个可与“性能工具”探查器结合使用的输出文件。

## <a name="syntax"></a>语法

```
/PROFILE
```

## <a name="remarks"></a>备注

/PROFILE 表示以下链接器选项：

- [/OPT： REF](opt-optimizations.md)

- /OPT： NOICF

- [/INCREMENTAL：否](incremental-link-incrementally.md)

- [/FIXED：否](fixed-fixed-base-address.md)

/PROFILE 导致链接器生成程序映像中的重定位部分。  使用重定位节，探查器可以转换程序图像以获取配置文件数据。

**/PROFILE** 仅适用于企业 (团队开发) 版本。  有关 PREfast 的详细信息，请参阅 [C/c + + 代码分析概述](../../code-quality/code-analysis-for-c-cpp-overview.md)。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 展开“配置属性”节点。

1. 展开“链接器”节点。

1. 选择“高级”属性页。

1. 修改 **配置文件** 属性。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

1. 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.Profile%2A>。

### <a name="to-set-this-linker-option-within-visual-studio-cmake-project"></a>在 Visual Studio CMake 项目中设置此链接器选项

**CMake** 项目不具有 **属性页**，则可以通过将 CMakeLists.txt 正在修改设置链接器选项。

1. 打开项目根目录中的 CMakeLists.txt。

1. 添加以下代码。 有关详细信息，请参阅 [CMake 引用](https://cmake.org/cmake/help/v3.0/command/set_target_properties.html)

1. 重新生成解决方案。

```
SET_TARGET_PROPERTIES(${PROJECT_NAME} PROPERTIES LINK_FLAGS "/PROFILE")
```

## <a name="see-also"></a>另请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
