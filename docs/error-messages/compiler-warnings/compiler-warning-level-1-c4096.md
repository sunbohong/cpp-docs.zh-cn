---
description: 了解详细信息：编译器警告 (等级 1) C4096
title: 编译器警告 (等级 1) C4096
ms.date: 11/04/2016
f1_keywords:
- C4096
helpviewer_keywords:
- C4096
ms.assetid: abf3cca2-2f21-45d8-b025-6b513b00681e
ms.openlocfilehash: 2d787a2de5974b16fb962c17530532480d993fd6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97278033"
---
# <a name="compiler-warning-level-1-c4096"></a>编译器警告 (等级 1) C4096

"a"：接口不是 COM 接口;不会发送到 IDL

你可能打算用作 COM 接口的接口定义未定义为 COM 接口，因此不会将其发送到 IDL 文件。

请参阅表示接口是 COM 接口的列表属性的 [接口特性](../../windows/attributes/interface-attributes.md) 。

下面的示例生成 C4096：

```cpp
// C4096.cpp
// compile with: /W1 /LD
#include "windows.h"
[module(name="xx")];

// [object, uuid("00000000-0000-0000-0000-000000000001")]
__interface a
{
};

[coclass, uuid("00000000-0000-0000-0000-000000000002")]
struct b : a
{
};   // C4096, remove coclass or uncomment object
```
