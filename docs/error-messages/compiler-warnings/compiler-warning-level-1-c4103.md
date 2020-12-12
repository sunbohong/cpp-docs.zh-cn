---
description: 了解详细信息：编译器警告 (等级 1) C4103
title: 编译器警告 (等级 1) C4103
ms.date: 11/04/2016
f1_keywords:
- C4103
helpviewer_keywords:
- C4103
ms.assetid: 9021b514-375e-4d62-b261-ccb06f299e8e
ms.openlocfilehash: 98a9cfbda60ccc938f2cda7803fcdf7e996def9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272222"
---
# <a name="compiler-warning-level-1-c4103"></a>编译器警告 (等级 1) C4103

"filename"：包含标头后更改了对齐方式，可能是由于缺少 #pragma pack (pop) 

打包影响类的布局，并且通常情况下，如果在标头文件中进行封装更改，则可能会出现问题。

在退出标头文件之前，请使用 #pragma [pack](../../preprocessor/pack.md) (pop) ，以解决此警告。

下面的示例生成 C4103：

```cpp
// C4103.h
#pragma pack(push, 4)

// defintions and declarations

// uncomment the following line to resolve
// #pragma pack(pop)
```

然后，

```cpp
// C4103.cpp
// compile with: /LD /W1
#include "c4103.h"   // C4103
```
