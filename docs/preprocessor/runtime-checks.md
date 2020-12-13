---
description: 了解详细信息： runtime_checks 杂注
title: runtime_checks 杂注
ms.date: 08/29/2019
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
helpviewer_keywords:
- runtime_checks pragma
- pragmas, runtime_checks
ms.assetid: ae50b43f-f88d-47ad-a2db-3389e9e7df5b
ms.openlocfilehash: 2ee04751e9cc978487670314675d3fa4ae52bd3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342291"
---
# <a name="runtime_checks-pragma"></a>runtime_checks 杂注

禁用或还原 [/RTC](../build/reference/rtc-run-time-error-checks.md) 设置。

## <a name="syntax"></a>语法

> **#pragma runtime_checks ( "** [ *runtime_checks* ] **"，** { **restore**  |  **off** } **)**

## <a name="remarks"></a>备注

不能启用由编译器选项启用的运行时检查。 例如，如果未在 `/RTCs` 命令行上指定，则指定将 `#pragma runtime_checks( "s", restore)` 不会启用堆栈帧验证。

**Runtime_checks** 杂注必须出现在函数的外部，并在出现杂注后定义的第一个函数处生效。 **restore** 和 **off** 参数打开或关闭 **runtime_checks** 中指定的选项。

**runtime_checks** 可以为下表中显示的零个或多个参数。

### <a name="parameters-of-the-runtime_checks-pragma"></a>runtime_checks 杂注的参数

| 参数 | 运行时检查的类型 |
|--------------------|-----------------------------|
| **s** | 启用堆栈（帧）验证。 |
| **c** | 报告何时向较小的数据类型赋值会导致数据丢失。 |
| **u** | 报告变量在定义之前的使用情况。 |

这些参数与编译器选项一起使用的参数相同 `/RTC` 。 例如：

```cpp
#pragma runtime_checks( "sc", restore )
```

将 **runtime_checks** 杂注和空字符串 (**""**) 一起使用是该指令的特殊形式：

- 当使用 **off** 参数时，它将关闭上表中列出的运行时错误检查。

- 使用 **restore** 参数时，它会将运行时错误检查重置为你使用编译器选项指定的检查 `/RTC` 。

```cpp
#pragma runtime_checks( "", off )
/* runtime checks are off in this region */
#pragma runtime_checks( "", restore )
```

## <a name="see-also"></a>请参阅

[Pragma 指令和 __pragma 关键字](../preprocessor/pragma-directives-and-the-pragma-keyword.md)
