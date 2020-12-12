---
description: 了解详细信息：编译器警告 (等级 1) C4518
title: 编译器警告（等级 1）C4518
ms.date: 11/04/2016
f1_keywords:
- C4518
helpviewer_keywords:
- C4518
ms.assetid: 4ad21004-f076-43fd-99f4-4bf1f9be4c0b
ms.openlocfilehash: 1a04dbcdc62e6758e2b65c6b0ef5aa99a1823ef0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212293"
---
# <a name="compiler-warning-level-1-c4518"></a>编译器警告（等级 1）C4518

"说明符"：存储类或类型说明符 (s 在此处意外) ：掉

下面的示例生成 C4518：

```cpp
// C4518.cpp
// compile with: /c /W1
_declspec(dllexport) extern "C" void MyFunction();   // C4518

extern "C" void MyFunction();   // OK
```
