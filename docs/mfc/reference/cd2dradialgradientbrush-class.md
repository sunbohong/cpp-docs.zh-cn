---
description: 了解详细信息： CD2DRadialGradientBrush 类
title: CD2DRadialGradientBrush 类
ms.date: 11/04/2016
f1_keywords:
- CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::CD2DRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::Attach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Create
- AFXRENDERTARGET/CD2DRadialGradientBrush::Destroy
- AFXRENDERTARGET/CD2DRadialGradientBrush::Detach
- AFXRENDERTARGET/CD2DRadialGradientBrush::Get
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::GetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetCenter
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetGradientOriginOffset
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusX
- AFXRENDERTARGET/CD2DRadialGradientBrush::SetRadiusY
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_pRadialGradientBrush
- AFXRENDERTARGET/CD2DRadialGradientBrush::m_RadialGradientBrushProperties
helpviewer_keywords:
- CD2DRadialGradientBrush [MFC], CD2DRadialGradientBrush
- CD2DRadialGradientBrush [MFC], Attach
- CD2DRadialGradientBrush [MFC], Create
- CD2DRadialGradientBrush [MFC], Destroy
- CD2DRadialGradientBrush [MFC], Detach
- CD2DRadialGradientBrush [MFC], Get
- CD2DRadialGradientBrush [MFC], GetCenter
- CD2DRadialGradientBrush [MFC], GetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], GetRadiusX
- CD2DRadialGradientBrush [MFC], GetRadiusY
- CD2DRadialGradientBrush [MFC], SetCenter
- CD2DRadialGradientBrush [MFC], SetGradientOriginOffset
- CD2DRadialGradientBrush [MFC], SetRadiusX
- CD2DRadialGradientBrush [MFC], SetRadiusY
- CD2DRadialGradientBrush [MFC], m_pRadialGradientBrush
- CD2DRadialGradientBrush [MFC], m_RadialGradientBrushProperties
ms.assetid: 6c76d84a-d831-4ee2-96f1-82c1f5b0d6a9
ms.openlocfilehash: c5e169a5d608edd246d5c7269c94e3b225fdd491
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97118740"
---
# <a name="cd2dradialgradientbrush-class"></a>CD2DRadialGradientBrush 类

ID2D1RadialGradientBrush 的包装器。

## <a name="syntax"></a>语法

```
class CD2DRadialGradientBrush : public CD2DGradientBrush;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CD2DRadialGradientBrush：： CD2DRadialGradientBrush](#cd2dradialgradientbrush)|构造 CD2DLinearGradientBrush 对象。|
|[CD2DRadialGradientBrush：： ~ CD2DRadialGradientBrush](#_dtorcd2dradialgradientbrush)|析构函数。 当 D2D 放射梯度画笔对象被销毁时调用。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CD2DRadialGradientBrush：： Attach](#attach)|将现有资源接口附加到对象|
|[CD2DRadialGradientBrush：： Create](#create)|创建 CD2DRadialGradientBrush。  (重写 [CD2DResource：： Create](../../mfc/reference/cd2dresource-class.md#create). ) |
|[CD2DRadialGradientBrush：:D estroy](#destroy)|销毁 CD2DRadialGradientBrush 对象。  (重写 [CD2DGradientBrush：:D estroy](../../mfc/reference/cd2dgradientbrush-class.md#destroy)。 ) |
|[CD2DRadialGradientBrush：:D etach](#detach)|从对象分离资源接口|
|[CD2DRadialGradientBrush：： Get](#get)|返回 ID2D1RadialGradientBrush 接口|
|[CD2DRadialGradientBrush：： GetCenter](#getcenter)|检索渐变椭圆的中心|
|[CD2DRadialGradientBrush：： GetGradientOriginOffset](#getgradientoriginoffset)|检索渐变原点相对于渐变椭圆中心的偏移量|
|[CD2DRadialGradientBrush：： GetRadiusX](#getradiusx)|检索渐变椭圆的 x 轴半径|
|[CD2DRadialGradientBrush：： GetRadiusY](#getradiusy)|检索渐变椭圆的 y 轴半径|
|[CD2DRadialGradientBrush：： SetCenter](#setcenter)|指定画笔坐标空间中渐变椭圆的中心|
|[CD2DRadialGradientBrush：： SetGradientOriginOffset](#setgradientoriginoffset)|指定梯度原点相对于渐变椭圆中心的偏移量|
|[CD2DRadialGradientBrush：： SetRadiusX](#setradiusx)|指定画笔坐标空间中渐变椭圆的 x 轴半径|
|[CD2DRadialGradientBrush：： SetRadiusY](#setradiusy)|指定画笔坐标空间中渐变椭圆的 y 轴半径|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CD2DRadialGradientBrush：： operator ID2D1RadialGradientBrush *](#operator_id2d1radialgradientbrush_star)|返回 ID2D1RadialGradientBrush 接口|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CD2DRadialGradientBrush：： m_pRadialGradientBrush](#m_pradialgradientbrush)|指向 ID2D1RadialGradientBrush 的指针。|
|[CD2DRadialGradientBrush：： m_RadialGradientBrushProperties](#m_radialgradientbrushproperties)|画笔渐变的中心、梯度源偏移量和 x 轴半径和 y 轴半径。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

[CD2DGradientBrush](../../mfc/reference/cd2dgradientbrush-class.md)

`CD2DRadialGradientBrush`

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="_dtorcd2dradialgradientbrush"></a> CD2DRadialGradientBrush：： ~ CD2DRadialGradientBrush

析构函数。 当 D2D 放射梯度画笔对象被销毁时调用。

```
virtual ~CD2DRadialGradientBrush();
```

## <a name="cd2dradialgradientbrushattach"></a><a name="attach"></a> CD2DRadialGradientBrush：： Attach

将现有资源接口附加到对象

```cpp
void Attach(ID2D1RadialGradientBrush* pResource);
```

### <a name="parameters"></a>parameters

*pResource*<br/>
现有的资源接口。 不能为 NULL

## <a name="cd2dradialgradientbrushcd2dradialgradientbrush"></a><a name="cd2dradialgradientbrush"></a> CD2DRadialGradientBrush：： CD2DRadialGradientBrush

构造 CD2DLinearGradientBrush 对象。

```
CD2DRadialGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
    D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES RadialGradientBrushProperties,
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

*RadialGradientBrushProperties*<br/>
画笔渐变的中心、梯度源偏移量和 x 轴半径和 y 轴半径。

*colorInterpolationGamma*<br/>
执行梯度停止点之间的颜色插值的空间。

*extendMode*<br/>
[0，1] 标准化范围外的渐变的行为。

*pBrushProperties*<br/>
指向画笔的不透明度和转换的指针。

*bAutoDestroy*<br/>
指示对象将被所有者 (pParentTarget) 销毁。

## <a name="cd2dradialgradientbrushcreate"></a><a name="create"></a> CD2DRadialGradientBrush：： Create

创建 CD2DRadialGradientBrush。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>parameters

*pRenderTarget*<br/>
指向呈现器目标的指针。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="cd2dradialgradientbrushdestroy"></a><a name="destroy"></a> CD2DRadialGradientBrush：:D estroy

销毁 CD2DRadialGradientBrush 对象。

```
virtual void Destroy();
```

## <a name="cd2dradialgradientbrushdetach"></a><a name="detach"></a> CD2DRadialGradientBrush：:D etach

从对象分离资源接口

```
ID2D1RadialGradientBrush* Detach();
```

### <a name="return-value"></a>返回值

指向已分离资源接口的指针。

## <a name="cd2dradialgradientbrushget"></a><a name="get"></a> CD2DRadialGradientBrush：： Get

返回 ID2D1RadialGradientBrush 接口

```
ID2D1RadialGradientBrush* Get();
```

### <a name="return-value"></a>返回值

指向 ID2D1RadialGradientBrush 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dradialgradientbrushgetcenter"></a><a name="getcenter"></a> CD2DRadialGradientBrush：： GetCenter

检索渐变椭圆的中心

```
CD2DPointF GetCenter() const;
```

### <a name="return-value"></a>返回值

渐变椭圆的中心。 此值在画笔的坐标空间中表示

## <a name="cd2dradialgradientbrushgetgradientoriginoffset"></a><a name="getgradientoriginoffset"></a> CD2DRadialGradientBrush：： GetGradientOriginOffset

检索渐变原点相对于渐变椭圆中心的偏移量

```
CD2DPointF GetGradientOriginOffset() const;
```

### <a name="return-value"></a>返回值

渐变原点相对于渐变椭圆的中心的偏移量。 此值在画笔的坐标空间中表示

## <a name="cd2dradialgradientbrushgetradiusx"></a><a name="getradiusx"></a> CD2DRadialGradientBrush：： GetRadiusX

检索渐变椭圆的 x 轴半径

```
FLOAT GetRadiusX() const;
```

### <a name="return-value"></a>返回值

渐变椭圆的 x 轴半径。 此值在画笔的坐标空间中表示

## <a name="cd2dradialgradientbrushgetradiusy"></a><a name="getradiusy"></a> CD2DRadialGradientBrush：： GetRadiusY

检索渐变椭圆的 y 轴半径

```
FLOAT GetRadiusY() const;
```

### <a name="return-value"></a>返回值

渐变椭圆的 y 轴半径。 此值在画笔的坐标空间中表示

## <a name="cd2dradialgradientbrushm_pradialgradientbrush"></a><a name="m_pradialgradientbrush"></a> CD2DRadialGradientBrush：： m_pRadialGradientBrush

指向 ID2D1RadialGradientBrush 的指针。

```
ID2D1RadialGradientBrush* m_pRadialGradientBrush;
```

## <a name="cd2dradialgradientbrushm_radialgradientbrushproperties"></a><a name="m_radialgradientbrushproperties"></a> CD2DRadialGradientBrush：： m_RadialGradientBrushProperties

画笔渐变的中心、梯度源偏移量和 x 轴半径和 y 轴半径。

```
D2D1_RADIAL_GRADIENT_BRUSH_PROPERTIES m_RadialGradientBrushProperties;
```

## <a name="cd2dradialgradientbrushoperator-id2d1radialgradientbrush"></a><a name="operator_id2d1radialgradientbrush_star"></a> CD2DRadialGradientBrush：： operator ID2D1RadialGradientBrush *

返回 ID2D1RadialGradientBrush 接口

```
operator ID2D1RadialGradientBrush*();
```

### <a name="return-value"></a>返回值

指向 ID2D1RadialGradientBrush 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dradialgradientbrushsetcenter"></a><a name="setcenter"></a> CD2DRadialGradientBrush：： SetCenter

指定画笔坐标空间中渐变椭圆的中心

```cpp
void SetCenter(CD2DPointF point);
```

### <a name="parameters"></a>parameters

*情况*<br/>
画笔坐标空间中渐变椭圆的中心

## <a name="cd2dradialgradientbrushsetgradientoriginoffset"></a><a name="setgradientoriginoffset"></a> CD2DRadialGradientBrush：： SetGradientOriginOffset

指定梯度原点相对于渐变椭圆中心的偏移量

```cpp
void SetGradientOriginOffset(CD2DPointF gradientOriginOffset);
```

### <a name="parameters"></a>parameters

*gradientOriginOffset*<br/>
相对于渐变椭圆中心的渐变原点的偏移量

## <a name="cd2dradialgradientbrushsetradiusx"></a><a name="setradiusx"></a> CD2DRadialGradientBrush：： SetRadiusX

指定画笔坐标空间中渐变椭圆的 x 轴半径

```cpp
void SetRadiusX(FLOAT radiusX);
```

### <a name="parameters"></a>parameters

*radiusX*<br/>
渐变椭圆的 x 轴半径。 此值位于画笔的坐标空间中

## <a name="cd2dradialgradientbrushsetradiusy"></a><a name="setradiusy"></a> CD2DRadialGradientBrush：： SetRadiusY

指定画笔坐标空间中渐变椭圆的 y 轴半径

```cpp
void SetRadiusY(FLOAT radiusY);
```

### <a name="parameters"></a>parameters

*radiusY*<br/>
渐变椭圆的 y 轴半径。 此值位于画笔的坐标空间中

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
