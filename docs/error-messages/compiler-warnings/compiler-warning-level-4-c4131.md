---
description: 详细了解：编译器警告 (级别 4) C4131
title: 编译器警告（等级 4）C4131
ms.date: 11/04/2016
f1_keywords:
- C4131
helpviewer_keywords:
- C4131
ms.assetid: 7903b3e1-454f-4be2-aa9b-230992f96a2d
ms.openlocfilehash: b4b54a38ad634b1cc0d444b0b6d5136b6a208626
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97261783"
---
# <a name="compiler-warning-level-4-c4131"></a>编译器警告（等级 4）C4131

“函数”：使用旧样式的声明符

指定的函数声明不是原型形式。

旧样式的函数声明应转换为原型形式。

下面的示例展示一个旧样式的函数声明：

```c
// C4131.c
// compile with: /W4 /c
void addrec( name, id ) // C4131 expected
char *name;
int id;
{ }
```

下面的示例展示一个原型形式：

```c
void addrec( char *name, int id )
{ }
```
