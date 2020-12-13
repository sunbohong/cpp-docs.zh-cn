---
description: 了解详细信息： raw_property_prefixes import 特性
title: raw_property_prefixes 导入属性
ms.date: 08/29/2019
f1_keywords:
- raw_property_prefixes
helpviewer_keywords:
- raw_property_prefixes attribute
ms.assetid: 03a0f48c-c460-4175-a762-9f7f8d84b12f
ms.openlocfilehash: 7289f9aeba249249ecf78ffb3ad3b32669ac9fe3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142709"
---
# <a name="raw_property_prefixes-import-attribute"></a>raw_property_prefixes 导入属性

**C++ 专用**

指定用于三个属性方法的备用前缀。

## <a name="syntax"></a>语法

> **#import** *类型库* **raw_property_prefixes (** "*GetPrefix*" **、** "*PutPrefix*" **、** "*PutRefPrefix*" **)**

### <a name="parameters"></a>parameters

*GetPrefix*\
用于方法的前缀 `propget` 。

*PutPrefix*\
用于方法的前缀 `propput` 。

*PutRefPrefix*\
用于方法的前缀 `propputref` 。

## <a name="remarks"></a>备注

默认情况下，低级别 `propget` 、 `propput` 和 `propputref` 方法通过分别使用、和的前缀进行命名的成员函数公开 `get_` `put_` `putref_` 。 这些前缀与在 MIDL 生成的标头文件中使用的名称兼容。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
