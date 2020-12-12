---
description: 了解详细信息： CBitmapRenderTarget 类
title: CBitmapRenderTarget 类
ms.date: 11/04/2016
f1_keywords:
- CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::CBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::Attach
- AFXRENDERTARGET/CBitmapRenderTarget::Detach
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmap
- AFXRENDERTARGET/CBitmapRenderTarget::GetBitmapRenderTarget
- AFXRENDERTARGET/CBitmapRenderTarget::m_pBitmapRenderTarget
helpviewer_keywords:
- CBitmapRenderTarget [MFC], CBitmapRenderTarget
- CBitmapRenderTarget [MFC], Attach
- CBitmapRenderTarget [MFC], Detach
- CBitmapRenderTarget [MFC], GetBitmap
- CBitmapRenderTarget [MFC], GetBitmapRenderTarget
- CBitmapRenderTarget [MFC], m_pBitmapRenderTarget
ms.assetid: c89a4437-812e-4943-acb2-b429a04cc4d2
ms.openlocfilehash: a7987651c988dcf7fcd4c4decf4a2bd474ab8619
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122676"
---
# <a name="cbitmaprendertarget-class"></a>CBitmapRenderTarget 类

ID2D1BitmapRenderTarget 的包装器。

## <a name="syntax"></a>语法

```
class CBitmapRenderTarget : public CRenderTarget;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CBitmapRenderTarget：： CBitmapRenderTarget](#cbitmaprendertarget)|构造 CBitmapRenderTarget 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CBitmapRenderTarget：： Attach](#attach)|将现有呈现器目标接口附加到对象|
|[CBitmapRenderTarget：:D etach](#detach)|从对象分离呈现目标接口|
|[CBitmapRenderTarget：： GetBitmap](#getbitmap)|检索此呈现器目标的位图。 返回的位图可用于绘制操作。|
|[CBitmapRenderTarget：： GetBitmapRenderTarget](#getbitmaprendertarget)|返回 ID2D1BitmapRenderTarget 接口|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CBitmapRenderTarget：： operator ID2D1BitmapRenderTarget *](#operator_id2d1bitmaprendertarget_star)|返回 ID2D1BitmapRenderTarget 接口|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CBitmapRenderTarget：： m_pBitmapRenderTarget](#m_pbitmaprendertarget)|指向 ID2D1BitmapRenderTarget 对象的指针。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

`CBitmapRenderTarget`

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cbitmaprendertargetattach"></a><a name="attach"></a> CBitmapRenderTarget：： Attach

将现有呈现器目标接口附加到对象

```cpp
void Attach(ID2D1BitmapRenderTarget* pTarget);
```

### <a name="parameters"></a>parameters

*pTarget*<br/>
现有的呈现器目标接口。 不能为 NULL

## <a name="cbitmaprendertargetcbitmaprendertarget"></a><a name="cbitmaprendertarget"></a> CBitmapRenderTarget：： CBitmapRenderTarget

构造 CBitmapRenderTarget 对象。

```
CBitmapRenderTarget();
```

## <a name="cbitmaprendertargetdetach"></a><a name="detach"></a> CBitmapRenderTarget：:D etach

从对象分离呈现目标接口

```
ID2D1BitmapRenderTarget* Detach();
```

### <a name="return-value"></a>返回值

指向分离的呈现器目标接口的指针。

## <a name="cbitmaprendertargetgetbitmap"></a><a name="getbitmap"></a> CBitmapRenderTarget：： GetBitmap

检索此呈现器目标的位图。 返回的位图可用于绘制操作。

```
BOOL GetBitmap(CD2DBitmap& bitmap);
```

### <a name="parameters"></a>parameters

*位图*<br/>
此方法返回时，包含此呈现器目标的有效位图。 此位图可用于绘制操作。

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="cbitmaprendertargetgetbitmaprendertarget"></a><a name="getbitmaprendertarget"></a> CBitmapRenderTarget：： GetBitmapRenderTarget

返回 ID2D1BitmapRenderTarget 接口

```
ID2D1BitmapRenderTarget* GetBitmapRenderTarget();
```

### <a name="return-value"></a>返回值

指向 ID2D1BitmapRenderTarget 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cbitmaprendertargetm_pbitmaprendertarget"></a><a name="m_pbitmaprendertarget"></a> CBitmapRenderTarget：： m_pBitmapRenderTarget

指向 ID2D1BitmapRenderTarget 对象的指针。

```
ID2D1BitmapRenderTarget* m_pBitmapRenderTarget;
```

## <a name="cbitmaprendertargetoperator-id2d1bitmaprendertarget"></a><a name="operator_id2d1bitmaprendertarget_star"></a> CBitmapRenderTarget：： operator ID2D1BitmapRenderTarget *

返回 ID2D1BitmapRenderTarget 接口

```
operator ID2D1BitmapRenderTarget*();
```

### <a name="return-value"></a>返回值

指向 ID2D1BitmapRenderTarget 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
