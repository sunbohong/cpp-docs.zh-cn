---
description: 了解详细信息： message 类
title: message 类
ms.date: 11/04/2016
f1_keywords:
- message
- AGENTS/concurrency::message
- AGENTS/concurrency::message::message
- AGENTS/concurrency::message::add_ref
- AGENTS/concurrency::message::msg_id
- AGENTS/concurrency::message::remove_ref
- AGENTS/concurrency::message::payload
helpviewer_keywords:
- message class
ms.assetid: 3e1f3505-6c0c-486c-8191-666d0880ec62
ms.openlocfilehash: 0e15dafd9606e68f7a6ed1bed3795791c0f6870c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97202309"
---
# <a name="message-class"></a>message 类

包含正在消息块之间传递的数据负载的基本消息信封。

## <a name="syntax"></a>语法

```cpp
template<class T>
class message : public ::Concurrency::details::_Runtime_object;
```

### <a name="parameters"></a>parameters

*T*<br/>
消息内有效负载的数据类型。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|`type`|的类型别名 `T` 。|

### <a name="public-constructors"></a>公共构造函数

|“属性”|说明|
|----------|-----------------|
|[message](#ctor)|已重载。 构造 `message` 对象。|
|[~ 消息析构函数](#dtor)|销毁 `message` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[add_ref](#add_ref)|添加到对象的引用计数 `message` 。 用于需要引用计数来确定消息生存期的消息块。|
|msg_id |返回对象的 ID `message` 。|
|[remove_ref](#remove_ref)|从对象的引用计数中减去 `message` 。 用于需要引用计数来确定消息生存期的消息块。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[负载](#payload)|对象的负载 `message` 。|

## <a name="remarks"></a>备注

有关详细信息，请参阅 [异步消息块](../../../parallel/concrt/asynchronous-message-blocks.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

`message`

## <a name="requirements"></a>要求

**标头：** agents.h

**命名空间：** 并发

## <a name="add_ref"></a><a name="add_ref"></a> add_ref

添加到对象的引用计数 `message` 。 用于需要引用计数来确定消息生存期的消息块。

```cpp
long add_ref();
```

### <a name="return-value"></a>返回值

引用计数的新值。

## <a name="message"></a><a name="ctor"></a> 消息

构造 `message` 对象。

```cpp
message(
    T const& _P);

message(
    T const& _P,
    runtime_object_identity _Id);

message(
    message const& _Msg);

message(
    _In_ message const* _Msg);
```

### <a name="parameters"></a>parameters

*_P*<br/>
此消息的有效负载。

*_Id*<br/>
此消息的唯一 ID。

*_Msg*<br/>
指向对象的引用或指针 `message` 。

### <a name="remarks"></a>备注

如果参数为，则采用指向对象的指针作为参数的构造函数将 `message` 引发 [invalid_argument](../../../standard-library/invalid-argument-class.md) 异常 `_Msg` `NULL` 。

## <a name="message"></a><a name="dtor"></a> ~ 消息

销毁 `message` 对象。

```cpp
virtual ~message();
```

## <a name="msg_id"></a><a name="msg_id"></a> msg_id

返回对象的 ID `message` 。

```cpp
runtime_object_identity msg_id() const;
```

### <a name="return-value"></a>返回值

`runtime_object_identity` 对象的 `message`。

## <a name="payload"></a><a name="payload"></a> 负载

对象的负载 `message` 。

```cpp
T const payload;
```

## <a name="remove_ref"></a><a name="remove_ref"></a> remove_ref

从对象的引用计数中减去 `message` 。 用于需要引用计数来确定消息生存期的消息块。

```cpp
long remove_ref();
```

### <a name="return-value"></a>返回值

引用计数的新值。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)
