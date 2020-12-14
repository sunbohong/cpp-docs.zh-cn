---
description: 了解详细信息： CD2DRoundedRect 类
title: CD2DRoundedRect 类
ms.date: 11/04/2016
f1_keywords:
- CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect
- AFXRENDERTARGET/CD2DRoundedRect::CD2DRoundedRect
helpviewer_keywords:
- CD2DRoundedRect [MFC], CD2DRoundedRect
ms.assetid: 06207fb5-e92b-41c0-bceb-b45d8f466531
ms.openlocfilehash: 13c1b0910c9d78f615d64e3eecba8bb813916413
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97240658"
---
# <a name="cd2droundedrect-class"></a>CD2DRoundedRect 类

`D2D1_ROUNDED_RECT`的包装器。

## <a name="syntax"></a>语法

```
class CD2DRoundedRect : public D2D1_ROUNDED_RECT;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CD2DRoundedRect：： CD2DRoundedRect](#cd2droundedrect)|已重载。 `CD2DRoundedRect`从对象构造对象 `D2D1_ROUNDED_RECT` 。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`D2D1_ROUNDED_RECT`

[CD2DRoundedRect](../../mfc/reference/cd2droundedrect-class.md)

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2droundedrectcd2droundedrect"></a><a name="cd2droundedrect"></a> CD2DRoundedRect：： CD2DRoundedRect

从 CD2DRectF 对象构造 CD2DRoundedRect 对象。

```
CD2DRoundedRect(
    const CD2DRectF& rectIn,
    const CD2DSizeF& sizeRadius);

CD2DRoundedRect(const D2D1_ROUNDED_RECT& rectIn);
CD2DRoundedRect(const D2D1_ROUNDED_RECT* rectIn);
```

### <a name="parameters"></a>parameters

*rectIn*<br/>
源矩形

*sizeRadius*<br/>
半径大小

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
