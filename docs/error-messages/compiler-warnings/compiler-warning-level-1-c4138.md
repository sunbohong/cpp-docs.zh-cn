---
description: 了解详细信息：编译器警告 (等级 1) C4138
title: 编译器警告（等级 1）C4138
ms.date: 11/04/2016
f1_keywords:
- C4138
helpviewer_keywords:
- C4138
ms.assetid: 65ebf929-bba0-4237-923b-c1b66adfe17d
ms.openlocfilehash: 68789c7300944c7435431688ff147f40cd4cadb0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278020"
---
# <a name="compiler-warning-level-1-c4138"></a>编译器警告（等级 1）C4138

在注释外找到“*/”

结束注释分隔符前面没有开始注释分隔符。 编译器假定星号 (<strong>\*</strong>) 和正斜杠 (/) 之间有一个空格。

## <a name="example"></a>示例

```cpp
// C4138a.cpp
// compile with: /W1
int */*comment*/ptr;   // C4138 Ambiguous first delimiter causes warning
int main()
{
}
```

此警告可由嵌套注释引起。

如果注释掉包含注释的代码段，在 **#if / #endif** 块中包含代码，并将控制表达式设置为零，可能会解决此警告：

```cpp
// C4138b.cpp
// compile with: /W1
#if 0
int my_variable;   /* Declaration currently not needed */
#endif
int main()
{
}
```
