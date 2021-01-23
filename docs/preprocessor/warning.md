---
title: 出现 pragma
description: 详细了解 pragma Microsoft c/c + + 中的警告
ms.date: 01/22/2021
f1_keywords:
- warning_CPP
- vc-pragma.warning
helpviewer_keywords:
- pragma, warning
- push pragma warning
- pop warning pragma
- warning pragma
no-loc:
- pragma
ms.openlocfilehash: 97d48acc3c0e4651d3b05c0a6405d5c9c2031cf6
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98712838"
---
# <a name="warning-no-locpragma"></a>`warning` pragma

启用编译器警告消息的行为的选择性修改。

## <a name="syntax"></a>语法

> **`#pragma warning(`**\
> &nbsp;&nbsp;&nbsp;&nbsp;*`warning-specifier`* **`:`** *`warning-number-list`*\
> &nbsp;&nbsp;&nbsp;&nbsp;[**`;`** *`warning-specifier`* **`:`** *`warning-number-list`* ... ] **`)`**\
> **`#pragma warning( push`** [ **`,`** *n* ] **`)`**\
> **`#pragma warning( pop )`**

## <a name="remarks"></a>注解

以下警告说明符参数可用。

| 警告说明符 | 含义 |
|--|--|
| `1`, `2`, `3`, `4` | 将给定级别应用于指定的警告。 还会打开默认情况下处于关闭状态的指定警告。 |
| `default` | 将警告行为重置为其默认值。 还会打开默认情况下处于关闭状态的指定警告。 警告将在其默认存档级别生成。<br /><br /> 有关详细信息，请参阅 [默认情况下处于关闭状态的编译器警告](../preprocessor/compiler-warnings-that-are-off-by-default.md)。 |
| `disable` | 不要发出指定的警告消息。 |
| `error` | 将指定警告报告为错误。 |
| `once` | 只显示指定消息一次。 |
| `suppress` | 在堆栈上推送的当前状态 pragma ，为下一行禁用指定的警告，然后弹出警告堆栈以 pragma 重置状态。 |

下面的代码语句说明， *`warning-number-list`* 参数可以包含多个警告编号，并且 *`warning-specifier`* 可以在同一指令中指定多个参数 pragma 。

```cpp
#pragma warning( disable : 4507 34; once : 4385; error : 164 )
```

此指令在功能上等效于以下代码：

```cpp
// Disable warning messages 4507 and 4034.
#pragma warning( disable : 4507 34 )

// Issue warning C4385 only once.
#pragma warning( once : 4385 )

// Report warning C4164 as an error.
#pragma warning( error : 164 )
```

编译器将 4000 添加到 0 和 999 之间的任何警告编号。

范围4700-4999 中的警告数字与代码生成相关联。 对于这些警告，当编译器到达函数定义时生效的警告的状态对函数的其余部分保持有效。 **`warning`** pragma 在函数中使用时，只会在函数的末尾后生效，而不能更改大于4699的警告数字的状态。 下面的示例显示了的正确放置 **`warning`** pragma 以禁用代码生成警告消息，然后将其还原。

```cpp
// pragma_warning.cpp
// compile with: /W1
#pragma warning(disable:4700)
void Test() {
   int x;
   int y = x;   // no C4700 here
   #pragma warning(default:4700)   // C4700 enabled after Test ends
}

int main() {
   int x;
   int y = x;   // C4700
}
```

请注意，整个函数体中的最后一个设置 **`warning`** pragma 将对整个函数有效。

## <a name="push-and-pop"></a>推送和弹出

**`warning`** pragma 还支持以下语法，其中可选的 *n* 参数表示 (1 到 4) 的警告等级。

`#pragma warning( push [ , n ] )`

`#pragma warning( pop )`

pragma `warning( push )` 存储每个警告的当前警告状态。 pragma `warning( push, n )` 存储每个警告的当前状态，并将全局警告级别设置为 *n*。

pragma `warning( pop )` 弹出推送到堆栈上的最后一个警告状态。 对和之间的警告状态所做的任何 `push` 更改 `pop` 都将被撤消。 请看以下示例：

```cpp
#pragma warning( push )
#pragma warning( disable : 4705 )
#pragma warning( disable : 4706 )
#pragma warning( disable : 4707 )
// Some code
#pragma warning( pop )
```

在此代码的末尾，将 `pop` 每个警告 (的状态还原为4705、4706和 4707) 到代码开头的内容。

当你编写标头文件时，你可以使用 `push` 和 `pop` 来确保用户所做的警告状态更改不会阻止标头正确编译。 `push`在标头的开头和结尾使用 `pop` 。 例如，你可能有一个标头不会在警告级别4完全编译。 以下代码会将警告等级更改为3，然后在标头的末尾还原原始警告等级。

```cpp
#pragma warning( push, 3 )
// Declarations/definitions
#pragma warning( pop )
```

有关可帮助您禁止显示警告的编译器选项的详细信息，请参阅 [`/FI`](../build/reference/fi-name-forced-include-file.md) 和 [`/w`](../build/reference/compiler-option-warning-level.md) 。

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
