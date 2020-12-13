---
description: 了解详细信息： no_namespace import 特性
title: no_namespace 导入属性
ms.date: 08/29/2019
f1_keywords:
- no_namespace
helpviewer_keywords:
- no_namespace attribute
ms.assetid: 5d81b741-a558-451b-b493-1f3b18967337
ms.openlocfilehash: e1503015f455af65a138e4e3e6843fd0516d2773
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333313"
---
# <a name="no_namespace-import-attribute"></a>no_namespace 导入属性

**C++ 专用**

指定编译器不生成命名空间名称。

## <a name="syntax"></a>语法

> **#import** *类型-库* **no_namespace**

## <a name="remarks"></a>备注

`#import` 标头文件中的类型库内容通常在命名空间中定义。 命名空间名称是在 `library` 原始 IDL 文件的语句中指定的。 如果指定了 **no_namespace** 特性，则编译器不会生成此命名空间。

如果要使用不同的命名空间名称，请改用 [rename_namespace](../preprocessor/rename-namespace.md) 特性。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
