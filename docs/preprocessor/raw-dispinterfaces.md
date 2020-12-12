---
description: 了解详细信息： raw_dispinterfaces import 特性
title: raw_dispinterfaces 导入属性
ms.date: 08/29/2019
f1_keywords:
- raw_dispinterfaces
helpviewer_keywords:
- raw_dispinterfaces attribute
ms.assetid: f762864d-29bf-445b-825a-ba7b29a95409
ms.openlocfilehash: 447f76bdee16d2719c02ad4a73883f8f176f2584
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202010"
---
# <a name="raw_dispinterfaces-import-attribute"></a>raw_dispinterfaces 导入属性

**C++ 专用**

通知编译器为调度接口方法生成低级别包装函数，并通知调用 `IDispatch::Invoke` 并返回 HRESULT 错误代码的属性。

## <a name="syntax"></a>语法

> **#import** *类型-库* **raw_dispinterfaces**

## <a name="remarks"></a>备注

如果未指定此特性，则仅生成高级包装，这会在失败时引发 c + + 异常。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
