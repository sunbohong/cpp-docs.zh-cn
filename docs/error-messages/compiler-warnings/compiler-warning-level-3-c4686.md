---
title: 编译器警告（等级 3）C4686
description: Microsoft c + + 编译器警告 C4686。
ms.date: 08/29/2020
f1_keywords:
- C4686
helpviewer_keywords:
- C4686
ms.assetid: 767c83c2-9e4b-4f9e-88c8-02128ba563f4
ms.openlocfilehash: 6886ae7f413de630457b53e85b5cd75c4542ee19
ms.sourcegitcommit: 3628707bc17c99aac7aac27eb126cc2eaa4d07b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "89194492"
---
# <a name="compiler-warning-level-3-c4686"></a>编译器警告（等级 3）C4686

> "*用户定义类型*"：行为可能有更改，UDT 中的更改返回调用约定

## <a name="remarks"></a>备注

在返回类型中使用类模板专用化之前，未对其进行定义。 实例化类的任何内容都解析 C4686;声明实例或访问成员 (例如， `C<int>::some_member`) 也是选项。

默认情况下，此警告处于关闭状态。 有关详细信息，请参阅 [默认情况下处于关闭状态的编译器警告](../../preprocessor/compiler-warnings-that-are-off-by-default.md)。

## <a name="example"></a>示例

改为尝试以下操作：

```cpp
// C4686.cpp
// compile with: /W3
#pragma warning (default : 4686)
template <class T>
class C;

template <class T>
C<T> f(T);

template <class T>
class C {};

int main() {
   f(1);   // C4686
}

template <class T>
C<T> f(T) {
   return C<int>();
}
```
