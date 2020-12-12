---
description: '详细了解： (C/c + + #undef 指令) '
title: '#undef 指令 (C/C++)'
ms.date: 08/29/2019
f1_keywords:
- '#undef'
helpviewer_keywords:
- '#undef directive'
- undef directive (#undef)
- preprocessor, directives
ms.assetid: 88900e0e-2c19-4a63-b681-f3d3133c24ca
ms.openlocfilehash: 20dfd1d0b26f18a26e7ad407704d6cb0ffd563bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300423"
---
# <a name="undef-directive-cc"></a> (C/c + + 的 #undef 指令) 

移除（取消定义）之前使用 `#define` 创建的名称。

## <a name="syntax"></a>语法

> **#undef** *标识符*

## <a name="remarks"></a>备注

**#Undef** 指令删除当前的 *标识符* 定义。 因此，预处理器将忽略以后出现的 *标识符* 。 若要使用 **#undef** 删除宏定义，请仅指定宏 *标识符*，而不是参数列表。

还可以将 **#undef** 指令应用于没有先前定义的标识符。 这将确保该标识符是不确定的。 不在 **#undef** 语句内执行宏替换。

**#Undef** 指令通常与 `#define` 指令配对，以在源程序中创建区域，其中标识符具有特殊意义。 例如，源程序的特定函数可使用清单常量定义不会影响程序的其余部分的环境特定值。 **#Undef** 指令还适用于 `#if` 控制源程序的条件编译的指令。 有关详细信息，请参阅 [#if、#elif、#else 和 #endif 指令](../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md)。

在下面的示例中， **#undef** 指令删除符号常量和宏的定义。 请注意，只给定宏的标识符。

```C
#define WIDTH 80
#define ADD( X, Y ) ((X) + (Y))
.
.
.
#undef WIDTH
#undef ADD
```

**Microsoft 专用**

宏可以从命令行中使用选项进行定义 `/U` ，后跟要定义的宏名称。 发出此命令的效果等效于 `#undef` 文件开头的 *宏名* 语句序列。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[预处理器指令](../preprocessor/preprocessor-directives.md)
