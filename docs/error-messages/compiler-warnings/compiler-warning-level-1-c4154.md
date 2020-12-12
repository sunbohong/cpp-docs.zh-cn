---
description: 了解详细信息：编译器警告 (等级 1) C4154
title: 编译器警告 (等级 1) C4154
ms.date: 11/04/2016
f1_keywords:
- C4154
helpviewer_keywords:
- C4154
ms.assetid: 4511afeb-e893-4cc6-83b6-4c7a0477f76b
ms.openlocfilehash: 5654cae0fb11216928d265870c91ef0d9c0dd61d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267334"
---
# <a name="compiler-warning-level-1-c4154"></a>编译器警告 (等级 1) C4154

删除数组表达式;转换到提供的指针

不能 **`delete`** 对数组使用，因此编译器将数组转换为指针。

## <a name="example"></a>示例

```cpp
// C4154.cpp
// compile with: /c /W1
int main() {
   int array[ 10 ];
   delete array;   // C4154 can't delete stack object

   int *parray2 = new int [10];
   int (&array2)[10] = (int(&)[10]) parray2;
   delete [] array2;   // C4154

   // try the following line instead
   delete [] &array2;
}
```
