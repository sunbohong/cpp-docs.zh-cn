---
description: 了解详细信息： target_block 类
title: target_block 类
ms.date: 11/04/2016
f1_keywords:
- target_block
- AGENTS/concurrency::target_block
- AGENTS/concurrency::target_block::target_block
- AGENTS/concurrency::target_block::propagate
- AGENTS/concurrency::target_block::send
- AGENTS/concurrency::target_block::async_send
- AGENTS/concurrency::target_block::decline_incoming_messages
- AGENTS/concurrency::target_block::enable_batched_processing
- AGENTS/concurrency::target_block::initialize_target
- AGENTS/concurrency::target_block::link_source
- AGENTS/concurrency::target_block::process_input_messages
- AGENTS/concurrency::target_block::process_message
- AGENTS/concurrency::target_block::propagate_message
- AGENTS/concurrency::target_block::register_filter
- AGENTS/concurrency::target_block::remove_sources
- AGENTS/concurrency::target_block::send_message
- AGENTS/concurrency::target_block::sync_send
- AGENTS/concurrency::target_block::unlink_source
- AGENTS/concurrency::target_block::unlink_sources
- AGENTS/concurrency::target_block::wait_for_async_sends
helpviewer_keywords:
- target_block class
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
ms.openlocfilehash: 0860ff7b185eef997d7c76f61d67ad10056ca9cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188412"
---
# <a name="target_block-class"></a>target_block 类

`target_block` 类是抽象基类，它提供基本链接管理功能和针对仅限于目标的块的错误检查。

## <a name="syntax"></a>语法

```cpp
template<class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>>
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

### <a name="parameters"></a>parameters

*_SourceLinkRegistry*<br/>
用于保存源链接的链接注册表。

*_MessageProcessorType*<br/>
用于消息处理的处理器类型。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|`source_iterator`|此对象的的迭代器的类型 `source_link_manager` `target_block` 。|

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[target_block](#ctor)|构造 `target_block` 对象。|
|[~ target_block 析构函数](#dtor)|销毁 `target_block` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[传](#propagate)|将消息从源块异步传递到此目标块。|
|[send](#send)|将消息从源块同步传递到此目标块。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[async_send](#async_send)|异步发送消息以进行处理。|
|[decline_incoming_messages](#decline_incoming_messages)|向块指示应拒绝新消息。|
|[enable_batched_processing](#enable_batched_processing)|启用该块的批处理。|
|[initialize_target](#initialize_target)|初始化基对象。 具体而言， `message_processor` 需要对对象进行初始化。|
|[link_source](#link_source)|将指定的源块链接到此 `target_block` 对象。|
|[process_input_messages](#process_input_messages)|处理作为输入接收的消息。|
|[process_message](#process_message)|在派生类中重写时，处理由该 `target_block` 对象接受的消息。|
|[propagate_message](#propagate_message)|当在派生类中重写时，此方法将消息从块异步传递 `ISource` 到此 `target_block` 对象。 此 `propagate` 方法由源块调用时由方法调用。|
|[register_filter](#register_filter)|注册将对收到的每条消息调用的筛选器方法。|
|[remove_sources](#remove_sources)|等待未完成的异步发送操作完成后，断开所有源。|
|[send_message](#send_message)|当在派生类中重写时，此方法将消息从块同步传递 `ISource` 到此 `target_block` 对象。 此 `send` 方法由源块调用时由方法调用。|
|[sync_send](#sync_send)|同步发送消息以进行处理。|
|[unlink_source](#unlink_source)|从此对象断开指定的源块 `target_block` 。|
|[unlink_sources](#unlink_sources)|将所有源块与此 `target_block` 对象断开。  (重写 [ITarget：： unlink_sources](itarget-class.md#unlink_sources)。 ) |
|[wait_for_async_sends](#wait_for_async_sends)|等待所有异步传播完成。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[ITarget](itarget-class.md)

`target_block`

## <a name="requirements"></a>要求

**标头：** agents.h

**命名空间：** 并发

## <a name="async_send"></a><a name="async_send"></a> async_send

异步发送消息以进行处理。

```cpp
void async_send(_Inout_opt_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>parameters

*_PMessage*<br/>
指向正在发送的消息的指针。

## <a name="decline_incoming_messages"></a><a name="decline_incoming_messages"></a> decline_incoming_messages

向块指示应拒绝新消息。

```cpp
void decline_incoming_messages();
```

### <a name="remarks"></a>备注

此方法由析构函数调用，以确保在析构正在进行时，新消息被拒绝。

## <a name="enable_batched_processing"></a><a name="enable_batched_processing"></a> enable_batched_processing

启用该块的批处理。

```cpp
void enable_batched_processing();
```

## <a name="initialize_target"></a><a name="initialize_target"></a> initialize_target

初始化基对象。 具体而言， `message_processor` 需要对对象进行初始化。

```cpp
void initialize_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>parameters

*_PScheduler*<br/>
用于计划任务的计划程序。

*_PScheduleGroup*<br/>
用于计划任务的计划组。

## <a name="link_source"></a><a name="link_source"></a> link_source

将指定的源块链接到此 `target_block` 对象。

```cpp
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>parameters

*_PSource*<br/>
指向 `ISource` 要链接的块的指针。

### <a name="remarks"></a>备注

不应在对象上直接调用此函数 `target_block` 。 块应使用方法连接在一起 `link_target` `ISource` ，这将对 `link_source` 相应目标调用方法。

## <a name="process_input_messages"></a><a name="process_input_messages"></a> process_input_messages

处理作为输入接收的消息。

```cpp
virtual void process_input_messages(_Inout_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>parameters

*_PMessage*<br/>
指向要处理的消息的指针。

## <a name="process_message"></a><a name="process_message"></a> process_message

在派生类中重写时，处理由该 `target_block` 对象接受的消息。

```cpp
virtual void process_message(message<_Source_type> *);
```

## <a name="propagate"></a><a name="propagate"></a> 传

将消息从源块异步传递到此目标块。

```cpp
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>parameters

*_PMessage*<br/>
指向 `message` 对象的指针。

*_PSource*<br/>
指向提供消息的源块的指针。

### <a name="return-value"></a>返回值

[Message_status](concurrency-namespace-enums.md)指示目标决定对消息执行的操作。

### <a name="remarks"></a>备注

如果[](../../../standard-library/invalid-argument-class.md) `_PMessage` 或参数为，方法将引发 invalid_argument 异常 `_PSource` `NULL` 。

## <a name="propagate_message"></a><a name="propagate_message"></a> propagate_message

当在派生类中重写时，此方法将消息从块异步传递 `ISource` 到此 `target_block` 对象。 此 `propagate` 方法由源块调用时由方法调用。

```cpp
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```

### <a name="parameters"></a>parameters

*_PMessage*<br/>
指向 `message` 对象的指针。

*_PSource*<br/>
指向提供消息的源块的指针。

### <a name="return-value"></a>返回值

[Message_status](concurrency-namespace-enums.md)指示目标决定对消息执行的操作。

## <a name="register_filter"></a><a name="register_filter"></a> register_filter

注册将对收到的每条消息调用的筛选器方法。

```cpp
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>parameters

*_Filter*<br/>
筛选器方法。

## <a name="remove_sources"></a><a name="remove_sources"></a> remove_sources

等待未完成的异步发送操作完成后，断开所有源。

```cpp
void remove_sources();
```

### <a name="remarks"></a>备注

所有目标块都应调用此例程，以删除其析构函数中的源。

## <a name="send"></a><a name="send"></a> 发送

将消息从源块同步传递到此目标块。

```cpp
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>parameters

*_PMessage*<br/>
指向 `message` 对象的指针。

*_PSource*<br/>
指向提供消息的源块的指针。

### <a name="return-value"></a>返回值

[Message_status](concurrency-namespace-enums.md)指示目标决定对消息执行的操作。

### <a name="remarks"></a>备注

如果[](../../../standard-library/invalid-argument-class.md) `_PMessage` 或参数为，方法将引发 invalid_argument 异常 `_PSource` `NULL` 。

使用 `send` 消息启动外的方法和在网络内传播消息是危险的，可能会导致死锁。

当 `send` 返回时，消息已被接受，并传输到目标块中，或者被目标拒绝。

## <a name="send_message"></a><a name="send_message"></a> send_message

当在派生类中重写时，此方法将消息从块同步传递 `ISource` 到此 `target_block` 对象。 此 `send` 方法由源块调用时由方法调用。

```cpp
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>返回值

[Message_status](concurrency-namespace-enums.md)指示目标决定对消息执行的操作。

### <a name="remarks"></a>备注

默认情况下， `declined` 除非由派生类重写，否则将返回。

## <a name="sync_send"></a><a name="sync_send"></a> sync_send

同步发送消息以进行处理。

```cpp
void sync_send(_Inout_opt_ message<_Source_type>* _PMessage);
```

### <a name="parameters"></a>parameters

*_PMessage*<br/>
指向正在发送的消息的指针。

## <a name="target_block"></a><a name="ctor"></a> target_block

构造 `target_block` 对象。

```cpp
target_block();
```

## <a name="target_block"></a><a name="dtor"></a> ~ target_block

销毁 `target_block` 对象。

```cpp
virtual ~target_block();
```

## <a name="unlink_source"></a><a name="unlink_source"></a> unlink_source

从此对象断开指定的源块 `target_block` 。

```cpp
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>parameters

*_PSource*<br/>
指向要取消链接的块的指针 `ISource` 。

## <a name="unlink_sources"></a><a name="unlink_sources"></a> unlink_sources

将所有源块与此 `target_block` 对象断开。

```cpp
virtual void unlink_sources();
```

## <a name="wait_for_async_sends"></a><a name="wait_for_async_sends"></a> wait_for_async_sends

等待所有异步传播完成。

```cpp
void wait_for_async_sends();
```

### <a name="remarks"></a>备注

消息块析构函数使用此方法，以确保所有异步操作在销毁块之前都有时间完成。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)<br/>
[ITarget 类](itarget-class.md)
