---
description: 了解更多：编译器错误 C2868
title: 编译器错误 C2868
ms.date: 11/04/2016
f1_keywords:
- C2868
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
ms.openlocfilehash: c6a6368fbdfe61014a606fadce92322234e438f1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333789"
---
# <a name="compiler-error-c2868"></a>编译器错误 C2868

> "*identifier*"：非法的 using 声明语法;应为限定名

[Using 声明](../../cpp/using-declaration.md)需要 *限定名*，范围运算符 (`::`) 以标识符名称结尾的命名空间、类或枚举名称的序列。 单个范围解析运算符可用于引入全局命名空间的名称。

## <a name="example"></a>示例

下面的示例生成 C2868，并显示正确的用法：

```cpp
// C2868.cpp
class X {
public:
   int i;
};

class Y : X {
public:
   using X::i;   // OK
};

int main() {
   using X;   // C2868
}
```
