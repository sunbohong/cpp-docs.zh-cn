---
description: 了解详细信息： propagator_block 类
title: propagator_block 类
ms.date: 11/04/2016
f1_keywords:
- propagator_block
- AGENTS/concurrency::propagator_block
- AGENTS/concurrency::propagator_block::propagator_block
- AGENTS/concurrency::propagator_block::propagate
- AGENTS/concurrency::propagator_block::send
- AGENTS/concurrency::propagator_block::decline_incoming_messages
- AGENTS/concurrency::propagator_block::initialize_source_and_target
- AGENTS/concurrency::propagator_block::link_source
- AGENTS/concurrency::propagator_block::process_input_messages
- AGENTS/concurrency::propagator_block::propagate_message
- AGENTS/concurrency::propagator_block::register_filter
- AGENTS/concurrency::propagator_block::remove_network_links
- AGENTS/concurrency::propagator_block::send_message
- AGENTS/concurrency::propagator_block::unlink_source
- AGENTS/concurrency::propagator_block::unlink_sources
helpviewer_keywords:
- propagator_block class
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
ms.openlocfilehash: 4dd006829e01f663be20be76a2cc2e0364ef7b38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115243"
---
# <a name="propagator_block-class"></a>propagator_block 类

`propagator_block` 类是同时为源和目标的消息块的抽象基类。 它合并了 `source_block` 和 `target_block` 类的功能。

## <a name="syntax"></a>语法

```cpp
template<class _TargetLinkRegistry, class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class propagator_block : public source_block<_TargetLinkRegistry,
    _MessageProcessorType>,
public ITarget<typename _SourceLinkRegistry::type::source_type>;
```

### <a name="parameters"></a>parameters

*_TargetLinkRegistry*<br/>
用于保存目标链接的链接注册表。

*_SourceLinkRegistry*<br/>
用于保存源链接的链接注册表。

*_MessageProcessorType*<br/>
用于消息处理的处理器类型。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|`source_iterator`|此的的迭代器的类型 `source_link_manager` `propagator_block` 。|

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[propagator_block](#ctor)|构造 `propagator_block` 对象。|
|[~ propagator_block 析构函数](#dtor)|销毁 `propagator_block` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[传](#propagate)|将消息从源块异步传递到此目标块。|
|[send](#send)|将消息同步启动到此块。 由块调用 `ISource` 。 此函数完成后，消息将已传播到块中。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[decline_incoming_messages](#decline_incoming_messages)|向块指示应拒绝新消息。|
|[initialize_source_and_target](#initialize_source_and_target)|初始化基对象。 具体而言， `message_processor` 需要对对象进行初始化。|
|[link_source](#link_source)|将指定的源块链接到此 `propagator_block` 对象。|
|[process_input_messages](#process_input_messages)|处理输入消息。 这仅适用于派生自 source_block 的传播程序块 (替代 [source_block：:p rocess_input_messages](source-block-class.md#process_input_messages)。 ) |
|[propagate_message](#propagate_message)|当在派生类中重写时，此方法将消息从块异步传递 `ISource` 到此 `propagator_block` 对象。 此 `propagate` 方法由源块调用时由方法调用。|
|[register_filter](#register_filter)|注册将对每个收到的消息调用的筛选器方法。|
|[remove_network_links](#remove_network_links)|从此对象中移除所有源和目标网络链接 `propagator_block` 。|
|[send_message](#send_message)|当在派生类中重写时，此方法将消息从块同步传递 `ISource` 到此 `propagator_block` 对象。 此 `send` 方法由源块调用时由方法调用。|
|[unlink_source](#unlink_source)|从此对象断开指定的源块 `propagator_block` 。|
|[unlink_sources](#unlink_sources)|将所有源块与此 `propagator_block` 对象断开。  (重写 [ITarget：： unlink_sources](itarget-class.md#unlink_sources)。 ) |

## <a name="remarks"></a>备注

为了避免多重继承， `propagator_block` 该类继承自 `source_block` 类和 `ITarget` 抽象类。 类中的大部分功能 `target_block` 都在此处复制。

## <a name="inheritance-hierarchy"></a>继承层次结构

[ISource](isource-class.md)

[ITarget](itarget-class.md)

[source_block](source-block-class.md)

`propagator_block`

## <a name="requirements"></a>要求

**标头：** agents.h

**命名空间：** 并发

## <a name="decline_incoming_messages"></a><a name="decline_incoming_messages"></a> decline_incoming_messages

向块指示应拒绝新消息。

```cpp
void decline_incoming_messages();
```

### <a name="remarks"></a>备注

此方法由析构函数调用，以确保在析构正在进行时，新消息被拒绝。

## <a name="initialize_source_and_target"></a><a name="initialize_source_and_target"></a> initialize_source_and_target

初始化基对象。 具体而言， `message_processor` 需要对对象进行初始化。

```cpp
void initialize_source_and_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```

### <a name="parameters"></a>parameters

*_PScheduler*<br/>
用于计划任务的计划程序。

*_PScheduleGroup*<br/>
用于计划任务的计划组。

## <a name="link_source"></a><a name="link_source"></a> link_source

将指定的源块链接到此 `propagator_block` 对象。

```cpp
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>parameters

*_PSource*<br/>
指向 `ISource` 要链接的块的指针。

## <a name="process_input_messages"></a><a name="process_input_messages"></a> process_input_messages

处理输入消息。 这只适用于从源块派生的传播器块。

```cpp
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```

### <a name="parameters"></a>parameters

*_PMessage*<br/>
指向要处理的消息的指针。

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

`propagate`方法由链接源块在目标块上调用。 它将异步任务排队以处理消息（如果尚未对其进行排队或执行）。

如果[](../../../standard-library/invalid-argument-class.md) `_PMessage` 或参数为，方法将引发 invalid_argument 异常 `_PSource` `NULL` 。

## <a name="propagate_message"></a><a name="propagate_message"></a> propagate_message

当在派生类中重写时，此方法将消息从块异步传递 `ISource` 到此 `propagator_block` 对象。 此 `propagate` 方法由源块调用时由方法调用。

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

## <a name="propagator_block"></a><a name="ctor"></a> propagator_block

构造 `propagator_block` 对象。

```cpp
propagator_block();
```

## <a name="propagator_block"></a><a name="dtor"></a> ~ propagator_block

销毁 `propagator_block` 对象。

```cpp
virtual ~propagator_block();
```

## <a name="register_filter"></a><a name="register_filter"></a> register_filter

注册将对每个收到的消息调用的筛选器方法。

```cpp
void register_filter(filter_method const& _Filter);
```

### <a name="parameters"></a>parameters

*_Filter*<br/>
筛选器方法。

## <a name="remove_network_links"></a><a name="remove_network_links"></a> remove_network_links

从此对象中移除所有源和目标网络链接 `propagator_block` 。

```cpp
void remove_network_links();
```

## <a name="send"></a><a name="send"></a> 发送

将消息同步启动到此块。 由块调用 `ISource` 。 此函数完成后，消息将已传播到块中。

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

如果[](../../../standard-library/invalid-argument-class.md) `_PMessage` 或参数为，则此方法将引发 invalid_argument 异常 `_PSource` `NULL` 。

## <a name="send_message"></a><a name="send_message"></a> send_message

当在派生类中重写时，此方法将消息从块同步传递 `ISource` 到此 `propagator_block` 对象。 此 `send` 方法由源块调用时由方法调用。

```cpp
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```

### <a name="return-value"></a>返回值

[Message_status](concurrency-namespace-enums.md)指示目标决定对消息执行的操作。

### <a name="remarks"></a>备注

默认情况下， `declined` 除非由派生类重写，否则将返回。

## <a name="unlink_source"></a><a name="unlink_source"></a> unlink_source

从此对象断开指定的源块 `propagator_block` 。

```cpp
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```

### <a name="parameters"></a>parameters

*_PSource*<br/>
指向要取消链接的块的指针 `ISource` 。

## <a name="unlink_sources"></a><a name="unlink_sources"></a> unlink_sources

将所有源块与此 `propagator_block` 对象断开。

```cpp
virtual void unlink_sources();
```

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)<br/>
[source_block 类](source-block-class.md)<br/>
[ITarget 类](itarget-class.md)
