---
description: 了解更多：编译器错误 C2008
title: 编译器错误 C2008
ms.date: 11/04/2016
f1_keywords:
- C2008
helpviewer_keywords:
- C2008
ms.assetid: e748ccbe-ffd4-4008-aca7-e53c25225209
ms.openlocfilehash: 3fcde1885fd752a03a1285470a232f1daaa27df2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298521"
---
# <a name="compiler-error-c2008"></a>编译器错误 C2008

“character”: 宏定义中的意外

紧跟在宏名称之后的字符。 若要解决此错误，宏名称后必须有一个空格。

下面的示例生成 C2008：

```cpp
// C2008.cpp
#define TEST1"mytest1"    // C2008
```

可能的解决方法：

```cpp
// C2008b.cpp
// compile with: /c
#define TEST2 "mytest2"
```
