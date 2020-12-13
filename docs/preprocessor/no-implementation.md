---
description: 了解详细信息： no_implementation import 特性
title: no_implementation 导入属性
ms.date: 08/29/2019
f1_keywords:
- no_implementation
helpviewer_keywords:
- no_implementation attribute
ms.assetid: bdc67785-e131-409c-87bc-f4d2f4abb07b
ms.openlocfilehash: 0cfd51b344847d2e5658fd4e4ec1a9f30db51fe6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333324"
---
# <a name="no_implementation-import-attribute"></a>no_implementation 导入属性

**C++ 专用**

取消了 `.tli` 标头的生成，其中包含包装成员函数的实现。

## <a name="syntax"></a>语法

> **#import** *类型-库* **no_implementation**

## <a name="remarks"></a>备注

如果指定此特性，则 `.tlh` 将在不 `#include` 包含头文件的语句的情况下生成带有公开类型库项的声明的标头 `.tli` 。

此属性与 [implementation_only](../preprocessor/implementation-only.md)结合使用。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
