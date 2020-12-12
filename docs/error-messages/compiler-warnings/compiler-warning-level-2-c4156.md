---
description: 详细了解：编译器警告 (等级 2) C4156
title: 编译器警告 (等级 2) C4156
ms.date: 11/04/2016
f1_keywords:
- C4156
helpviewer_keywords:
- C4156
ms.assetid: 9adf3acb-c0fe-42a8-a4db-5822b1493f77
ms.openlocfilehash: 243652ec191e315d7ad06a571c78a1dedce0f032
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326486"
---
# <a name="compiler-warning-level-2-c4156"></a>编译器警告 (等级 2) C4156

未使用数组形式的 "delete" 删除数组表达式;替换数组形式

的非数组形式 **`delete`** 无法删除数组。 编译器已转换 **`delete`** 为数组形式。

只有 Microsoft extension (/Ze) 下才会出现此警告。

## <a name="example"></a>示例

```cpp
// C4156.cpp
// compile with: /W2
int main()
{
   int (*array)[ 10 ] = new int[ 5 ][ 10 ];
   delete array; // C4156, changed by compiler to "delete [] array;"
}
```
