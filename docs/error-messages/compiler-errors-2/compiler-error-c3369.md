---
description: 了解更多：编译器错误 C3369
title: 编译器错误 C3369
ms.date: 11/04/2016
f1_keywords:
- C3369
helpviewer_keywords:
- C3369
ms.assetid: c6ceb9cb-3df9-4334-9a5c-d16db351d476
ms.openlocfilehash: 0391dbd7fe80daf93c8070253181c40fb805fa82
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97150795"
---
# <a name="compiler-error-c3369"></a>编译器错误 C3369

“模块名”: idl_module 已经定义

定义 DLL 的 [Idl_module](../../windows/attributes/idl-module.md) 使用只能在程序中出现一次。

以下示例生成 C3369:

```cpp
// C3369.cpp
// compile with: /c
[idl_module(name="name1", dllname="x.dll")]; // C3369
[idl_module(name="name1", dllname="x.dll")];
```
