---
description: 详细了解：编译器警告 (级别 4) C4125
title: 编译器警告（等级 4）C4125
ms.date: 11/04/2016
f1_keywords:
- C4125
helpviewer_keywords:
- C4125
ms.assetid: a081d1f4-0789-4915-91df-7ff0b28ca245
ms.openlocfilehash: 82c94743e2ff52efacdf1b5f139bc4d9d40d0eed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261913"
---
# <a name="compiler-warning-level-4-c4125"></a>编译器警告（等级 4）C4125

十进制数字终止八进制转义序列

编译器未用十进制数求八进制数，并假定十进制数字是一个字符。

## <a name="example"></a>示例

```cpp
// C4125a.cpp
// compile with: /W4
char array1[] = "\709"; // C4125
int main()
{
}
```

如果数字 9 作为一个字符，请如下更正示例：

```cpp
// C4125b.cpp
// compile with: /W4
char array[] = "\0709";  // C4125 String containing "89"
int main()
{
}
```
