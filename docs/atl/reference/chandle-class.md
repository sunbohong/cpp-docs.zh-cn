---
description: 了解详细信息： CHandle 类
title: CHandle 类
ms.date: 07/09/2019
f1_keywords:
- CHandle
- ATLBASE/ATL::CHandle
- ATLBASE/ATL::CHandle::CHandle
- ATLBASE/ATL::CHandle::Attach
- ATLBASE/ATL::CHandle::Close
- ATLBASE/ATL::CHandle::Detach
- ATLBASE/ATL::CHandle::m_h
helpviewer_keywords:
- CHandle class
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
ms.openlocfilehash: 01c3b281daf829bc6488df35114c6cb853640ed1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97141669"
---
# <a name="chandle-class"></a>CHandle 类

此类提供用于创建和使用 handle 对象的方法。

## <a name="syntax"></a>语法

```
class CHandle
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CHandle::CHandle](#chandle)|构造函数。|
|[CHandle：： ~ CHandle](#dtor)|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CHandle：： Attach](#attach)|调用此方法可将 `CHandle` 对象附加到现有句柄。|
|[CHandle：： Close](#close)|调用此方法可关闭 `CHandle` 对象。|
|[CHandle：:D etach](#detach)|调用此方法可从对象分离句柄 `CHandle` 。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CHandle：： operator 句柄](#operator_handle)|返回存储句柄的值。|
|[CHandle：： operator =](#operator_eq)|赋值运算符。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CHandle：： m_h](#m_h)|存储句柄的成员变量。|

## <a name="remarks"></a>备注

`CHandle`只要需要句柄，就可以使用对象：主要区别在于 `CHandle` 将自动删除该对象。

> [!NOTE]
> 某些 API 函数将使用 NULL 作为空或无效的句柄，而其他 API 函数使用 INVALID_HANDLE_VALUE。 `CHandle` 仅使用 NULL，并将 INVALID_HANDLE_VALUE 视为真实句柄。 如果调用可返回 INVALID_HANDLE_VALUE 的 API，则应在调用 [CHandle：： Attach](#attach) 或将其传递给构造函数之前检查该值 `CHandle` ，并改为传递 NULL。

## <a name="requirements"></a>要求

**标头：** atlbase。h

## <a name="chandleattach"></a><a name="attach"></a> CHandle：： Attach

调用此方法可将 `CHandle` 对象附加到现有句柄。

```cpp
void Attach(HANDLE h) throw();
```

### <a name="parameters"></a>parameters

*h*<br/>
`CHandle` 将取得句柄 *h* 的所有权。

### <a name="remarks"></a>备注

将 `CHandle` 对象分配给 *h* 句柄，然后调用- **B1 (**。 在调试版本中，如果 *h* 为 NULL，则会引发 ATLASSERT。 不会对句柄的有效性进行任何其他检查。

## <a name="chandlechandle"></a><a name="chandle"></a> CHandle::CHandle

构造函数。

```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```

### <a name="parameters"></a>parameters

*h*<br/>
现有的句柄或 `CHandle` 。

### <a name="remarks"></a>备注

`CHandle`使用现有的句柄或对象，创建一个新的对象 `CHandle` 。

## <a name="chandlechandle"></a><a name="dtor"></a> CHandle：： ~ CHandle

析构函数。

```
~CHandle() throw();
```

### <a name="remarks"></a>备注

`CHandle`通过调用[CHandle：： Close](#close)释放对象。

## <a name="chandleclose"></a><a name="close"></a> CHandle：： Close

调用此方法可关闭 `CHandle` 对象。

```cpp
void Close() throw();
```

### <a name="remarks"></a>备注

关闭打开的对象句柄。 如果句柄为 NULL，则如果已调用，则会在 `Close` 调试生成中引发 ATLASSERT。

## <a name="chandledetach"></a><a name="detach"></a> CHandle：:D etach

调用此方法可从对象分离句柄 `CHandle` 。

```
HANDLE Detach() throw();
```

### <a name="return-value"></a>返回值

返回正在分离的句柄。

### <a name="remarks"></a>备注

释放句柄的所有权。

## <a name="chandlem_h"></a><a name="m_h"></a> CHandle：： m_h

存储句柄的成员变量。

```
HANDLE m_h;
```

## <a name="chandleoperator-"></a><a name="operator_eq"></a> CHandle：： operator =

赋值运算符。

```
CHandle& operator=(CHandle& h) throw();
```

### <a name="parameters"></a>parameters

*h*<br/>
`CHandle` 将取得句柄 *h* 的所有权。

### <a name="return-value"></a>返回值

返回对新对象的引用 `CHandle` 。

### <a name="remarks"></a>备注

如果 `CHandle` 对象当前包含一个句柄，则会将其关闭。 `CHandle`传入的对象的句柄引用将设置为 NULL。 这可确保两个 `CHandle` 对象永远不会包含相同的活动句柄。

## <a name="chandleoperator-handle"></a><a name="operator_handle"></a> CHandle：： operator 句柄

返回存储句柄的值。

```
operator HANDLE() const throw();
```

### <a name="remarks"></a>备注

返回存储在 [CHandle：： m_h](#m_h)中的值。

## <a name="see-also"></a>请参阅

[类概述](../../atl/atl-class-overview.md)
