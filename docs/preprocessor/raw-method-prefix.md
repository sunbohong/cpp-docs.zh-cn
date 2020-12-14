---
description: 了解详细信息： raw_method_prefix
title: raw_method_prefix
ms.date: 08/29/2019
f1_keywords:
- raw_method_prefix
helpviewer_keywords:
- raw_method_prefix attribute
ms.assetid: 71490313-af78-4bb2-b28a-eee67950d30b
ms.openlocfilehash: 9e05f70814e48a4460287e96905b543f7d76dde6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201984"
---
# <a name="raw_method_prefix"></a>raw_method_prefix

**C++ 专用**

指定不同的前缀以避免名称冲突。

## <a name="syntax"></a>语法

> **#import** *类型库* **raw_method_prefix (** "*前缀*" **)**

### <a name="parameters"></a>parameters

*作为*\
要使用的前缀。

## <a name="remarks"></a>备注

低级别属性和方法由使用 **raw_** 默认前缀命名的成员函数公开，以避免与高级错误处理成员函数发生名称冲突。

> [!NOTE]
> **Raw_method_prefix** 属性的效果在存在 [raw_interfaces_only](raw-interfaces-only.md)属性时保持不变。 在指定前缀时， **raw_method_prefix** 始终优先于 `raw_interfaces_only` 。 如果在同一语句中同时使用这两个特性 `#import` ，则使用 **raw_method_prefix** 特性指定的前缀。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
