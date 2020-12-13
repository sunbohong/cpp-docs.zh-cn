---
description: 了解详细信息： no_smart_pointers import 特性
title: no_smart_pointers 导入属性
ms.date: 08/29/2019
f1_keywords:
- no_smart_pointers
helpviewer_keywords:
- no_smart_pointers attribute
ms.assetid: d69dd71e-08a8-4446-a3d0-a062dc29cb17
ms.openlocfilehash: cf2299668a2e1b24cdf45069766466f448ee9d66
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333273"
---
# <a name="no_smart_pointers-import-attribute"></a>no_smart_pointers 导入属性

**C++ 专用**

取消对类型库中所有接口的智能指针的创建。

## <a name="syntax"></a>语法

> **#import** *类型-库* **no_smart_pointers**

## <a name="remarks"></a>备注

默认情况下，当使用 `#import` 时，您将获得针对类型库中的所有接口的智能指针声明。 这些智能指针的类型为 [_com_ptr_t](../cpp/com-ptr-t-class.md)。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
