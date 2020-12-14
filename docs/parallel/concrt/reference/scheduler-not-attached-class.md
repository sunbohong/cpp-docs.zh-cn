---
description: 了解详细信息： scheduler_not_attached 类
title: scheduler_not_attached 类
ms.date: 11/04/2016
f1_keywords:
- scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached
- CONCRT/concurrency::scheduler_not_attached::scheduler_not_attached
helpviewer_keywords:
- scheduler_not_attached class
ms.assetid: 26001970-b400-463b-be3d-8623359c399a
ms.openlocfilehash: 1d412ffecea288d4ecad1d0c2949e7444adfd913
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188854"
---
# <a name="scheduler_not_attached-class"></a>scheduler_not_attached 类

此类描述需要将计划程序附加到当前上下文以执行操作，而实际并未进行附加即执行该操作时引发的异常。

## <a name="syntax"></a>语法

```cpp
class scheduler_not_attached : public std::exception;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[scheduler_not_attached](#ctor)|已重载。 构造 `scheduler_not_attached` 对象。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`exception`

`scheduler_not_attached`

## <a name="requirements"></a>要求

**标头：** concrt

**命名空间：** 并发

## <a name="scheduler_not_attached"></a><a name="ctor"></a> scheduler_not_attached

构造 `scheduler_not_attached` 对象。

```cpp
explicit _CRTIMP scheduler_not_attached(_In_z_ const char* _Message) throw();

scheduler_not_attached() throw();
```

### <a name="parameters"></a>parameters

*_Message*<br/>
错误的描述性消息。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)<br/>
[计划程序类](scheduler-class.md)
