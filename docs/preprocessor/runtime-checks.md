---
description: 详细了解 pragma Microsoft c/c + + 中的 runtime_checks 指令
title: runtime_checks pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.runtime_checks
- runtime_checks_CPP
helpviewer_keywords:
- runtime_checks pragma
- pragma, runtime_checks
no-loc:
- pragma
ms.openlocfilehash: 4932126ffe33d2f8a99f6d94e3c58d2c0322df92
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712812"
---
# <a name="runtime_checks-no-locpragma"></a>`runtime_checks` pragma

禁用或还原 [`/RTC`](../build/reference/rtc-run-time-error-checks.md) 编译器选项设置。

## <a name="syntax"></a>语法

> **`#pragma runtime_checks( "`** [ *运行时-检查选项* ] **`",`** { **`restore`** | **`off`** } **`)`**

## <a name="remarks"></a>注解

不能启用由编译器选项启用的运行时检查。 例如，如果未在 **`/RTCs`** 命令行上指定，则指定将 `#pragma runtime_checks( "s", restore)` 不会启用堆栈帧验证。

**`runtime_checks`** pragma 必须出现在函数的外部，并在看到之后在定义的第一个函数处生效 pragma 。 **`restore`** 和 **`off`** 参数打开 **`runtime_checks`** pragma 或关闭中指定的选项。

*运行时检查选项* 可以是下表中显示的零个或多个参数。

### <a name="parameters-of-the-runtime_checks-pragma"></a>runtime_checks 杂注的参数

| 参数 | 运行时检查的类型 |
|--------------------|-----------------------------|
| **`s`** | 启用堆栈（帧）验证。 |
| **`c`** | 报告何时向较小的数据类型赋值会导致数据丢失。 |
| **`u`** | 报告变量在定义之前的使用情况。 |

这些参数与编译器选项一起使用的参数相同 **`/RTC`** 。 例如：

```cpp
#pragma runtime_checks( "sc", restore )
```

使用 **`runtime_checks`** pragma 带有空字符串的 (**`""`**) 是一种特殊形式的指令：

- 使用 **`off`** 参数时，它会关闭上表中列出的运行时错误检查。

- 使用 **`restore`** 参数时，它会将运行时错误检查重置为你使用编译器选项指定的检查 **`/RTC`** 。

```cpp
#pragma runtime_checks( "", off )
/* runtime checks are off in this region */
#pragma runtime_checks( "", restore )
```

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
