---
description: 了解详细信息： unsupported_os 类
title: unsupported_os 类
ms.date: 11/04/2016
f1_keywords:
- unsupported_os
- CONCRT/concurrency::unsupported_os
- CONCRT/concurrency::unsupported_os::unsupported_os
helpviewer_keywords:
- unsupported_os class
ms.assetid: 6fa57636-341b-4b51-84cc-261d283ff736
ms.openlocfilehash: 1f9ee74db42d2b34c1b4e24a1951d84a442224bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188087"
---
# <a name="unsupported_os-class"></a>unsupported_os 类

此类描述使用不受支持的操作系统时引发的一种异常。

## <a name="syntax"></a>语法

```cpp
class unsupported_os : public std::exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[unsupported_os](#ctor)|已重载。 构造 `unsupported_os` 对象。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`unsupported_os`

## <a name="requirements"></a>要求

**标头：** concrt

**命名空间：** 并发

## <a name="unsupported_os"></a><a name="ctor"></a> unsupported_os

构造 `unsupported_os` 对象。

### <a name="syntax"></a>语法

```cpp
explicit _CRTIMP unsupported_os(_In_z_ const char* _Message) throw();

unsupported_os() throw();
```

### <a name="parameters"></a>parameters

*_Message*<br/>
错误的描述性消息。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)
