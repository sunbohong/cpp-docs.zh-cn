---
description: 了解详细信息：控件标志
title: 控制标志
ms.date: 11/04/2016
f1_keywords:
- c.flags
helpviewer_keywords:
- flags, control
- heap allocation, control flags
- debug heap, control flags
ms.assetid: 8dbd24a5-0633-42d1-9771-776db338465f
ms.openlocfilehash: 6b49bfa49e2e231a64af8d88739778964ce8ed21
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195731"
---
# <a name="control-flags"></a>控制标志

Microsoft C 运行库的调试版本使用下列标志控制堆分配和报告过程。 有关详细信息，请参阅 [CRT 调试方法](/visualstudio/debugger/crt-debugging-techniques)。

|标志|描述|
|----------|-----------------|
|[_CRTDBG_MAP_ALLOC](../c-runtime-library/crtdbg-map-alloc.md)|将基堆函数映射到其对应的调试版本|
|[_DEBUG](../c-runtime-library/debug.md)|支持使用运行时函数的调试版本|
|[_CRTDBG_CHECK_CRT_DF](../c-runtime-library/crtdbgflag.md)|控制调试堆管理器如何跟踪分配|

这些标志可以使用 /D 命令行选项或 `#define` 指令定义。 如果标志是使用 `#define` 定义的，则指令必须在标头文件包含例程声明的语句之前显示。

## <a name="see-also"></a>请参阅

[全局变量和标准类型](../c-runtime-library/global-variables-and-standard-types.md)
