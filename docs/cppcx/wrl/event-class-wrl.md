---
description: '了解详细信息：事件类 (WRL) '
title: '事件类 (WRL) '
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Event class
- Microsoft::WRL::Wrappers::Event::Event, constructor
- Microsoft::WRL::Wrappers::Event::operator= operator
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
ms.openlocfilehash: e3a61a40d1160830df80a7e0650e60fbf803e3d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272820"
---
# <a name="event-class-wrl"></a>事件类 (WRL) 

表示一个事件。

## <a name="syntax"></a>语法

```cpp
class Event : public HandleT<HandleTraits::EventTraits>;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

“属性”                   | 描述
---------------------- | ------------------------------------------------
[Event：： Event](#event) | 初始化 `Event` 类的新实例。

### <a name="public-operators"></a>公共运算符

名称                                 | 描述
------------------------------------ | ------------------------------------------------------------------------
[Event：： operator =](#operator-assign) | 将指定的 `Event` 引用分配给当前 `Event` 实例。

## <a name="inheritance-hierarchy"></a>继承层次结构

`HandleT`

`Event`

## <a name="requirements"></a>要求

**标头：** corewrappers。h

**命名空间：** Microsoft：： WRL：：包装

## <a name="eventevent"></a><a name="event"></a> Event：： Event

初始化 `Event` 类的新实例。

```cpp
explicit Event(
   HANDLE h = HandleT::Traits::GetInvalidValue()
);
WRL_NOTHROW Event(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>parameters

*h*<br/>
事件的句柄。 默认情况下， *h* 初始化为 **`nullptr`** 。

## <a name="eventoperator"></a><a name="operator-assign"></a> Event：： operator =

将指定的 `Event` 引用分配给当前 `Event` 实例。

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>parameters

*h*<br/>
对实例的右值引用 `Event` 。

### <a name="return-value"></a>返回值

指向当前实例的指针 `Event` 。
