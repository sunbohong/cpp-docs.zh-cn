---
description: 了解详细信息： Platform：： WrongThreadException 类
title: Platform::WrongThreadException 类
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::WrongThreadException
- VCCORLIB/Platform::WrongThreadException::WrongThreadException
helpviewer_keywords:
- Platform::WrongThreadException
ms.assetid: c193f97e-0392-4535-a4c4-0711e4e4a836
ms.openlocfilehash: a7fbaed7766a3928ca24d56f5233c38d9298d466
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307725"
---
# <a name="platformwrongthreadexception-class"></a>Platform::WrongThreadException 类

当线程通过不属于该线程单元的代理对象的接口指针调用时引发。

## <a name="syntax"></a>语法

```cpp
public ref class WrongThreadException : COMException,    IException,    IPrintable,    IEquatable
```

### <a name="remarks"></a>备注

有关更多信息，请参见 [COMException](../cppcx/platform-comexception-class.md)。

### <a name="requirements"></a>要求

**支持的最低客户端：** Windows 8

**支持的最低服务器：** Windows Server 2012

**命名空间：** Platform

**Metadata：** platform.string

## <a name="see-also"></a>请参阅

[Platform：： COMException 类](../cppcx/platform-comexception-class.md)
