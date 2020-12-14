---
description: 了解详细信息： CD2DGradientBrush 类
title: CD2DGradientBrush 类
ms.date: 03/27/2019
f1_keywords:
- CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::CD2DGradientBrush
- AFXRENDERTARGET/CD2DGradientBrush::Destroy
- AFXRENDERTARGET/CD2DGradientBrush::m_arGradientStops
- AFXRENDERTARGET/CD2DGradientBrush::m_colorInterpolationGamma
- AFXRENDERTARGET/CD2DGradientBrush::m_extendMode
- AFXRENDERTARGET/CD2DGradientBrush::m_pGradientStops
helpviewer_keywords:
- CD2DGradientBrush [MFC], CD2DGradientBrush
- CD2DGradientBrush [MFC], Destroy
- CD2DGradientBrush [MFC], m_arGradientStops
- CD2DGradientBrush [MFC], m_colorInterpolationGamma
- CD2DGradientBrush [MFC], m_extendMode
- CD2DGradientBrush [MFC], m_pGradientStops
ms.assetid: 5bf133e6-16b7-4e3a-845d-0ce63fafe5ec
ms.openlocfilehash: c1af08ae27bd2cbee48c4abe22f413ffeb85cd1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193391"
---
# <a name="cd2dgradientbrush-class"></a>CD2DGradientBrush 类

CD2DLinearGradientBrush 和 CD2DRadialGradientBrush 类的基类。

## <a name="syntax"></a>语法

```
class CD2DGradientBrush : public CD2DBrush;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CD2DGradientBrush：： CD2DGradientBrush](#cd2dgradientbrush)|构造 CD2DGradientBrush 对象。|
|[CD2DGradientBrush：： ~ CD2DGradientBrush](#_dtorcd2dgradientbrush)|析构函数。 当 D2D 渐变画笔对象被销毁时调用。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CD2DGradientBrush：:D estroy](#destroy)|销毁 CD2DGradientBrush 对象。  (重写 [CD2DBrush：:D estroy](../../mfc/reference/cd2dbrush-class.md#destroy)。 ) |

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CD2DGradientBrush：： m_arGradientStops](#m_argradientstops)|D2D1_GRADIENT_STOP 结构的数组。|
|[CD2DGradientBrush：： m_colorInterpolationGamma](#m_colorinterpolationgamma)|执行梯度停止点之间的颜色插值的空间。|
|[CD2DGradientBrush：： m_extendMode](#m_extendmode)|[0，1] 标准化范围外的渐变的行为。|
|[CD2DGradientBrush：： m_pGradientStops](#m_pgradientstops)|指向 D2D1_GRADIENT_STOP 结构的数组的指针。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

`CD2DGradientBrush`

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2dgradientbrushcd2dgradientbrush"></a><a name="_dtorcd2dgradientbrush"></a> CD2DGradientBrush：： ~ CD2DGradientBrush

析构函数。 当 D2D 渐变画笔对象被销毁时调用。

```
virtual ~CD2DGradientBrush();
```

## <a name="cd2dgradientbrushcd2dgradientbrush"></a><a name="cd2dgradientbrush"></a> CD2DGradientBrush：： CD2DGradientBrush

构造 CD2DGradientBrush 对象。

```
CD2DGradientBrush(
    CRenderTarget* pParentTarget,
    const D2D1_GRADIENT_STOP* gradientStops,
    UINT gradientStopsCount,
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

*colorInterpolationGamma*<br/>
执行梯度停止点之间的颜色插值的空间。

*extendMode*<br/>
[0，1] 标准化范围外的渐变的行为。

*pBrushProperties*<br/>
指向画笔的不透明度和转换的指针。

*bAutoDestroy*<br/>
指示对象将被所有者 (pParentTarget) 销毁。

## <a name="cd2dgradientbrushdestroy"></a><a name="destroy"></a> CD2DGradientBrush：:D estroy

销毁 CD2DGradientBrush 对象。

```
virtual void Destroy();
```

## <a name="cd2dgradientbrushm_argradientstops"></a><a name="m_argradientstops"></a> CD2DGradientBrush：： m_arGradientStops

D2D1_GRADIENT_STOP 结构的数组。

```
CArray<D2D1_GRADIENT_STOP, D2D1_GRADIENT_STOP> m_arGradientStops;
```

## <a name="cd2dgradientbrushm_colorinterpolationgamma"></a><a name="m_colorinterpolationgamma"></a> CD2DGradientBrush：： m_colorInterpolationGamma

执行梯度停止点之间的颜色插值的空间。

```
D2D1_GAMMA m_colorInterpolationGamma;
```

## <a name="cd2dgradientbrushm_extendmode"></a><a name="m_extendmode"></a> CD2DGradientBrush：： m_extendMode

[0，1] 标准化范围外的渐变的行为。

```
D2D1_EXTEND_MODE m_extendMode;
```

## <a name="cd2dgradientbrushm_pgradientstops"></a><a name="m_pgradientstops"></a> CD2DGradientBrush：： m_pGradientStops

指向 D2D1_GRADIENT_STOP 结构的数组的指针。

```
ID2D1GradientStopCollection* m_pGradientStops;
```

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
