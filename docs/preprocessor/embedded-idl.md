---
description: 了解详细信息： embedded_idl import 特性
title: embedded_idl 导入属性
ms.date: 08/29/2019
f1_keywords:
- embedded_idl
helpviewer_keywords:
- embedded_idl attribute
ms.assetid: f1c1c2e8-3872-4172-8795-8d1288a20452
ms.openlocfilehash: a56c6e664c082db4b6eac078b7133a1ead947d3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97300588"
---
# <a name="embedded_idl-import-attribute"></a>embedded_idl 导入属性

**C++ 专用**

指定是否将类型库写入 `.tlh` 包含特性生成的代码的文件。

## <a name="syntax"></a>语法

> **#import** *类型-library* **embedded_idl** [ **(** { **"emitidl"**  |  **"no_emitidl"** } **)** ]

### <a name="parameters"></a>parameters

**emitidl**\
从 *类型库* 导入的类型信息出现在为特性化项目生成的 IDL 中。 此行为是默认行为，并且如果未指定参数，则该行为生效 `embedded_idl` 。

**"no_emitidl"**\
从 *类型库* 导入的类型信息在为特性化项目生成的 IDL 中不存在。

## <a name="example"></a>示例

```cpp
// import_embedded_idl.cpp
// compile with: /LD
#include <windows.h>
[module(name="MyLib2")];
#import "\school\bin\importlib.tlb" embedded_idl("no_emitidl")
```

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
