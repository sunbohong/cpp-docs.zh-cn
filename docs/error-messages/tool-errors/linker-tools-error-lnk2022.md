---
description: 了解详细信息：链接器工具错误 LNK2022
title: 链接器工具错误 LNK2022
ms.date: 11/04/2016
f1_keywords:
- LNK2022
helpviewer_keywords:
- LNK2022
ms.assetid: d2128c73-dde3-4b8e-a9b2-0a153acefb3b
ms.openlocfilehash: ed609c47e67a4719f2447f9cdff35221ef157cf8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275836"
---
# <a name="linker-tools-error-lnk2022"></a>链接器工具错误 LNK2022

> 元数据操作失败 (*HRESULT*) ： *error_message*

链接器在合并元数据时检测到错误。 必须解析元数据错误才能成功链接。

诊断此问题的一种方法是对对象文件运行 **ildasm 标记** ，以查找中列出了令牌的类型 `error_message` ，并查找不同之处。  在元数据中，具有相同名称的两个不同类型是无效的，即使 LayoutType 属性不同也是如此。

LNK2022 的一个原因是，一个类型 (如结构) 存在于具有相同名称的多个 compiland 中，但存在有冲突的定义，并且使用 [/clr](../../build/reference/clr-common-language-runtime-compilation.md)进行编译时。  在这种情况下，请确保在所有 compiland 中该类型具有相同的定义。  中列出了类型名称 `error_message` 。

LNK2022 的另一个可能原因是链接器在与 [#using](../../preprocessor/hash-using-directive-cpp.md) ) 指定给编译器 (的位置发现元数据文件不同。 确保元数据文件（.dll 或 .netmodule）在传递给链接器时与传递给编译器时位于相同的位置。

在生成 ATL 应用程序时， `_ATL_MIXED` 如果在至少一个 compiland 中使用宏，则需要使用宏。

## <a name="examples"></a>示例

下面的示例定义了一个空类型。

```cpp
// LNK2022_a.cpp
// compile with: /clr /c
public ref class Test {};
```

此示例显示不能链接两个包含同名但不同定义的类型的源代码文件。

下面的示例生成 LNK2022。

```cpp
// LNK2022_b.cpp
// compile with: LNK2022_a.cpp /clr /LD
// LNK2022 expected
public ref class Test {
   void func() {}
   int var;
};
```
