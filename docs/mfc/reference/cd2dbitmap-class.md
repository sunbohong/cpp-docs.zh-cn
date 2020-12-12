---
description: 了解详细信息： CD2DBitmap 类
title: CD2DBitmap 类
ms.date: 11/04/2016
f1_keywords:
- CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::CD2DBitmap
- AFXRENDERTARGET/CD2DBitmap::Attach
- AFXRENDERTARGET/CD2DBitmap::CopyFromBitmap
- AFXRENDERTARGET/CD2DBitmap::CopyFromMemory
- AFXRENDERTARGET/CD2DBitmap::CopyFromRenderTarget
- AFXRENDERTARGET/CD2DBitmap::Create
- AFXRENDERTARGET/CD2DBitmap::Destroy
- AFXRENDERTARGET/CD2DBitmap::Detach
- AFXRENDERTARGET/CD2DBitmap::Get
- AFXRENDERTARGET/CD2DBitmap::GetDPI
- AFXRENDERTARGET/CD2DBitmap::GetPixelFormat
- AFXRENDERTARGET/CD2DBitmap::GetPixelSize
- AFXRENDERTARGET/CD2DBitmap::GetSize
- AFXRENDERTARGET/CD2DBitmap::IsValid
- AFXRENDERTARGET/CD2DBitmap::CommonInit
- AFXRENDERTARGET/CD2DBitmap::m_bAutoDestroyHBMP
- AFXRENDERTARGET/CD2DBitmap::m_hBmpSrc
- AFXRENDERTARGET/CD2DBitmap::m_lpszType
- AFXRENDERTARGET/CD2DBitmap::m_pBitmap
- AFXRENDERTARGET/CD2DBitmap::m_sizeDest
- AFXRENDERTARGET/CD2DBitmap::m_strPath
- AFXRENDERTARGET/CD2DBitmap::m_uiResID
helpviewer_keywords:
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], CD2DBitmap
- CD2DBitmap [MFC], Attach
- CD2DBitmap [MFC], CopyFromBitmap
- CD2DBitmap [MFC], CopyFromMemory
- CD2DBitmap [MFC], CopyFromRenderTarget
- CD2DBitmap [MFC], Create
- CD2DBitmap [MFC], Destroy
- CD2DBitmap [MFC], Detach
- CD2DBitmap [MFC], Get
- CD2DBitmap [MFC], GetDPI
- CD2DBitmap [MFC], GetPixelFormat
- CD2DBitmap [MFC], GetPixelSize
- CD2DBitmap [MFC], GetSize
- CD2DBitmap [MFC], IsValid
- CD2DBitmap [MFC], CommonInit
- CD2DBitmap [MFC], m_bAutoDestroyHBMP
- CD2DBitmap [MFC], m_hBmpSrc
- CD2DBitmap [MFC], m_lpszType
- CD2DBitmap [MFC], m_pBitmap
- CD2DBitmap [MFC], m_sizeDest
- CD2DBitmap [MFC], m_strPath
- CD2DBitmap [MFC], m_uiResID
ms.assetid: 2b3686f1-812c-462b-b449-9f0cb6949bf6
ms.openlocfilehash: ab023caa92683b24098db1a03d081922e3dfd48b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227645"
---
# <a name="cd2dbitmap-class"></a>CD2DBitmap 类

ID2D1Bitmap 的包装器。

## <a name="syntax"></a>语法

```
class CD2DBitmap : public CD2DResource;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CD2DBitmap：： CD2DBitmap](#cd2dbitmap)|已重载。 从 HBITMAP 构造 CD2DBitmap 对象。|
|[CD2DBitmap：： ~ CD2DBitmap](#_dtorcd2dbitmap)|析构函数。 当 D2D 位图对象被销毁时调用。|

### <a name="protected-constructors"></a>受保护的构造函数

|名称|描述|
|----------|-----------------|
|[CD2DBitmap：： CD2DBitmap](#cd2dbitmap)|已重载。 构造 CD2DBitmap 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CD2DBitmap：： Attach](#attach)|将现有资源接口附加到对象|
|[CD2DBitmap：： CopyFromBitmap](#copyfrombitmap)|将指定的区域从指定的位图复制到当前位图|
|[CD2DBitmap：： CopyFromMemory](#copyfrommemory)|将指定区域从内存复制到当前位图|
|[CD2DBitmap：： CopyFromRenderTarget](#copyfromrendertarget)|将指定的区域从指定的呈现器目标复制到当前位图|
|[CD2DBitmap：： Create](#create)|创建 CD2DBitmap。  (重写 [CD2DResource：： Create](../../mfc/reference/cd2dresource-class.md#create). ) |
|[CD2DBitmap：:D estroy](#destroy)|销毁 CD2DBitmap 对象。  (重写 [CD2DResource：:D estroy](../../mfc/reference/cd2dresource-class.md#destroy)。 ) |
|[CD2DBitmap：:D etach](#detach)|从对象分离资源接口|
|[CD2DBitmap：： Get](#get)|返回 ID2D1Bitmap 接口|
|[CD2DBitmap：： GetDPI](#getdpi)|返回位图 (DPI) 的每英寸点数|
|[CD2DBitmap：： GetPixelFormat](#getpixelformat)|检索位图的像素格式和 alpha 模式|
|[CD2DBitmap：： GetPixelSize](#getpixelsize)|返回位图的大小，以设备相关单位 (像素) |
|[CD2DBitmap：： GetSize](#getsize)|返回位图的大小（以与设备无关的像素为单位） (Dip) |
|[CD2DBitmap：： IsValid](#isvalid)|检查资源有效性 (重写 [CD2DResource：： IsValid](../../mfc/reference/cd2dresource-class.md#isvalid). ) |

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CD2DBitmap：： CommonInit](#commoninit)|初始化对象|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CD2DBitmap：： operator ID2D1Bitmap *](#operator_id2d1bitmap_star)|返回 ID2D1Bitmap 接口|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CD2DBitmap：： m_bAutoDestroyHBMP](#m_bautodestroyhbmp)|如果应销毁 m_hBmpSrc，则为 TRUE;否则为 FALSE。|
|[CD2DBitmap：： m_hBmpSrc](#m_hbmpsrc)|源位图句柄。|
|[CD2DBitmap：： m_lpszType](#m_lpsztype)|资源类型。|
|[CD2DBitmap：： m_pBitmap](#m_pbitmap)|存储指向 ID2D1Bitmap 对象的指针。|
|[CD2DBitmap：： m_sizeDest](#m_sizedest)|位图目标大小。|
|[CD2DBitmap：： m_strPath](#m_strpath)|Botmap 文件路径。|
|[CD2DBitmap：： m_uiResID](#m_uiresid)|位图资源 ID。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DBitmap`

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2dbitmapcd2dbitmap"></a><a name="_dtorcd2dbitmap"></a> CD2DBitmap：： ~ CD2DBitmap

析构函数。 当 D2D 位图对象被销毁时调用。

```
virtual ~CD2DBitmap();
```

## <a name="cd2dbitmapattach"></a><a name="attach"></a> CD2DBitmap：： Attach

将现有的资源接口附加到对象。

```cpp
void Attach(ID2D1Bitmap* pResource);
```

### <a name="parameters"></a>parameters

*pResource*<br/>
现有的资源接口。 不能为 NULL。

## <a name="cd2dbitmapcd2dbitmap"></a><a name="cd2dbitmap"></a> CD2DBitmap：： CD2DBitmap

从资源构造 CD2DBitmap 对象。

```
CD2DBitmap(
    CRenderTarget* pParentTarget,
    UINT uiResID,
    LPCTSTR lpszType = NULL,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    LPCTSTR lpszPath,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    HBITMAP hbmpSrc,
    CD2DSizeU sizeDest = CD2DSizeU(0, 0),
    BOOL bAutoDestroy = TRUE);

CD2DBitmap(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>parameters

*pParentTarget*<br/>
指向呈现器目标的指针。

*uiResID*<br/>
资源的资源 ID 号。

*lpszType*<br/>
指向以 null 结尾的字符串的指针，该字符串包含资源类型。

*sizeDest*<br/>
位图的目标大小。

*bAutoDestroy*<br/>
指示对象将被所有者 (pParentTarget) 销毁。

*lpszPath*<br/>
指向以 null 结尾的字符串的指针，该字符串包含文件的名称。

*hbmpSrc*<br/>
位图的句柄。

## <a name="cd2dbitmapcommoninit"></a><a name="commoninit"></a> CD2DBitmap：： CommonInit

初始化对象。

```cpp
void CommonInit();
```

## <a name="cd2dbitmapcopyfrombitmap"></a><a name="copyfrombitmap"></a> CD2DBitmap：： CopyFromBitmap

将指定的区域从指定的位图复制到当前位图。

```
HRESULT CopyFromBitmap(
    const CD2DBitmap* pBitmap,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>parameters

*pBitmap*<br/>
要从中进行复制的位图。

*destPoint*<br/>
在当前位图中，将 srcRect 指定的区域复制到的区域的左上角。

*srcRect*<br/>
要复制的位图区域。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="cd2dbitmapcopyfrommemory"></a><a name="copyfrommemory"></a> CD2DBitmap：： CopyFromMemory

将指定区域从内存复制到当前位图。

```
HRESULT CopyFromMemory(
    const void* srcData,
    UINT32 pitch,
    const CD2DRectU* destRect = NULL);
```

### <a name="parameters"></a>parameters

*srcData*<br/>
要复制的数据。

*推广*<br/>
存储在 srcData 中的源位图的跨距或音调。 跨距是内存) 中一行 (一个像素的字节计数。 跨距可以从以下公式计算得出：像素宽 \* 字节/像素 + 内存填充。

*destRect*<br/>
在当前位图中，将 srcRect 指定的区域复制到的区域的左上角。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="cd2dbitmapcopyfromrendertarget"></a><a name="copyfromrendertarget"></a> CD2DBitmap：： CopyFromRenderTarget

将指定的区域从指定的呈现器目标复制到当前位图。

```
HRESULT CopyFromRenderTarget(
    const CRenderTarget* pRenderTarget,
    const CD2DPointU* destPoint = NULL,
    const CD2DRectU* srcRect = NULL);
```

### <a name="parameters"></a>parameters

*pRenderTarget*<br/>
包含要复制的区域的呈现器目标。

*destPoint*<br/>
在当前位图中，将 srcRect 指定的区域复制到的区域的左上角。

*srcRect*<br/>
要复制的 renderTarget 的区域。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="cd2dbitmapcreate"></a><a name="create"></a> CD2DBitmap：： Create

创建 CD2DBitmap。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>parameters

*pRenderTarget*<br/>
指向呈现器目标的指针。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="cd2dbitmapdestroy"></a><a name="destroy"></a> CD2DBitmap：:D estroy

销毁 CD2DBitmap 对象。

```
virtual void Destroy();
```

## <a name="cd2dbitmapdetach"></a><a name="detach"></a> CD2DBitmap：:D etach

从对象分离资源接口。

```
ID2D1Bitmap* Detach();
```

### <a name="return-value"></a>返回值

指向已分离资源接口的指针。

## <a name="cd2dbitmapget"></a><a name="get"></a> CD2DBitmap：： Get

返回 ID2D1Bitmap 接口。

```
ID2D1Bitmap* Get();
```

### <a name="return-value"></a>返回值

指向 ID2D1Bitmap 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dbitmapgetdpi"></a><a name="getdpi"></a> CD2DBitmap：： GetDPI

返回位图 (DPI) 的每英寸点数。

```
CD2DSizeF GetDPI() const;
```

### <a name="return-value"></a>返回值

位图的水平和垂直 DPI。

## <a name="cd2dbitmapgetpixelformat"></a><a name="getpixelformat"></a> CD2DBitmap：： GetPixelFormat

检索位图的像素格式和 alpha 模式

```
D2D1_PIXEL_FORMAT GetPixelFormat() const;
```

### <a name="return-value"></a>返回值

位图的像素格式和 alpha 模式。

## <a name="cd2dbitmapgetpixelsize"></a><a name="getpixelsize"></a> CD2DBitmap：： GetPixelSize

返回位图的大小，以与设备相关的单位 (像素) 。

```
CD2DSizeU GetPixelSize() const;
```

### <a name="return-value"></a>返回值

位图的大小（以像素为单位）。

## <a name="cd2dbitmapgetsize"></a><a name="getsize"></a> CD2DBitmap：： GetSize

返回位图的大小（以与设备无关的像素为单位） (Dip) 。

```
CD2DSizeF GetSize() const;
```

### <a name="return-value"></a>返回值

位图的大小（以 Dip 为限）。

## <a name="cd2dbitmapisvalid"></a><a name="isvalid"></a> CD2DBitmap：： IsValid

检查资源有效性。

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>返回值

如果资源有效，则为 TRUE;否则为 FALSE。

## <a name="cd2dbitmapm_bautodestroyhbmp"></a><a name="m_bautodestroyhbmp"></a> CD2DBitmap：： m_bAutoDestroyHBMP

如果应销毁 m_hBmpSrc，则为 TRUE;否则为 FALSE。

```
BOOL m_bAutoDestroyHBMP;
```

## <a name="cd2dbitmapm_hbmpsrc"></a><a name="m_hbmpsrc"></a> CD2DBitmap：： m_hBmpSrc

源位图句柄。

```
HBITMAP m_hBmpSrc;
```

## <a name="cd2dbitmapm_lpsztype"></a><a name="m_lpsztype"></a> CD2DBitmap：： m_lpszType

资源类型。

```
LPCTSTR m_lpszType;
```

## <a name="cd2dbitmapm_pbitmap"></a><a name="m_pbitmap"></a> CD2DBitmap：： m_pBitmap

存储指向 ID2D1Bitmap 对象的指针。

```
ID2D1Bitmap* m_pBitmap;
```

## <a name="cd2dbitmapm_sizedest"></a><a name="m_sizedest"></a> CD2DBitmap：： m_sizeDest

位图目标大小。

```
CD2DSizeU m_sizeDest;
```

## <a name="cd2dbitmapm_strpath"></a><a name="m_strpath"></a> CD2DBitmap：： m_strPath

Botmap 文件路径。

```
CString m_strPath;
```

## <a name="cd2dbitmapm_uiresid"></a><a name="m_uiresid"></a> CD2DBitmap：： m_uiResID

位图资源 ID。

```
UINT m_uiResID;
```

## <a name="cd2dbitmapoperator-id2d1bitmap"></a><a name="operator_id2d1bitmap_star"></a> CD2DBitmap：： operator ID2D1Bitmap *

返回 ID2D1Bitmap 接口

```
operator ID2D1Bitmap*();
```

### <a name="return-value"></a>返回值

指向 ID2D1Bitmap 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
