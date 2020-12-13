---
description: 了解详细信息： ITopologyExecutionResource 结构
title: ITopologyExecutionResource 结构
ms.date: 11/04/2016
f1_keywords:
- ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetId
- CONCRTRM/concurrency::ITopologyExecutionResource::ITopologyExecutionResource::GetNext
helpviewer_keywords:
- ITopologyExecutionResource structure
ms.assetid: e36756f7-4cd9-4fa6-ba60-23fea58ef2bf
ms.openlocfilehash: c2567cf9e34e0b27308e331056d5e0dbc99b2779
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334380"
---
# <a name="itopologyexecutionresource-structure"></a>ITopologyExecutionResource 结构

资源管理器定义的执行资源的接口。

## <a name="syntax"></a>语法

```cpp
struct ITopologyExecutionResource;
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[ITopologyExecutionResource：： GetId](#getid)|返回此执行资源的资源管理器的唯一标识符。|
|[ITopologyExecutionResource：： GetNext](#getnext)|返回一个指向枚举顺序中下一执行资源的接口。|

## <a name="remarks"></a>备注

通常使用此接口来遍历由资源管理器观察到的系统拓扑。

## <a name="inheritance-hierarchy"></a>继承层次结构

`ITopologyExecutionResource`

## <a name="requirements"></a>要求

**标头：** concrtrm。h

**命名空间：** 并发

## <a name="itopologyexecutionresourcegetid-method"></a><a name="getid"></a> ITopologyExecutionResource：： GetId 方法

返回此执行资源的资源管理器的唯一标识符。

```cpp
virtual unsigned int GetId() const = 0;
```

### <a name="return-value"></a>返回值

此执行资源的资源管理器的唯一标识符。

## <a name="itopologyexecutionresourcegetnext-method"></a><a name="getnext"></a> ITopologyExecutionResource：： GetNext 方法

返回一个指向枚举顺序中下一执行资源的接口。

```cpp
virtual ITopologyExecutionResource *GetNext() const = 0;
```

### <a name="return-value"></a>返回值

一个指向枚举顺序中下一执行资源的接口。 如果此执行资源所属节点的枚举顺序中没有更多的节点，此方法将返回值 `NULL`。

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)
