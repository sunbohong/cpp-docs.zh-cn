---
description: 了解详细信息： CD2DBrush 类
title: CD2DBrush 类
ms.date: 11/04/2016
f1_keywords:
- CD2DBrush
- AFXRENDERTARGET/CD2DBrush
- AFXRENDERTARGET/CD2DBrush::CD2DBrush
- AFXRENDERTARGET/CD2DBrush::Attach
- AFXRENDERTARGET/CD2DBrush::Destroy
- AFXRENDERTARGET/CD2DBrush::Detach
- AFXRENDERTARGET/CD2DBrush::Get
- AFXRENDERTARGET/CD2DBrush::GetOpacity
- AFXRENDERTARGET/CD2DBrush::GetTransform
- AFXRENDERTARGET/CD2DBrush::IsValid
- AFXRENDERTARGET/CD2DBrush::SetOpacity
- AFXRENDERTARGET/CD2DBrush::SetTransform
- AFXRENDERTARGET/CD2DBrush::m_pBrush
- AFXRENDERTARGET/CD2DBrush::m_pBrushProperties
helpviewer_keywords:
- CD2DBrush [MFC], CD2DBrush
- CD2DBrush [MFC], Attach
- CD2DBrush [MFC], Destroy
- CD2DBrush [MFC], Detach
- CD2DBrush [MFC], Get
- CD2DBrush [MFC], GetOpacity
- CD2DBrush [MFC], GetTransform
- CD2DBrush [MFC], IsValid
- CD2DBrush [MFC], SetOpacity
- CD2DBrush [MFC], SetTransform
- CD2DBrush [MFC], m_pBrush
- CD2DBrush [MFC], m_pBrushProperties
ms.assetid: 0d2c0857-2261-48a8-8ee0-a88cbf08499a
ms.openlocfilehash: 6d19601258951a297a734aa304e2a22c98baf5c9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227567"
---
# <a name="cd2dbrush-class"></a>CD2DBrush 类

ID2D1Brush 的包装器。

## <a name="syntax"></a>语法

```
class CD2DBrush : public CD2DResource;
```

## <a name="members"></a>成员

### <a name="protected-constructors"></a>受保护的构造函数

|名称|描述|
|----------|-----------------|
|[CD2DBrush：： CD2DBrush](#cd2dbrush)|构造 CD2DBrush 对象。|
|[CD2DBrush：： ~ CD2DBrush](#_dtorcd2dbrush)|析构函数。 当 D2D 画笔对象被销毁时调用。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CD2DBrush：： Attach](#attach)|将现有资源接口附加到对象|
|[CD2DBrush：:D estroy](#destroy)|销毁 CD2DBrush 对象。  (重写 [CD2DResource：:D estroy](../../mfc/reference/cd2dresource-class.md#destroy)。 ) |
|[CD2DBrush：:D etach](#detach)|从对象分离资源接口|
|[CD2DBrush：： Get](#get)|返回 ID2D1Brush 接口|
|[CD2DBrush：： GetOpacity](#getopacity)|获取此画笔的不透明度|
|[CD2DBrush：： GetTransform](#gettransform)|获取呈现器目标的当前转换|
|[CD2DBrush：： IsValid](#isvalid)|检查资源有效性 (重写 [CD2DResource：： IsValid](../../mfc/reference/cd2dresource-class.md#isvalid). ) |
|[CD2DBrush：： SetOpacity](#setopacity)|设置此画笔的不透明度|
|[CD2DBrush：： SetTransform](#settransform)|将指定的转换应用于呈现器目标，并替换现有转换。 所有后续绘图操作都在转换后的空间中发生|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CD2DBrush：： operator ID2D1Brush *](#operator_id2d1brush_star)|返回 ID2D1Brush 接口|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CD2DBrush：： m_pBrush](#m_pbrush)|存储指向 ID2D1Brush 对象的指针。|
|[CD2DBrush：： m_pBrushProperties](#m_pbrushproperties)|画笔属性。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DBrush`

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2dbrushcd2dbrush"></a><a name="_dtorcd2dbrush"></a> CD2DBrush：： ~ CD2DBrush

析构函数。 当 D2D 画笔对象被销毁时调用。

```
virtual ~CD2DBrush();
```

## <a name="cd2dbrushattach"></a><a name="attach"></a> CD2DBrush：： Attach

将现有的资源接口附加到对象。

```cpp
void Attach(ID2D1Brush* pResource);
```

### <a name="parameters"></a>parameters

*pResource*<br/>
现有的资源接口。 不能为 NULL。

## <a name="cd2dbrushcd2dbrush"></a><a name="cd2dbrush"></a> CD2DBrush：： CD2DBrush

构造 CD2DBrush 对象。

```
CD2DBrush(
    CRenderTarget* pParentTarget,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>parameters

*pParentTarget*<br/>
指向呈现器目标的指针。

*pBrushProperties*<br/>
指向画笔的不透明度和转换的指针。

*bAutoDestroy*<br/>
指示对象将被所有者 (pParentTarget) 销毁。

## <a name="cd2dbrushdestroy"></a><a name="destroy"></a> CD2DBrush：:D estroy

销毁 CD2DBrush 对象。

```
virtual void Destroy();
```

## <a name="cd2dbrushdetach"></a><a name="detach"></a> CD2DBrush：:D etach

从对象分离资源接口。

```
ID2D1Brush* Detach();
```

### <a name="return-value"></a>返回值

指向已分离资源接口的指针。

## <a name="cd2dbrushget"></a><a name="get"></a> CD2DBrush：： Get

返回 ID2D1Brush 接口

```
ID2D1Brush* Get();
```

### <a name="return-value"></a>返回值

指向 ID2D1Brush 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dbrushgetopacity"></a><a name="getopacity"></a> CD2DBrush：： GetOpacity

获取此画笔的不透明度

```
FLOAT GetOpacity() const;
```

### <a name="return-value"></a>返回值

一个介于0和1之间的值，该值指示画笔的不透明度。 此值是一个固定乘数，可线性缩放画笔填充的所有像素的 alpha 值。 不透明度值介于0和1之间，然后将其相乘。

## <a name="cd2dbrushgettransform"></a><a name="gettransform"></a> CD2DBrush：： GetTransform

获取呈现器目标的当前转换

```cpp
void GetTransform(D2D1_MATRIX_3X2_F* transform) const;
```

### <a name="parameters"></a>parameters

*transform*<br/>
当此返回时，包含呈现器目标的当前转换。 此参数未经初始化即被传递。

## <a name="cd2dbrushisvalid"></a><a name="isvalid"></a> CD2DBrush：： IsValid

检查资源有效性

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>返回值

如果资源有效，则为 TRUE;否则为 FALSE。

## <a name="cd2dbrushm_pbrush"></a><a name="m_pbrush"></a> CD2DBrush：： m_pBrush

存储指向 ID2D1Brush 对象的指针。

```
ID2D1Brush* m_pBrush;
```

## <a name="cd2dbrushm_pbrushproperties"></a><a name="m_pbrushproperties"></a> CD2DBrush：： m_pBrushProperties

画笔属性。

```
CD2DBrushProperties* m_pBrushProperties;
```

## <a name="cd2dbrushoperator-id2d1brush"></a><a name="operator_id2d1brush_star"></a> CD2DBrush：： operator ID2D1Brush *

返回 ID2D1Brush 接口

```
operator ID2D1Brush*();
```

### <a name="return-value"></a>返回值

指向 ID2D1Brush 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dbrushsetopacity"></a><a name="setopacity"></a> CD2DBrush：： SetOpacity

设置此画笔的不透明度

```cpp
void SetOpacity(FLOAT opacity);
```

### <a name="parameters"></a>parameters

*蒙*<br/>
一个介于0和1之间的值，该值指示画笔的不透明度。 此值是一个固定乘数，可线性缩放画笔填充的所有像素的 alpha 值。 不透明度值介于0和1之间，然后将其相乘。

## <a name="cd2dbrushsettransform"></a><a name="settransform"></a> CD2DBrush：： SetTransform

将指定的转换应用于呈现器目标，并替换现有转换。 所有后续绘图操作都在转换后的空间中发生。

```cpp
void SetTransform(const D2D1_MATRIX_3X2_F* transform);
```

### <a name="parameters"></a>parameters

*transform*<br/>
要应用于呈现器目标的转换

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
