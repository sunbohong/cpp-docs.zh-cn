---
description: 了解详细信息： high_property_prefixes import 特性
title: high_property_prefixes 导入属性
ms.date: 08/29/2019
f1_keywords:
- high_property_prefixes
helpviewer_keywords:
- high_property_prefixes attribute
ms.assetid: 91c6cc2b-19b6-4aba-8831-d9e5cccb58b5
ms.openlocfilehash: af6835f5835c23dceadbb5152e36b0dabcbb8c98
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167469"
---
# <a name="high_property_prefixes-import-attribute"></a>high_property_prefixes 导入属性

**C++ 专用**

指定用于三个属性方法的备用前缀。

## <a name="syntax"></a>语法

> **#import** *类型库* **high_property_prefixes (** "*GetPrefix*" **、** "*PutPrefix*" **、** "*PutRefPrefix*" **)**

### <a name="parameters"></a>parameters

*GetPrefix*\
要用于方法的前缀 `propget` 。

*PutPrefix*\
要用于方法的前缀 `propput` 。

*PutRefPrefix*\
要用于方法的前缀 `propputref` 。

## <a name="remarks"></a>备注

默认情况下，高级错误处理 `propget` 、 `propput` 和 `propputref` 方法由名为前缀、和的成员函数公开 `Get` `Put` `PutRef` 。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
