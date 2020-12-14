---
description: 详细了解：编译器警告 (级别 4) C4210
title: 编译器警告（等级 4）C4210
ms.date: 11/04/2016
f1_keywords:
- C4210
helpviewer_keywords:
- C4210
ms.assetid: f8600adf-dfe2-4022-a37a-3d4997641dfd
ms.openlocfilehash: aeb64e1f07f82ce1779c58bbacf3b0576642f343
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314758"
---
# <a name="compiler-warning-level-4-c4210"></a>编译器警告（等级 4）C4210

使用了非标准扩展：函数给定文件范围

使用默认的 Microsoft 扩展 ([/ze](../../build/reference/za-ze-disable-language-extensions.md)) 时，函数声明具有文件范围。

```c
// C4210.c
// compile with: /W4 /c
void func1()
{
   extern int func2( double );   // C4210 expected
}

int main()
{
   func2( 4 );   //  /Ze passes 4 as type double
}                //  /Za passes 4 as type int
```

此扩展会阻止你的代码移植到其他编译器。
