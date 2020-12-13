---
description: 了解详细信息： raw_interfaces_only import 特性
title: raw_interfaces_only 导入属性
ms.date: 08/29/2019
f1_keywords:
- raw_interfaces_only
helpviewer_keywords:
- raw_interfaces_only attribute
ms.assetid: 87056c6d-3f34-4248-af58-f5775a35bfb7
ms.openlocfilehash: f043bef5cde0454ce9f08f45efb0417aa7fdbb2d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142735"
---
# <a name="raw_interfaces_only-import-attribute"></a>raw_interfaces_only 导入属性

**C++ 专用**

禁止生成错误处理包装函数，以及使用这些包装函数的 [属性](../cpp/property-cpp.md) 声明。

## <a name="syntax"></a>语法

> **#import** *类型-库* **raw_interfaces_only**

## <a name="remarks"></a>备注

**Raw_interfaces_only** 特性还会导致删除命名非属性函数时使用的默认前缀。 通常，前缀是 `raw_` 。 如果指定此特性，则将从类型库中直接获取函数名称。

利用此特性，您可以只公开类型库的低级别内容。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
