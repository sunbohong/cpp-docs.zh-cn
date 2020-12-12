---
description: 了解详细信息：数学错误 M6111
title: 数学错误 M6111
ms.date: 11/04/2016
f1_keywords:
- M6111
helpviewer_keywords:
- M6111
ms.assetid: c0fc13f8-33c8-4e3f-a440-126cc623441b
ms.openlocfilehash: 9bf2d620a0df18752b74aaacd4d2415510407f0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244337"
---
# <a name="math-error-m6111"></a>数学错误 M6111

堆栈下溢

浮点运算导致8087/287/387 协处理器或模拟器上出现堆栈下溢。

此错误通常是由对不返回值的函数的调用导致的 **`long double`** 。 例如，以下编译和运行时，将生成此错误：

```
long double ld() {};
main ()
{
  ld();
}
```

程序终止，退出代码为139。
