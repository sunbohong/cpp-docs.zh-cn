---
description: 了解详细信息： CD2DBitmapBrush 类
title: CD2DBitmapBrush 类
ms.date: 11/04/2016
f1_keywords:
- CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::CD2DBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::Attach
- AFXRENDERTARGET/CD2DBitmapBrush::Create
- AFXRENDERTARGET/CD2DBitmapBrush::Destroy
- AFXRENDERTARGET/CD2DBitmapBrush::Detach
- AFXRENDERTARGET/CD2DBitmapBrush::Get
- AFXRENDERTARGET/CD2DBitmapBrush::GetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::GetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::GetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::SetBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeX
- AFXRENDERTARGET/CD2DBitmapBrush::SetExtendModeY
- AFXRENDERTARGET/CD2DBitmapBrush::SetInterpolationMode
- AFXRENDERTARGET/CD2DBitmapBrush::CommonInit
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmap
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrush
- AFXRENDERTARGET/CD2DBitmapBrush::m_pBitmapBrushProperties
helpviewer_keywords:
- CD2DBitmapBrush [MFC], CD2DBitmapBrush
- CD2DBitmapBrush [MFC], Attach
- CD2DBitmapBrush [MFC], Create
- CD2DBitmapBrush [MFC], Destroy
- CD2DBitmapBrush [MFC], Detach
- CD2DBitmapBrush [MFC], Get
- CD2DBitmapBrush [MFC], GetBitmap
- CD2DBitmapBrush [MFC], GetExtendModeX
- CD2DBitmapBrush [MFC], GetExtendModeY
- CD2DBitmapBrush [MFC], GetInterpolationMode
- CD2DBitmapBrush [MFC], SetBitmap
- CD2DBitmapBrush [MFC], SetExtendModeX
- CD2DBitmapBrush [MFC], SetExtendModeY
- CD2DBitmapBrush [MFC], SetInterpolationMode
- CD2DBitmapBrush [MFC], CommonInit
- CD2DBitmapBrush [MFC], m_pBitmap
- CD2DBitmapBrush [MFC], m_pBitmapBrush
- CD2DBitmapBrush [MFC], m_pBitmapBrushProperties
ms.assetid: 46ebbe34-66e0-44c8-af1d-d129e851de5e
ms.openlocfilehash: a9d4c1955b1318ecb273482cd49025090bf97d3d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227580"
---
# <a name="cd2dbitmapbrush-class"></a>CD2DBitmapBrush 类

ID2D1BitmapBrush 的包装器。

## <a name="syntax"></a>语法

```
class CD2DBitmapBrush : public CD2DBrush;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CD2DBitmapBrush：： CD2DBitmapBrush](#cd2dbitmapbrush)|已重载。 从文件构造 CD2DBitmapBrush 对象。|
|[CD2DBitmapBrush：： ~ CD2DBitmapBrush](#dtor)|析构函数。 当 D2D 位图画笔对象被销毁时调用。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CD2DBitmapBrush：： Attach](#attach)|将现有资源接口附加到对象|
|[CD2DBitmapBrush：： Create](#create)|创建 CD2DBitmapBrush。  (重写 [CD2DResource：： Create](../../mfc/reference/cd2dresource-class.md#create). ) |
|[CD2DBitmapBrush：:D estroy](#destroy)|销毁 CD2DBitmapBrush 对象。  (重写 [CD2DBrush：:D estroy](../../mfc/reference/cd2dbrush-class.md#destroy)。 ) |
|[CD2DBitmapBrush：:D etach](#detach)|从对象分离资源接口|
|[CD2DBitmapBrush：： Get](#get)|返回 ID2D1BitmapBrush 接口|
|[CD2DBitmapBrush：： GetBitmap](#getbitmap)|获取此画笔用于绘制的位图源|
|[CD2DBitmapBrush：： GetExtendModeX](#getextendmodex)|获取画笔水平平铺那些超出其位图的区域的方法|
|[CD2DBitmapBrush：： GetExtendModeY](#getextendmodey)|获取画笔用于垂直平铺超出其位图的区域的方法|
|[CD2DBitmapBrush：： GetInterpolationMode](#getinterpolationmode)|获取缩放或旋转画笔位图时使用的内插方法|
|[CD2DBitmapBrush：： SetBitmap](#setbitmap)|指定此画笔用于绘制的位图源|
|[CD2DBitmapBrush：： SetExtendModeX](#setextendmodex)|指定画笔如何水平平铺那些超出其位图的区域|
|[CD2DBitmapBrush：： SetExtendModeY](#setextendmodey)|指定画笔如何垂直平铺超出其位图的区域|
|[CD2DBitmapBrush：： SetInterpolationMode](#setinterpolationmode)|指定在缩放或旋转画笔位图时使用的内插模式|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CD2DBitmapBrush：： CommonInit](#commoninit)|初始化对象|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CD2DBitmapBrush：： operator ID2D1BitmapBrush *](#operator_id2d1bitmapbrush_star)|返回 ID2D1BitmapBrush 接口|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CD2DBitmapBrush：： m_pBitmap](#m_pbitmap)|存储指向 CD2DBitmap 对象的指针。|
|[CD2DBitmapBrush：： m_pBitmapBrush](#m_pbitmapbrush)|存储指向 ID2D1BitmapBrush 对象的指针。|
|[CD2DBitmapBrush：： m_pBitmapBrushProperties](#m_pbitmapbrushproperties)|位图画笔属性。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DBrush](../../mfc/reference/cd2dbrush-class.md)

`CD2DBitmapBrush`

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2dbitmapbrushcd2dbitmapbrush"></a><a name="dtor"></a> CD2DBitmapBrush：： ~ CD2DBitmapBrush

析构函数。 当 D2D 位图画笔对象被销毁时调用。

```
virtual ~CD2DBitmapBrush();
```

## <a name="cd2dbitmapbrushattach"></a><a name="attach"></a> CD2DBitmapBrush：： Attach

将现有资源接口附加到对象

```cpp
void Attach(ID2D1BitmapBrush* pResource);
```

### <a name="parameters"></a>parameters

*pResource*<br/>
现有的资源接口。 不能为 NULL

## <a name="cd2dbitmapbrushcd2dbitmapbrush"></a><a name="cd2dbitmapbrush"></a> CD2DBitmapBrush：： CD2DBitmapBrush

构造 CD2DBitmapBrush 对象。

```
CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    UINT uiResID,
    LPCTSTR lpszType = NULL,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);

CD2DBitmapBrush(
    CRenderTarget* pParentTarget,
    LPCTSTR lpszImagePath,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties = NULL,
    CD2DBrushProperties* pBrushProperties = NULL,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>parameters

*pParentTarget*<br/>
指向呈现器目标的指针。

*pBitmapBrushProperties*<br/>
指向 "扩展模式" 和位图画笔内插模式的指针。

*pBrushProperties*<br/>
指向画笔的不透明度和转换的指针。

*bAutoDestroy*<br/>
指示对象将被所有者 (pParentTarget) 销毁。

*uiResID*<br/>
资源的资源 ID 号。

*lpszType*<br/>
指向以 null 结尾的字符串的指针，该字符串包含资源类型。

*sizeDest*<br/>
位图的目标大小。

*lpszImagePath*<br/>
指向以 null 结尾的字符串的指针，该字符串包含文件的名称。

## <a name="cd2dbitmapbrushcommoninit"></a><a name="commoninit"></a> CD2DBitmapBrush：： CommonInit

初始化对象

```cpp
void CommonInit(D2D1_BITMAP_BRUSH_PROPERTIES* pBitmapBrushProperties);
```

### <a name="parameters"></a>parameters

*pBitmapBrushProperties*<br/>
指向位图画笔属性的指针。

## <a name="cd2dbitmapbrushcreate"></a><a name="create"></a> CD2DBitmapBrush：： Create

创建 CD2DBitmapBrush。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>parameters

*pRenderTarget*<br/>
指向呈现器目标的指针。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="cd2dbitmapbrushdestroy"></a><a name="destroy"></a> CD2DBitmapBrush：:D estroy

销毁 CD2DBitmapBrush 对象。

```
virtual void Destroy();
```

## <a name="cd2dbitmapbrushdetach"></a><a name="detach"></a> CD2DBitmapBrush：:D etach

从对象分离资源接口

```
ID2D1BitmapBrush* Detach();
```

### <a name="return-value"></a>返回值

指向已分离资源接口的指针。

## <a name="cd2dbitmapbrushget"></a><a name="get"></a> CD2DBitmapBrush：： Get

返回 ID2D1BitmapBrush 接口

```
ID2D1BitmapBrush* Get();
```

### <a name="return-value"></a>返回值

指向 ID2D1BitmapBrush 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dbitmapbrushgetbitmap"></a><a name="getbitmap"></a> CD2DBitmapBrush：： GetBitmap

获取此画笔用于绘制的位图源

```
CD2DBitmap* GetBitmap();
```

### <a name="return-value"></a>返回值

指向 CD2DBitmap 对象的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dbitmapbrushgetextendmodex"></a><a name="getextendmodex"></a> CD2DBitmapBrush：： GetExtendModeX

获取画笔水平平铺那些超出其位图的区域的方法

```
D2D1_EXTEND_MODE GetExtendModeX() const;
```

### <a name="return-value"></a>返回值

一个值，该值指定画笔如何水平平铺那些超出其位图的区域

## <a name="cd2dbitmapbrushgetextendmodey"></a><a name="getextendmodey"></a> CD2DBitmapBrush：： GetExtendModeY

获取画笔用于垂直平铺超出其位图的区域的方法

```
D2D1_EXTEND_MODE GetExtendModeY() const;
```

### <a name="return-value"></a>返回值

一个值，该值指定画笔如何垂直平铺超出其位图的区域

## <a name="cd2dbitmapbrushgetinterpolationmode"></a><a name="getinterpolationmode"></a> CD2DBitmapBrush：： GetInterpolationMode

获取缩放或旋转画笔位图时使用的内插方法

```
D2D1_BITMAP_INTERPOLATION_MODE GetInterpolationMode() const;
```

### <a name="return-value"></a>返回值

缩放或旋转画笔位图时使用的内插方法

## <a name="cd2dbitmapbrushm_pbitmap"></a><a name="m_pbitmap"></a> CD2DBitmapBrush：： m_pBitmap

存储指向 CD2DBitmap 对象的指针。

```
CD2DBitmap* m_pBitmap;
```

## <a name="cd2dbitmapbrushm_pbitmapbrush"></a><a name="m_pbitmapbrush"></a> CD2DBitmapBrush：： m_pBitmapBrush

存储指向 ID2D1BitmapBrush 对象的指针。

```
ID2D1BitmapBrush* m_pBitmapBrush;
```

## <a name="cd2dbitmapbrushm_pbitmapbrushproperties"></a><a name="m_pbitmapbrushproperties"></a> CD2DBitmapBrush：： m_pBitmapBrushProperties

位图画笔属性。

```
D2D1_BITMAP_BRUSH_PROPERTIES* m_pBitmapBrushProperties;
```

## <a name="cd2dbitmapbrushoperator-id2d1bitmapbrush"></a><a name="operator_id2d1bitmapbrush_star"></a> CD2DBitmapBrush：： operator ID2D1BitmapBrush *

返回 ID2D1BitmapBrush 接口

```
operator ID2D1BitmapBrush*();
```

### <a name="return-value"></a>返回值

指向 ID2D1BitmapBrush 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dbitmapbrushsetbitmap"></a><a name="setbitmap"></a> CD2DBitmapBrush：： SetBitmap

指定此画笔用于绘制的位图源

```cpp
void SetBitmap(CD2DBitmap* pBitmap);
```

### <a name="parameters"></a>parameters

*pBitmap*<br/>
画笔使用的位图源

## <a name="cd2dbitmapbrushsetextendmodex"></a><a name="setextendmodex"></a> CD2DBitmapBrush：： SetExtendModeX

指定画笔如何水平平铺那些超出其位图的区域

```cpp
void SetExtendModeX(D2D1_EXTEND_MODE extendModeX);
```

### <a name="parameters"></a>parameters

*extendModeX*<br/>
一个值，该值指定画笔如何水平平铺那些超出其位图的区域

## <a name="cd2dbitmapbrushsetextendmodey"></a><a name="setextendmodey"></a> CD2DBitmapBrush：： SetExtendModeY

指定画笔如何垂直平铺超出其位图的区域

```cpp
void SetExtendModeY(D2D1_EXTEND_MODE extendModeY);
```

### <a name="parameters"></a>parameters

*extendModeY*<br/>
一个值，该值指定画笔如何垂直平铺超出其位图的区域

## <a name="cd2dbitmapbrushsetinterpolationmode"></a><a name="setinterpolationmode"></a> CD2DBitmapBrush：： SetInterpolationMode

指定在缩放或旋转画笔位图时使用的内插模式

```cpp
void SetInterpolationMode(D2D1_BITMAP_INTERPOLATION_MODE interpolationMode);
```

### <a name="parameters"></a>parameters

*interpolationMode*<br/>
缩放或旋转画笔位图时使用的内插模式

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
