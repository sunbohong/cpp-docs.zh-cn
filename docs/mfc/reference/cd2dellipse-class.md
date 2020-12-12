---
description: 了解详细信息： CD2DEllipse 类
title: CD2DEllipse 类
ms.date: 08/29/2019
f1_keywords:
- CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse
- AFXRENDERTARGET/CD2DEllipse::CD2DEllipse
helpviewer_keywords:
- CD2DEllipse [MFC], CD2DEllipse
ms.assetid: e9f02f54-acf2-427e-b349-db50cd9a77df
ms.openlocfilehash: 827ba5515cb4b20cb8e5b10012590a001e01c08f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97313055"
---
# <a name="cd2dellipse-class"></a>CD2DEllipse 类

`D2D1_ELLIPSE`的包装器。

## <a name="syntax"></a>语法

```
class CD2DEllipse : public D2D1_ELLIPSE;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CD2DEllipse：： CD2DEllipse](#cd2dellipse)|已重载。 `CD2DEllipse`从对象构造对象 `D2D1_ELLIPSE` 。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`D2D1_ELLIPSE`

`CD2DEllipse`

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2dellipsecd2dellipse"></a><a name="cd2dellipse"></a> CD2DEllipse：： CD2DEllipse

从 CD2DRectF 对象构造 CD2DEllipse 对象。

```
CD2DEllipse(const CD2DRectF& rect);
CD2DEllipse(const D2D1_ELLIPSE& ellipse);
CD2DEllipse(const D2D1_ELLIPSE* ellipse);

CD2DEllipse(
    const CD2DPointF& ptCenter,
    const CD2DSizeF& sizeRadius);
```

### <a name="parameters"></a>parameters

*rect*<br/>
源矩形

*椭圆*<br/>
源椭圆

*ptCenter*<br/>
椭圆的中心点。

*sizeRadius*<br/>
椭圆的 X 轴半径和 Y 轴半径。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
