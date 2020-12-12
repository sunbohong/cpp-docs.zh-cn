---
description: 了解详细信息： Platform：： AccessDeniedException 类
title: Platform::AccessDeniedException 类
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::AccessDeniedException
- VCCORLIB/Platform::AccessDeniedException::AccessDeniedException
helpviewer_keywords:
- Platform::AccessDeniedException
ms.assetid: 6ae2155b-7b16-4587-8d2d-da05eab4c7e9
ms.openlocfilehash: 2dd1e543093000521bceb0abed128a1dac27a6e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97276784"
---
# <a name="platformaccessdeniedexception-class"></a>Platform::AccessDeniedException 类

被拒绝访问资源或功能时引发。

## <a name="syntax"></a>语法

```cpp
public ref class AccessDeniedException : COMException,    IException,    IPrintable,   IEquatable
```

### <a name="remarks"></a>备注

如果碰到此异常，请确保已请求适当的功能，并在您的应用程序的包清单中做了必需的声明。 有关更多信息，请参见 [COMException](../cppcx/platform-comexception-class.md) 类。

### <a name="requirements"></a>要求

**支持的最低客户端：** Windows 8

**支持的最低服务器：** Windows Server 2012

**命名空间：** Platform

**Metadata：** platform.string

## <a name="see-also"></a>请参阅

[Platform：： COMException 类](../cppcx/platform-comexception-class.md)
