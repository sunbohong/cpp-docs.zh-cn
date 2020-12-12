---
description: 了解详细信息： CD2DLinearGradientBrush 类
title: CD2DLinearGradientBrush 类
ms.date: 11/04/2016
f1_keywords:
- CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::CD2DLinearGradientBrush
- AFXRENDERTARGET/CD2DLinearGradientBrush::Attach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Create
- AFXRENDERTARGET/CD2DLinearGradientBrush::Destroy
- AFXRENDERTARGET/CD2DLinearGradientBrush::Detach
- AFXRENDERTARGET/CD2DLinearGradientBrush::Get
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::GetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetEndPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::SetStartPoint
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_LinearGradientBrushProperties
- AFXRENDERTARGET/CD2DLinearGradientBrush::m_pLinearGradientBrush
helpviewer_keywords:
- CD2DLinearGradientBrush [MFC], CD2DLinearGradientBrush
- CD2DLinearGradientBrush [MFC], Attach
- CD2DLinearGradientBrush [MFC], Create
- CD2DLinearGradientBrush [MFC], Destroy
- CD2DLinearGradientBrush [MFC], Detach
- CD2DLinearGradientBrush [MFC], Get
- CD2DLinearGradientBrush [MFC], GetEndPoint
- CD2DLinearGradientBrush [MFC], GetStartPoint
- CD2DLinearGradientBrush [MFC], SetEndPoint
- CD2DLinearGradientBrush [MFC], SetStartPoint
- CD2DLinearGradientBrush [MFC], m_LinearGradientBrushProperties
- CD2DLinearGradientBrush [MFC], m_pLinearGradientBrush
ms.assetid: d4be9ff9-0ea8-45e6-9b8d-f3bc5673cbac
ms.openlocfilehash: b133abe796e609a44d1ebe35a6e6e969c8ee2a68
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180326"
---
# <a name="cd2dlineargradientbrush-class"></a>CD2DLinearGradientBrush 类

ID2D1LinearGradientBrush 的包装器。

## <a name="syntax"></a>语法

```
class CD2DLinearGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CD2DLinearGradientBrush：： CD2DLinearGradientBrush](#cd2dlineargradientbrush)|构造 CD2DLinearGradientBrush 对象。|
|[CD2DLinearGradientBrush：： ~ CD2DLinearGradientBrush](#_dtorcd2dlineargradientbrush)|析构函数。 当 D2D 线性渐变画笔对象被销毁时调用。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CD2DLinearGradientBrush：： Attach](#attach)|将现有资源接口附加到对象|
|[CD2DLinearGradientBrush：： Create](#create)|创建 CD2DLinearGradientBrush。  (重写 [CD2DResource：： Create](../../mfc/reference/cd2dresource-class.md#create). ) |
|[CD2DLinearGradientBrush：:D estroy](#destroy)|销毁 CD2DLinearGradientBrush 对象。  (重写 [CD2DGradientBrush：:D estroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy)。 ) |
|[CD2DLinearGradientBrush：:D etach](#detach)|从对象分离资源接口|
|[CD2DLinearGradientBrush：： Get](#get)|返回 ID2D1LinearGradientBrush 接口|
|[CD2DLinearGradientBrush：： GetEndPoint](#getendpoint)|检索线性渐变的结束坐标|
|[CD2DLinearGradientBrush：： GetStartPoint](#getstartpoint)|检索线性渐变的起始坐标|
|[CD2DLinearGradientBrush：： SetEndPoint](#setendpoint)|设置画笔坐标空间中线性渐变的结束坐标|
|[CD2DLinearGradientBrush：： SetStartPoint](#setstartpoint)|设置画笔坐标空间中线性渐变的起始坐标|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CD2DLinearGradientBrush：： operator ID2D1LinearGradientBrush *](#operator_id2d1lineargradientbrush_star)|返回 ID2D1LinearGradientBrush 接口|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CD2DLinearGradientBrush：： m_LinearGradientBrushProperties](#m_lineargradientbrushproperties)|渐变的起始点和结束点。|
|[CD2DLinearGradientBrush：： m_pLinearGradientBrush](#m_plineargradientbrush)|指向 ID2D1LinearGradientBrush 的指针。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DLinearGradientBrush`

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="_dtorcd2dlineargradientbrush"></a> CD2DLinearGradientBrush：： ~ CD2DLinearGradientBrush

析构函数。 当 D2D 线性渐变画笔对象被销毁时调用。

```
virtual ~CD2DLinearGradientBrush();
```

## <a name="cd2dlineargradientbrushattach"></a><a name="attach"></a> CD2DLinearGradientBrush：： Attach

将现有资源接口附加到对象

```cpp
void Attach(ID2D1LinearGradientBrush* pResource);
```

### <a name="parameters"></a>parameters

*pResource*<br/>
现有的资源接口。 不能为 NULL

## <a name="cd2dlineargradientbrushcd2dlineargradientbrush"></a><a name="cd2dlineargradientbrush"></a> CD2DLinearGradientBrush：： CD2DLinearGradientBrush

构造 CD2DLinearGradientBrush 对象。

```
CD2DLinearGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES LinearGradientBrushProperties,
    D2D1_GAMMA colorInterpolationGamma = D2D1_GAMMA_2_2,
    D2D1_EXTEND_MODE extendMode = D2D1_EXTEND_MODE_CLAMP,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>parameters

*pParentTarget*<br/>
指向呈现器目标的指针。

*gradientStops*<br/>
指向 D2D1_GRADIENT_STOP 结构的数组的指针。

*gradientStopsCount*<br/>
一个大于或等于1的值，指定 gradientStops 数组中的梯度停止点数。

*LinearGradientBrushProperties*<br/>
渐变的起始点和结束点。

*colorInterpolationGamma*<br/>
执行梯度停止点之间的颜色插值的空间。

*extendMode*<br/>
[0，1] 标准化范围外的渐变的行为。

*pBrushProperties*<br/>
指向画笔的不透明度和转换的指针。

*bAutoDestroy*<br/>
指示对象将被所有者 (pParentTarget) 销毁。

## <a name="cd2dlineargradientbrushcreate"></a><a name="create"></a> CD2DLinearGradientBrush：： Create

创建 CD2DLinearGradientBrush。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>parameters

*pRenderTarget*<br/>
指向呈现器目标的指针。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="cd2dlineargradientbrushdestroy"></a><a name="destroy"></a> CD2DLinearGradientBrush：:D estroy

销毁 CD2DLinearGradientBrush 对象。

```
virtual void Destroy();
```

## <a name="cd2dlineargradientbrushdetach"></a><a name="detach"></a> CD2DLinearGradientBrush：:D etach

从对象分离资源接口

```
ID2D1LinearGradientBrush* Detach();
```

### <a name="return-value"></a>返回值

指向已分离资源接口的指针。

## <a name="cd2dlineargradientbrushget"></a><a name="get"></a> CD2DLinearGradientBrush：： Get

返回 ID2D1LinearGradientBrush 接口

```
ID2D1LinearGradientBrush* Get();
```

### <a name="return-value"></a>返回值

指向 ID2D1LinearGradientBrush 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dlineargradientbrushgetendpoint"></a><a name="getendpoint"></a> CD2DLinearGradientBrush：： GetEndPoint

检索线性渐变的结束坐标

```
CD2DPointF GetEndPoint() const;
```

### <a name="return-value"></a>返回值

画笔坐标空间中线性渐变的二维结束坐标

## <a name="cd2dlineargradientbrushgetstartpoint"></a><a name="getstartpoint"></a> CD2DLinearGradientBrush：： GetStartPoint

检索线性渐变的起始坐标

```
CD2DPointF GetStartPoint() const;
```

### <a name="return-value"></a>返回值

画笔坐标空间中线性渐变的二维起始坐标。

## <a name="cd2dlineargradientbrushm_lineargradientbrushproperties"></a><a name="m_lineargradientbrushproperties"></a> CD2DLinearGradientBrush：： m_LinearGradientBrushProperties

渐变的起始点和结束点。

```
D2D1_LINEAR_GRADIENT_BRUSH_PROPERTIES m_LinearGradientBrushProperties;
```

## <a name="cd2dlineargradientbrushm_plineargradientbrush"></a><a name="m_plineargradientbrush"></a> CD2DLinearGradientBrush：： m_pLinearGradientBrush

指向 ID2D1LinearGradientBrush 的指针。

```
ID2D1LinearGradientBrush* m_pLinearGradientBrush;
```

## <a name="cd2dlineargradientbrushoperator-id2d1lineargradientbrush"></a><a name="operator_id2d1lineargradientbrush_star"></a> CD2DLinearGradientBrush：： operator ID2D1LinearGradientBrush *

返回 ID2D1LinearGradientBrush 接口

```
operator ID2D1LinearGradientBrush*();
```

### <a name="return-value"></a>返回值

指向 ID2D1LinearGradientBrush 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dlineargradientbrushsetendpoint"></a><a name="setendpoint"></a> CD2DLinearGradientBrush：： SetEndPoint

设置画笔坐标空间中线性渐变的结束坐标

```cpp
void SetEndPoint(CD2DPointF point);
```

### <a name="parameters"></a>parameters

*情况*<br/>
画笔坐标空间中线性渐变的二维结束坐标

## <a name="cd2dlineargradientbrushsetstartpoint"></a><a name="setstartpoint"></a> CD2DLinearGradientBrush：： SetStartPoint

设置画笔坐标空间中线性渐变的起始坐标

```cpp
void SetStartPoint(CD2DPointF point);
```

### <a name="parameters"></a>parameters

*情况*<br/>
画笔坐标空间中线性渐变的二维起始坐标。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
