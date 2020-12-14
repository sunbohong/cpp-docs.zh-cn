---
description: 了解详细信息： scheduler_interface 结构
title: scheduler_interface 结构
ms.date: 11/04/2016
f1_keywords:
- scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface
- PPLINTERFACE/concurrency::scheduler_interface::scheduler_interface::schedule
ms.assetid: 4de61c78-a2c6-4698-bd47-964baf7fa287
ms.openlocfilehash: ba56ef809cf398a192810eb96a8b4e4ca50ec1cc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97188867"
---
# <a name="scheduler_interface-structure"></a>scheduler_interface 结构

计划程序接口

## <a name="syntax"></a>语法

```cpp
struct __declspec(novtable) scheduler_interface;
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[scheduler_interface：： schedule](#schedule)||

## <a name="inheritance-hierarchy"></a>继承层次结构

`scheduler_interface`

## <a name="requirements"></a>要求

**标头：** pplinterface。h

**命名空间：** 并发

## <a name="scheduler_interfaceschedule-method"></a><a name="schedule"></a> scheduler_interface：： schedule 方法

```cpp
virtual void schedule(
    TaskProc_t,
void*) = 0;
```

## <a name="see-also"></a>请参阅

[并发命名空间](concurrency-namespace.md)
