---
title: 编译器警告（等级 4）C4571
description: 记录 Microsoft c + + 编译器警告 C4571。
ms.date: 08/24/2020
f1_keywords:
- C4571
helpviewer_keywords:
- C4571
ms.assetid: 07aa17bd-b15c-4266-824c-57cc445e8edd
ms.openlocfilehash: 35f2b30a8ab7cfcc27ed7aae3aedd9bc81efacc8
ms.sourcegitcommit: efc8c32205c9d610f40597556273a64306dec15d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2020
ms.locfileid: "88898557"
---
# <a name="compiler-warning-level-4-c4571"></a>编译器警告（等级 4）C4571

> 信息： `catch(...)` 自 Visual C++ 7.1 后语义发生了变化; 不再捕获结构化异常 (SEH) 

`catch(...)`指定编译器选项时，将为每个块生成 C4571 **`/EHs`** 。

## <a name="remarks"></a>注解

指定 **`/EHs`** 编译器选项时， `catch(...)` 块不会捕获结构化异常。 例如， (除以零或 null 指针异常。 ) `catch(...)` 块仅捕获显式引发的 c + + 异常。 有关详细信息，请参阅[异常处理](../../cpp/exception-handling-in-visual-cpp.md)。

默认情况下，此警告处于关闭状态。  打开此警告以确保在编译时，不会 **`/EHs`** `catch (...)` 捕获结构化异常。 有关详细信息，请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md)。

可以通过以下方式之一来解析 C4571：

- **`/EHa`** 如果你仍希望 `catch(...)` 块捕获结构化的异常，请在中进行编译。

- 如果你不希望 `catch(...)` 块捕获结构化的异常，但仍希望使用块，请不要启用 C4571 `catch(...)` 。  你仍可以使用结构化异常处理关键字 **`__try`** （ (、和) ）捕获结构化异常 **`__except`** **`__finally`** 。  但请记住，使用进行编译时 **`/EHs`** ，只在引发 c + + 异常时调用析构函数，而不会在出现 SEH 异常时调用。

- `catch(...)`将块替换为特定 c + + 异常的 catch 块，并根据需要在 c + + 异常处理周围添加结构化异常处理 (**`__try`** 、 **`__except`** 和 **`__finally`**) 。   有关详细信息，请参阅[结构化异常处理 (C/c + +) ](../../cpp/structured-exception-handling-c-cpp.md)和[ `/EH` (异常处理模型) ](../../build/reference/eh-exception-handling-model.md)。

## <a name="example"></a>示例

下面的示例生成 C4571。

```cpp
// C4571.cpp
// compile with: /EHs /W4 /c
#pragma warning(default : 4571)
int main() {
   try {
      int i = 0, j = 1;
      j /= i;   // this will throw a SE (divide by zero)
   }
   catch(...) {}   // C4571 warning
}
```
