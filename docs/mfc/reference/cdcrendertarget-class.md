---
description: 了解详细信息： CDCRenderTarget 类
title: CDCRenderTarget 类
ms.date: 11/04/2016
f1_keywords:
- CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::CDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::Attach
- AFXRENDERTARGET/CDCRenderTarget::BindDC
- AFXRENDERTARGET/CDCRenderTarget::Create
- AFXRENDERTARGET/CDCRenderTarget::Detach
- AFXRENDERTARGET/CDCRenderTarget::GetDCRenderTarget
- AFXRENDERTARGET/CDCRenderTarget::m_pDCRenderTarget
helpviewer_keywords:
- CDCRenderTarget [MFC], CDCRenderTarget
- CDCRenderTarget [MFC], Attach
- CDCRenderTarget [MFC], BindDC
- CDCRenderTarget [MFC], Create
- CDCRenderTarget [MFC], Detach
- CDCRenderTarget [MFC], GetDCRenderTarget
- CDCRenderTarget [MFC], m_pDCRenderTarget
ms.assetid: aa8059c9-08e6-49e4-9b8c-00fa54077a61
ms.openlocfilehash: 3959321bbd6274c821b1f02be5962b23ec9dbc95
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97185318"
---
# <a name="cdcrendertarget-class"></a>CDCRenderTarget 类

ID2D1DCRenderTarget 的包装器。

## <a name="syntax"></a>语法

```
class CDCRenderTarget : public CRenderTarget;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CDCRenderTarget：： CDCRenderTarget](#cdcrendertarget)|构造 CDCRenderTarget 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CDCRenderTarget：： Attach](#attach)|将现有呈现器目标接口附加到对象|
|[CDCRenderTarget：： BindDC](#binddc)|将呈现器目标绑定到它向其发出绘图命令的设备上下文|
|[CDCRenderTarget：： Create](#create)|创建 CDCRenderTarget。|
|[CDCRenderTarget：:D etach](#detach)|从对象分离呈现目标接口|
|[CDCRenderTarget：： GetDCRenderTarget](#getdcrendertarget)|返回 ID2D1DCRenderTarget 接口|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CDCRenderTarget：： operator ID2D1DCRenderTarget *](#operator_id2d1dcrendertarget_star)|返回 ID2D1DCRenderTarget 接口|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CDCRenderTarget：： m_pDCRenderTarget](#m_pdcrendertarget)|指向 ID2D1DCRenderTarget 对象的指针。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CRenderTarget](../../mfc/reference/crendertarget-class.md)

[CDCRenderTarget](../../mfc/reference/cdcrendertarget-class.md)

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cdcrendertargetattach"></a><a name="attach"></a> CDCRenderTarget：： Attach

将现有呈现器目标接口附加到对象

```cpp
void Attach(ID2D1DCRenderTarget* pTarget);
```

### <a name="parameters"></a>parameters

*pTarget*<br/>
现有的呈现器目标接口。 不能为 NULL

## <a name="cdcrendertargetbinddc"></a><a name="binddc"></a> CDCRenderTarget：： BindDC

将呈现器目标绑定到它向其发出绘图命令的设备上下文

```
BOOL BindDC(
    const CDC& dc,
    const CRect& rect);
```

### <a name="parameters"></a>parameters

*dc*<br/>
呈现器目标向其发出绘图命令的设备上下文

*rect*<br/>
将呈现器目标绑定到的设备上下文的句柄尺寸 (HDC) 

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="cdcrendertargetcdcrendertarget"></a><a name="cdcrendertarget"></a> CDCRenderTarget：： CDCRenderTarget

构造 CDCRenderTarget 对象。

```
CDCRenderTarget();
```

## <a name="cdcrendertargetcreate"></a><a name="create"></a> CDCRenderTarget：： Create

创建 CDCRenderTarget。

```
BOOL Create(const D2D1_RENDER_TARGET_PROPERTIES& props);
```

### <a name="parameters"></a>parameters

*属性*<br/>
呈现模式、像素格式、远程处理选项、DPI 信息和硬件呈现所需的最小 DirectX 支持。

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="cdcrendertargetdetach"></a><a name="detach"></a> CDCRenderTarget：:D etach

从对象分离呈现目标接口

```
ID2D1DCRenderTarget* Detach();
```

### <a name="return-value"></a>返回值

指向分离的呈现器目标接口的指针。

## <a name="cdcrendertargetgetdcrendertarget"></a><a name="getdcrendertarget"></a> CDCRenderTarget：： GetDCRenderTarget

返回 ID2D1DCRenderTarget 接口

```
ID2D1DCRenderTarget* GetDCRenderTarget();
```

### <a name="return-value"></a>返回值

指向 ID2D1DCRenderTarget 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cdcrendertargetm_pdcrendertarget"></a><a name="m_pdcrendertarget"></a> CDCRenderTarget：： m_pDCRenderTarget

指向 ID2D1DCRenderTarget 对象的指针。

```
ID2D1DCRenderTarget* m_pDCRenderTarget;
```

## <a name="cdcrendertargetoperator-id2d1dcrendertarget"></a><a name="operator_id2d1dcrendertarget_star"></a> CDCRenderTarget：： operator ID2D1DCRenderTarget *

返回 ID2D1DCRenderTarget 接口

```
operator ID2D1DCRenderTarget*();
```

### <a name="return-value"></a>返回值

指向 ID2D1DCRenderTarget 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
