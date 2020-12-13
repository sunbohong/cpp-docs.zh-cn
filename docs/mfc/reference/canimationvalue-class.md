---
description: 了解详细信息： CAnimationValue 类
title: CAnimationValue 类
ms.date: 11/04/2016
f1_keywords:
- CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::CAnimationValue
- AFXANIMATIONCONTROLLER/CAnimationValue::AddTransition
- AFXANIMATIONCONTROLLER/CAnimationValue::GetValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetVariable
- AFXANIMATIONCONTROLLER/CAnimationValue::SetDefaultValue
- AFXANIMATIONCONTROLLER/CAnimationValue::GetAnimationVariableList
- AFXANIMATIONCONTROLLER/CAnimationValue::m_value
helpviewer_keywords:
- CAnimationValue [MFC], CAnimationValue
- CAnimationValue [MFC], AddTransition
- CAnimationValue [MFC], GetValue
- CAnimationValue [MFC], GetVariable
- CAnimationValue [MFC], SetDefaultValue
- CAnimationValue [MFC], GetAnimationVariableList
- CAnimationValue [MFC], m_value
ms.assetid: 78c5ae19-ede5-4f20-bfbe-68b467b603c2
ms.openlocfilehash: d704e83d286b4078af90d09edef35e8445d149d3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336744"
---
# <a name="canimationvalue-class"></a>CAnimationValue 类

实现有一个值的动画对象功能。

## <a name="syntax"></a>语法

```
class CAnimationValue : public CAnimationBaseObject;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CAnimationValue：： CAnimationValue](#canimationvalue)|已重载。 构造 CAnimationValue 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CAnimationValue：： AddTransition](#addtransition)|添加要应用于值的转换。|
|[CAnimationValue：： GetValue](#getvalue)|已重载。 检索当前值。|
|[CAnimationValue：： GetVariable](#getvariable)|提供对封装的动画变量的访问。|
|[CAnimationValue：： SetDefaultValue](#setdefaultvalue)|设置默认值。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CAnimationValue：： GetAnimationVariableList](#getanimationvariablelist)|将封装的动画变量放入列表中。  (重写 [CAnimationBaseObject：： GetAnimationVariableList](../../mfc/reference/canimationbaseobject-class.md#getanimationvariablelist)。 ) |

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CAnimationValue：： operator DOUBLE](#operator_double)|提供 CAnimationValue 和 DOUBLE 之间的转换。|
|[CAnimationValue：： operator INT32](#operator_int32)|提供 CAnimationValue 和 INT32 之间的转换。|
|[CAnimationValue：： operator =](#operator_eq)|已重载。 将 INT32 值分配给 CAnimationValue。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CAnimationValue：： m_value](#m_value)|封装动画变量，它表示动画值。|

## <a name="remarks"></a>备注

CAnimationValue 类封装单个 CAnimationVariable 对象，并可在应用程序中表示单个动画值。 例如，你可以将此类用于动画透明度 (淡化效果) 、 (旋转对象) ，或在需要根据单个动画值创建动画时为任何其他情况使用此类。 若要在应用程序中使用此类，只需实例化此类的对象，将其添加到使用 CAnimationController：： AddAnimationObject 的动画控制器，并为每个要应用于此值的转换调用 AddTransition。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CAnimationBaseObject](../../mfc/reference/canimationbaseobject-class.md)

`CAnimationValue`

## <a name="requirements"></a>要求

**标头：** afxanimationcontroller.h

## <a name="canimationvalueaddtransition"></a><a name="addtransition"></a> CAnimationValue：： AddTransition

添加要应用于值的转换。

```cpp
void AddTransition(CBaseTransition* pTransition);
```

### <a name="parameters"></a>parameters

*pTransition*<br/>
指向转换对象的指针。

### <a name="remarks"></a>备注

调用此函数可将转换添加到要应用于动画变量的转换的内部列表。 添加转换时，它们不会立即应用，而是存储在内部列表中。 调用 CAnimationController：： AnimateGroup 时，会将转换应用 (添加到特定) 值的情节提要。

## <a name="canimationvaluecanimationvalue"></a><a name="canimationvalue"></a> CAnimationValue：： CAnimationValue

构造 CAnimationValue 对象。

```
CAnimationValue();

CAnimationValue(
    DOUBLE dblDefaultValue,
    UINT32 nGroupID,
    UINT32 nObjectID = (UINT32)-1,
    DWORD dwUserData = 0);
```

### <a name="parameters"></a>parameters

*dblDefaultValue*<br/>
指定默认值。

*nGroupID*<br/>
指定组 ID。

*nObjectID*<br/>
指定对象 ID。

*dwUserData*<br/>
指定用户定义数据。

### <a name="remarks"></a>备注

用默认属性构造 CAnimationValue 对象：默认值、组 ID 和对象 ID 均设置为0。

## <a name="canimationvaluegetanimationvariablelist"></a><a name="getanimationvariablelist"></a> CAnimationValue：： GetAnimationVariableList

将封装的动画变量放入列表中。

```
virtual void GetAnimationVariableList(
    CList<CAnimationVariable*,
    CAnimationVariable*>& lst);
```

### <a name="parameters"></a>parameters

*.lst*<br/>
当函数返回时，它包含一个指向 CAnimationVariable 的指针，该指针表示动画值。

## <a name="canimationvaluegetvalue"></a><a name="getvalue"></a> CAnimationValue：： GetValue

检索当前值。

```
BOOL GetValue(DOUBLE& dblValue);
BOOL GetValue(INT32& nValue);
```

### <a name="parameters"></a>parameters

*dblValue*<br/>
输出。 当函数返回时，它包含动画变量的当前值。

*N 值*<br/>
输出。 当函数返回时，它包含动画变量的当前值。

### <a name="return-value"></a>返回值

如果成功检索到当前值，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

调用此函数可检索当前值。 此实现调用封装的 COM 对象，如果调用失败，则此方法将返回以前在构造函数或 with SetDefaultValue 中设置的默认值。

## <a name="canimationvaluegetvariable"></a><a name="getvariable"></a> CAnimationValue：： GetVariable

提供对封装的动画变量的访问。

```
CAnimationVariable& GetVariable();
```

### <a name="return-value"></a>返回值

对封装的动画变量的引用。

### <a name="remarks"></a>备注

使用此方法访问封装的动画变量。 通过 CAnimationVariable，你可以访问基础 IUIAnimationVariable 对象，如果尚未创建动画变量，则该对象的指针可以为 NULL。

## <a name="canimationvaluem_value"></a><a name="m_value"></a> CAnimationValue：： m_value

封装动画变量，它表示动画值。

```
CAnimationVariable m_value;
```

## <a name="canimationvalueoperator-double"></a><a name="operator_double"></a> CAnimationValue：： operator DOUBLE

提供 CAnimationValue 和 DOUBLE 之间的转换。

```
operator DOUBLE();
```

### <a name="return-value"></a>返回值

动画值的当前值。

### <a name="remarks"></a>备注

提供 CAnimationValue 和 DOUBLE 之间的转换。 此方法在内部调用 GetValue，不检查是否有错误。 如果 GetValue 失败，则返回的值将包含先前在构造函数或 with SetDefaultValue 中设置的默认值。

## <a name="canimationvalueoperator-int32"></a><a name="operator_int32"></a> CAnimationValue：： operator INT32

提供 CAnimationValue 和 INT32 之间的转换。

```
operator INT32();
```

### <a name="return-value"></a>返回值

整数形式的动画值的当前值。

### <a name="remarks"></a>备注

提供 CAnimationValue 和 INT32 之间的转换。 此方法在内部调用 GetValue，不检查是否有错误。 如果 GetValue 失败，则返回的值将包含先前在构造函数或 with SetDefaultValue 中设置的默认值。

## <a name="canimationvalueoperator"></a><a name="operator_eq"></a> CAnimationValue：： operator =

将双精度值赋给 CAnimationValue。

```cpp
void operator=(DOUBLE dblVal);
void operator=(INT32 nVal);
```

### <a name="parameters"></a>parameters

*dblVal*<br/>
指定要分配给动画值的值。

*nVal*<br/>
指定要分配给动画值的值。

### <a name="remarks"></a>备注

将双精度值赋给 CAnimationValue。 此值设置为封装动画变量的默认值。 如果已将此动画对象订阅 (ValueChanged 或 IntegerValueChanged) 的事件，则需要重新启用这些事件。

## <a name="canimationvaluesetdefaultvalue"></a><a name="setdefaultvalue"></a> CAnimationValue：： SetDefaultValue

设置默认值。

```cpp
void SetDefaultValue(DOUBLE dblDefaultValue);
```

### <a name="parameters"></a>parameters

*dblDefaultValue*<br/>
指定默认值。

### <a name="remarks"></a>备注

使用此方法可设置默认值。 如果尚未启动动画并且/或尚未创建基础 COM 对象，则会将默认值返回给应用程序。 如果已创建封装在 CAnimationVarible 中的基础 COM 对象，则此方法将重新创建它，因此可能需要再次调用 EnableValueChanged/EnableIntegerValueChanged 方法。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
