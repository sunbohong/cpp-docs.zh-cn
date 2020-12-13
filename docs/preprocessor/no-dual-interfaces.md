---
description: 了解详细信息： no_dual_interfaces import 特性
title: no_dual_interfaces 导入属性
ms.date: 08/29/2019
f1_keywords:
- no_dual_interfaces
helpviewer_keywords:
- no_dual_interfaces attribute
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
ms.openlocfilehash: 1c3010b252ac71e38312fa193520938fbb4d681a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97333338"
---
# <a name="no_dual_interfaces-import-attribute"></a>no_dual_interfaces 导入属性

**C++ 专用**

更改编译器为双重接口方法生成包装器函数的方式。

## <a name="syntax"></a>语法

> **#import** *类型-库* **no_dual_interfaces**

## <a name="remarks"></a>备注

通常，包装器通过接口的虚拟函数表调用方法。 在 **no_dual_interfaces** 中，包装器改 `IDispatch::Invoke` 为调用以调用方法。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
