---
description: 了解详细信息： raw_native_types import 特性
title: raw_native_types 导入属性
ms.date: 08/29/2019
f1_keywords:
- raw_native_types
helpviewer_keywords:
- raw_native_types attribute
ms.assetid: 9f38daa8-8dc0-46a5-aff9-f1ff9c1e6f48
ms.openlocfilehash: 64eaadcbb3d9f07d47dd4a33bc16a222cae50f38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240528"
---
# <a name="raw_native_types-import-attribute"></a>raw_native_types 导入属性

**C++ 专用**

禁用高级别包装函数中的 COM 支持类，并强制改用低级别的数据类型。

## <a name="syntax"></a>语法

> **#import** *类型-库* **raw_native_types**

## <a name="remarks"></a>备注

默认情况下，高级错误处理方法使用 COM 支持类 [_bstr_t](../cpp/bstr-t-class.md) 和 [_variant_t](../cpp/variant-t-class.md) 来代替 `BSTR` 和 `VARIANT` 数据类型和原始 COM 接口指针。 这些类封装了为这些数据类型分配和解除分配内存存储的详细信息，并大大简化了类型强制转换和转换操作。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
