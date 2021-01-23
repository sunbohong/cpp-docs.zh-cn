---
description: 了解详细信息：优化 pragma
title: 平台 pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.optimize
- optimize_CPP
helpviewer_keywords:
- pragma, optimize
- optimize pragma
no-loc:
- pragma
ms.openlocfilehash: d9044788d0eea394867622d0f7aea1e365ad3399
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713449"
---
# <a name="optimize-no-locpragma"></a>`optimize` pragma

指定逐函数的优化。

## <a name="syntax"></a>语法

> **`#pragma optimize( "`** [ *优化-列表* ] **`",`** { **`on`** | **`off`** } **`)`**

## <a name="remarks"></a>注解

**`optimize`** pragma 必须出现在函数之外。 它在显示后在定义的第一个函数处生效 pragma 。 **`on`** 和 **`off`** 参数打开或关闭 *优化列表* 中指定的选项。

*优化列表* 可以是下表中显示的零个或多个参数。

### <a name="parameters-of-the-optimize-pragma"></a>optimize 杂注的参数

| 参数 | 优化的类型 |
|--------------------|--------------------------|
| **`g`** | 启用全局优化。 |
| **`s`** 或 **`t`** | 指定机器代码的短或快速序列。 |
| **`y`** | 在程序堆栈上生成帧指针。 |

这些参数与编译器选项一起使用的字母相同 [`/O`](../build/reference/o-options-optimize-code.md) 。 例如，以下 pragma 等效于 **`/Os`** 编译器选项：

```cpp
#pragma optimize( "s", on )
```

使用 **`optimize`** pragma 带有空字符串的 (**`""`**) 是一种特殊形式的指令：

使用 **`off`** 参数时，它将启用所有优化、、 **`g`** **`s`** 、 **`t`** 和 **`y`** 。

使用 **`on`** 参数时，它会将优化重置为使用编译器选项指定的优化 [`/O`](../build/reference/o-options-optimize-code.md) 。

```cpp
#pragma optimize( "", off )
/* unoptimized code section */
#pragma optimize( "", on )
```

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
