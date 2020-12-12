---
description: '了解详细信息：/ZW (Windows 运行时编译) '
title: /ZW（Windows 运行时编译）
ms.date: 04/08/2019
f1_keywords:
- VC.Project.VCCLCompilerTool.CompileAsWinRT
- /zw
helpviewer_keywords:
- /ZW
- -ZW compiler option
- /ZW compiler option
- -ZW
- Windows Runtime compiler option
ms.assetid: 0fe362b0-9526-498b-96e0-00d7a965a248
ms.openlocfilehash: b2c39cdfb3f1d22d12c8d07b1e844c550a7a0e3a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273912"
---
# <a name="zw-windows-runtime-compilation"></a>/ZW（Windows 运行时编译）

编译源代码，以支持 Microsoft c + + 组件扩展 c + +/CX 创建通用 Windows 平台 (UWP) 应用程序。

当使用 **/ZW** 进行编译时，请始终指定 **/ehsc** 。

## <a name="syntax"></a>语法

```cpp
/ZW /EHsc
/ZW:nostdlib /EHsc
```

## <a name="arguments"></a>参数

**nostdlib**<br/>
指示 Platform.winmd、Windows.Foundation.winmd 以及其他默认 Windows 元数据 (.winmd) 文件未自动包含在该编译中。 相反，必须使用 [/FU (名称强制 #using 文件) ](fu-name-forced-hash-using-file.md) 编译器选项显式指定 Windows 元数据文件。

## <a name="remarks"></a>备注

指定 **/ZW** 选项时，编译器支持以下功能：

- 您的应用程序在 Windows 运行时中执行所需的元数据文件、命名空间、数据类型和函数。

- 自动对 Windows 运行时对象的引用计数，并在对象的引用计数变为零时自动放弃该对象。

由于增量链接器不支持 .obj 文件中包含的 Windows 元数据（使用 **/ZW** 选项），因此，不推荐使用的 [/Gm (启用最小重新生成)](gm-enable-minimal-rebuild.md) 选项与 **/ZW** 不兼容。

有关详细信息，请参阅 [Visual C++ 语言参考](../../cppcx/visual-c-language-reference-c-cx.md)。

## <a name="requirements"></a>要求

## <a name="see-also"></a>另请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
