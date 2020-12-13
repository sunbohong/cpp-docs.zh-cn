---
description: 了解详细信息：编译器警告 (等级 1) C4612
title: 编译器警告（等级 1）C4612
ms.date: 08/27/2018
f1_keywords:
- C4612
helpviewer_keywords:
- C4612
ms.assetid: 21ac02b2-51cd-4aff-9b70-d543511d5962
ms.openlocfilehash: 2844b54c592f5c4c4817cfec97d57c41fa2055b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341719"
---
# <a name="compiler-warning-level-1-c4612"></a>编译器警告（等级 1）C4612

> 包含文件名中有错误

## <a name="remarks"></a>备注

当文件名不正确或缺失时，此警告与 **#pragma include_alias** 一起出现。

**#Pragma include_alias** 语句的参数可使用引号形式 ( "*filename*" ) 或尖括号形式 (\<*filename*>) ，但两者必须使用相同的形式。

## <a name="example"></a>示例

```cpp
// C4612.cpp
// compile with: /W1 /LD
#pragma include_alias("StandardIO", <stdio.h>) // C4612
```
