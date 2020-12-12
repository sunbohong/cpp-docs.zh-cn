---
description: 了解详细信息： CD2DPathGeometry 类
title: CD2DPathGeometry 类
ms.date: 11/04/2016
f1_keywords:
- CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::CD2DPathGeometry
- AFXRENDERTARGET/CD2DPathGeometry::Attach
- AFXRENDERTARGET/CD2DPathGeometry::Create
- AFXRENDERTARGET/CD2DPathGeometry::Destroy
- AFXRENDERTARGET/CD2DPathGeometry::Detach
- AFXRENDERTARGET/CD2DPathGeometry::GetFigureCount
- AFXRENDERTARGET/CD2DPathGeometry::GetSegmentCount
- AFXRENDERTARGET/CD2DPathGeometry::Open
- AFXRENDERTARGET/CD2DPathGeometry::Stream
- AFXRENDERTARGET/CD2DPathGeometry::m_pPathGeometry
helpviewer_keywords:
- CD2DPathGeometry [MFC], CD2DPathGeometry
- CD2DPathGeometry [MFC], Attach
- CD2DPathGeometry [MFC], Create
- CD2DPathGeometry [MFC], Destroy
- CD2DPathGeometry [MFC], Detach
- CD2DPathGeometry [MFC], GetFigureCount
- CD2DPathGeometry [MFC], GetSegmentCount
- CD2DPathGeometry [MFC], Open
- CD2DPathGeometry [MFC], Stream
- CD2DPathGeometry [MFC], m_pPathGeometry
ms.assetid: 686216eb-5080-4242-ace5-8fa1ce96307c
ms.openlocfilehash: eb33d498436c887eb038b3312e2b98ca04d6620b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97280529"
---
# <a name="cd2dpathgeometry-class"></a>CD2DPathGeometry 类

ID2D1PathGeometry 的包装器。

## <a name="syntax"></a>语法

```
class CD2DPathGeometry : public CD2DGeometry;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CD2DPathGeometry：： CD2DPathGeometry](#cd2dpathgeometry)|构造 CD2DPathGeometry 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CD2DPathGeometry：： Attach](#attach)|将现有资源接口附加到对象|
|[CD2DPathGeometry：： Create](#create)|创建 CD2DPathGeometry。  (重写 [CD2DResource：： Create](../../mfc/reference/cd2dresource-class.md#create). ) |
|[CD2DPathGeometry：:D estroy](#destroy)|销毁 CD2DPathGeometry 对象。  (重写 [CD2DGeometry：:D estroy](../../mfc/reference/cd2dgeometry-class.md#destroy)。 ) |
|[CD2DPathGeometry：:D etach](#detach)|从对象分离资源接口|
|[CD2DPathGeometry：： GetFigureCount](#getfigurecount)|检索路径几何图形中的数字。|
|[CD2DPathGeometry：： GetSegmentCount](#getsegmentcount)|检索路径几何图形中的段数。|
|[CD2DPathGeometry：： Open](#open)|检索用于用图形和段填充路径几何图形的几何图形接收器。|
|[CD2DPathGeometry：： Stream](#stream)|将路径几何图形的内容复制到指定的 ID2D1GeometrySink。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CD2DPathGeometry：： m_pPathGeometry](#m_ppathgeometry)|指向 ID2D1PathGeometry 的指针。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

[CD2DGeometry](../../mfc/reference/cd2dgeometry-class.md)

`CD2DPathGeometry`

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2dpathgeometryattach"></a><a name="attach"></a> CD2DPathGeometry：： Attach

将现有资源接口附加到对象

```cpp
void Attach(ID2D1PathGeometry* pResource);
```

### <a name="parameters"></a>parameters

*pResource*<br/>
现有的资源接口。 不能为 NULL

## <a name="cd2dpathgeometrycd2dpathgeometry"></a><a name="cd2dpathgeometry"></a> CD2DPathGeometry：： CD2DPathGeometry

构造 CD2DPathGeometry 对象。

```
CD2DPathGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>parameters

*pParentTarget*<br/>
指向呈现器目标的指针。

*bAutoDestroy*<br/>
指示对象将被所有者 (pParentTarget) 销毁。

## <a name="cd2dpathgeometrycreate"></a><a name="create"></a> CD2DPathGeometry：： Create

创建 CD2DPathGeometry。

```
virtual HRESULT Create(CRenderTarget* pRenderTarget);
```

### <a name="parameters"></a>parameters

*pRenderTarget*<br/>
指向呈现器目标的指针。

### <a name="return-value"></a>返回值

如果该方法成功，则它会返回 S_OK。 否则，它将返回 HRESULT 错误代码。

## <a name="cd2dpathgeometrydestroy"></a><a name="destroy"></a> CD2DPathGeometry：:D estroy

销毁 CD2DPathGeometry 对象。

```
virtual void Destroy();
```

## <a name="cd2dpathgeometrydetach"></a><a name="detach"></a> CD2DPathGeometry：:D etach

从对象分离资源接口

```
ID2D1PathGeometry* Detach();
```

### <a name="return-value"></a>返回值

指向已分离资源接口的指针。

## <a name="cd2dpathgeometrygetfigurecount"></a><a name="getfigurecount"></a> CD2DPathGeometry：： GetFigureCount

检索路径几何图形中的数字。

```
int GetFigureCount() const;
```

### <a name="return-value"></a>返回值

返回路径几何图形中的数字。

## <a name="cd2dpathgeometrygetsegmentcount"></a><a name="getsegmentcount"></a> CD2DPathGeometry：： GetSegmentCount

检索路径几何图形中的段数。

```
int GetSegmentCount() const;
```

### <a name="return-value"></a>返回值

返回路径几何图形中的段数。

## <a name="cd2dpathgeometrym_ppathgeometry"></a><a name="m_ppathgeometry"></a> CD2DPathGeometry：： m_pPathGeometry

指向 ID2D1PathGeometry 的指针。

```
ID2D1PathGeometry* m_pPathGeometry;
```

## <a name="cd2dpathgeometryopen"></a><a name="open"></a> CD2DPathGeometry：： Open

检索用于用图形和段填充路径几何图形的几何图形接收器。

```
ID2D1GeometrySink* Open();
```

### <a name="return-value"></a>返回值

指向 ID2D1GeometrySink 的指针，该指针用于使用图形和段填充路径几何图形。

## <a name="cd2dpathgeometrystream"></a><a name="stream"></a> CD2DPathGeometry：： Stream

将路径几何图形的内容复制到指定的 ID2D1GeometrySink。

```
BOOL Stream(ID2D1GeometrySink* geometrySink);
```

### <a name="parameters"></a>parameters

*geometrySink*<br/>
将路径几何图形内容复制到的接收器。 修改此接收器不会更改此路径几何图形的内容。

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
