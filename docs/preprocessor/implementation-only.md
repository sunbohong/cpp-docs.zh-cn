---
description: 了解详细信息： implementation_only import 特性
title: implementation_only 导入属性
ms.date: 08/29/2019
f1_keywords:
- implementation_only
helpviewer_keywords:
- implementation_only attribute
ms.assetid: d8cabc86-4425-45a0-9587-d57536980088
ms.openlocfilehash: 8afeb9981c5931596fc500419755521a41a3d7c7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236537"
---
# <a name="implementation_only-import-attribute"></a>implementation_only 导入属性

**C++ 专用**

禁止生成 `.tlh` 主类型库头文件。

## <a name="syntax"></a>语法

> **#import** *类型-库* **implementation_only**

## <a name="remarks"></a>备注

此文件包含用于公开类型库内容的所有声明。 `.tli`将生成标头文件，并在编译中包含包装成员函数的实现。

指定此属性时，标头的内容与 `.tli` 标头中通常使用的名称相同 `.tlh` 。 此外，成员函数未声明为内联。

**Implementation_only** 特性旨在与 [no_implementation](../preprocessor/no-implementation.md)特性结合使用，以便将实现保留在预编译头 (PCH) 文件中。 将在用于创建 PCH 的源区域中放置具有 `#import` 特性的 `no_implementation` 语句。 生成的 PCH 由很多源文件使用。 `#import`然后在 PCH 区域外使用带有 **implementation_only** 特性的语句。 只需在一个源文件中使用此语句一次。 它生成所有必需的包装成员函数，而不会对每个源文件进行额外的重新编译。

> [!NOTE]
> 一个语句中的 **implementation_only** 特性 `#import` 必须与 `#import` 具有特性的同一类型库的另一条语句结合使用 `no_implementation` 。 否则，将生成编译器错误。 这是因为编译由带有属性的语句生成的包装类定义 `#import` `no_implementation` 是编译由 **implementation_only** 属性生成的实现所必需的。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
