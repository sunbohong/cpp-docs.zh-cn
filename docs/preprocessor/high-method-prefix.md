---
description: 了解详细信息： high_method_prefix import 特性
title: high_method_prefix 导入属性
ms.date: 08/29/2019
f1_keywords:
- high_method_prefix
helpviewer_keywords:
- high_method_prefix attribute
ms.assetid: cacebf09-12f5-4919-ad40-939e206e340c
ms.openlocfilehash: 0ebf73892ad1ea544f3deee726695bb8e209cb2c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167482"
---
# <a name="high_method_prefix-import-attribute"></a>high_method_prefix 导入属性

**C++ 专用**

指定用于命名高级属性和方法的前缀。

## <a name="syntax"></a>语法

> **#import** *类型库* **high_method_prefix (** "*前缀*" **)**

### <a name="parameters"></a>parameters

*作为*\
要使用的前缀。

## <a name="remarks"></a>备注

默认情况下，由未使用前缀命名的成员函数公开高级错误处理属性和方法。 这些名称来自类型库。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
