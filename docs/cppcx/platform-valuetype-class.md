---
description: 详细了解： Platform：： ValueType 类
title: Platform::ValueType 类
ms.date: 02/03/2017
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::ValueType::ToString
helpviewer_keywords:
- Platform::ValueType Class
ms.assetid: 79aa8754-b140-4974-a5b1-be046938a10a
ms.openlocfilehash: e6873b4b884586d06dae6e2fd1966041fd49bcc8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307803"
---
# <a name="platformvaluetype-class"></a>Platform::ValueType 类

值类型实例的基类。

## <a name="syntax"></a>语法

```cpp
public ref class ValueType : Object
```

## <a name="public-methods"></a>公共方法

| 名称 | 描述 |
|--|--|
| [ValueType：： ToString](#tostring) | 返回对象的字符串表示形式。 继承自 [Platform：： Object](../cppcx/platform-object-class.md)。 |

### <a name="remarks"></a>备注

ValueType 类用于构造值类型。 ValueType 派生自有基本成员的 Object。 但是，编译器会将这些基本成员与从 ValueType 类派生的值类型分离。 值类型进行装箱时，编译器会重新附加这些基本成员。

### <a name="requirements"></a>要求

**支持的最低客户端：** Windows 8

**支持的最低服务器：** Windows Server 2012

**命名空间：** Platform

**Metadata：** platform.string

## <a name="valuetypetostring-method"></a><a name="tostring"></a> ValueType：： ToString 方法

返回对象的字符串表示形式。

### <a name="syntax"></a>语法

```cpp
Platform::String ToString();
```

### <a name="return-value"></a>返回值

一个表示值的 Platform：： String。

## <a name="see-also"></a>请参阅

[Platform 命名空间](../cppcx/platform-namespace-c-cx.md)
