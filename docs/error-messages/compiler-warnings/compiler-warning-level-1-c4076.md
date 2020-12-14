---
description: 了解详细信息：编译器警告 (等级 1) C4076
title: 编译器警告（等级 1）C4076
ms.date: 11/04/2016
f1_keywords:
- C4076
helpviewer_keywords:
- C4076
ms.assetid: 04581066-313a-4a11-bb60-721e6d038d75
ms.openlocfilehash: 0bae49d3af23e499851fbf70fb24fdeb817ee03c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198253"
---
# <a name="compiler-warning-level-1-c4076"></a>编译器警告（等级 1）C4076

> "*type 修饰符*"：不能与 "*typename*" 类型一起使用

## <a name="remarks"></a>备注

类型修饰符（无论是 **`signed`** 还是 **`unsigned`** ）不能用于非整数类型。 已忽略 *type 修饰符*。

## <a name="example"></a>示例

下面的示例生成 C4076;若要修复此问题，请删除 **`unsigned`** type 修饰符：

```cpp
// C4076.cpp
// compile with: /W1 /LD
unsigned double x;   // C4076
```
