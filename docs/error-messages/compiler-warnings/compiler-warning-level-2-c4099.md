---
description: 详细了解：编译器警告 (等级 2) C4099
title: 编译器警告 (等级 2) C4099
ms.date: 11/04/2016
f1_keywords:
- C4099
helpviewer_keywords:
- C4099
ms.assetid: 00bb803d-cae7-4ab8-8969-b46f54139ac8
ms.openlocfilehash: c35ce10560ca81f9457f6a21c4c55d96996e7645
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97326512"
---
# <a name="compiler-warning-level-2-c4099"></a>编译器警告 (等级 2) C4099

"identifier"：首次使用 "objecttype1" 查看的类型名称，现在使用 "objecttype2"

声明为结构的对象被定义为类，或者声明为类的对象定义为结构。 编译器使用定义中给定的类型。

## <a name="example"></a>示例

下面的示例生成 C4099。

```cpp
// C4099.cpp
// compile with: /W2 /c
struct A;
class A {};   // C4099, use different identifer or use same object type
```
