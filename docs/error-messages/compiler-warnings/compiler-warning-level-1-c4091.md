---
title: 编译器警告 (等级 1) C4091
ms.date: 11/04/2016
f1_keywords:
- C4091
helpviewer_keywords:
- C4091
ms.assetid: 3a404967-ab42-49b0-b324-fd7ba1859d78
ms.openlocfilehash: 1a9fef0a825f98ab3ce8d935c98eefe1866be6cf
ms.sourcegitcommit: c1fd917a8c06c6504f66f66315ff352d0c046700
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/16/2020
ms.locfileid: "90684685"
---
# <a name="compiler-warning-level-1-c4091"></a>编译器警告 (等级 1) C4091

"关键字"：未声明变量时忽略 "type" 的左侧

编译器检测到用户可能打算将变量声明为，但编译器不能声明变量。

## <a name="examples"></a>示例

**`__declspec`** 用户定义类型声明的开头的特性适用于该类型的变量。 C4091 指示未声明变量。 下面的示例生成 C4091。

```cpp
// C4091.cpp
// compile with: /W1 /c
__declspec(dllimport) class X {}; // C4091

// __declspec attribute applies to varX
__declspec(dllimport) class X2 {} varX;

// __declspec attribute after the class or struct keyword
// applies to user defined type
class __declspec(dllimport) X3 {};
```

如果标识符为 typedef，则它也不能是变量名。 下面的示例生成 C4091。

```cpp
// C4091_b.cpp
// compile with: /c /W1 /WX
#define LIST 4
typedef struct _LIST {} LIST;   // C4091
```
