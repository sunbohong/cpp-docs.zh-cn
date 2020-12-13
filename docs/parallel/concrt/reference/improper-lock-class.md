---
description: 了解详细信息： improper_lock 类
title: improper_lock 类
ms.date: 11/04/2016
f1_keywords:
- improper_lock
- CONCRT/concurrency::improper_lock
- CONCRT/concurrency::improper_lock::improper_lock
helpviewer_keywords:
- improper_lock class
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
ms.openlocfilehash: 8e29172ad171bbd3f95b3079840fb50b91dfe577
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334635"
---
# <a name="improper_lock-class"></a>improper_lock 类

此类描述错误获取锁时引发的异常。

## <a name="syntax"></a>语法

```cpp
class improper_lock : public std::exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[improper_lock](#ctor)|已重载。 构造一个 `improper_lock exception`。|

## <a name="remarks"></a>备注

通常，当尝试在同一上下文中以递归方式获取非可重入锁时，将引发此异常。

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`improper_lock`

## <a name="requirements"></a>要求

**标头：** concrt

**命名空间：** 并发

## <a name="improper_lock"></a><a name="ctor"></a> improper_lock

构造一个 `improper_lock exception`。

```cpp
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```

### <a name="parameters"></a>parameters

*_Message*<br/>
错误的描述性消息。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)<br/>
[critical_section 类](critical-section-class.md)<br/>
[reader_writer_lock 类](reader-writer-lock-class.md)
