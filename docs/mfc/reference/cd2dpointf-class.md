---
description: 了解详细信息： CD2DPointF 类
title: CD2DPointF 类
ms.date: 11/04/2016
f1_keywords:
- CD2DPointF
- AFXRENDERTARGET/CD2DPointF
- AFXRENDERTARGET/CD2DPointF::CD2DPointF
helpviewer_keywords:
- CD2DPointF [MFC], CD2DPointF
ms.assetid: 30f72083-1c8a-4f50-adb2-72dbbe3522d4
ms.openlocfilehash: 0f63aa35acb33504c96316b67ecc4f885f4f0247
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193352"
---
# <a name="cd2dpointf-class"></a>CD2DPointF 类

`D2D1_POINT_2F`的包装器。

## <a name="syntax"></a>语法

```
class CD2DPointF : public D2D1_POINT_2F;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CD2DPointF：： CD2DPointF](#cd2dpointf)|已重载。 `CD2DPointF`从对象构造对象 `D2D1_POINT_2F` 。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CD2DPointF：： operator CPoint](#operator_cpoint)|转换 `CD2DPointF` 为 `CPoint` 对象。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`D2D1_POINT_2F`

`CD2DPointF`

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2dpointfcd2dpointf"></a><a name="cd2dpointf"></a> CD2DPointF：： CD2DPointF

从 CPoint 对象构造 CD2DPointF 对象。

```
CD2DPointF(const CPoint& pt);
CD2DPointF(const D2D1_POINT_2F& pt);
CD2DPointF(const D2D1_POINT_2F* pt);
CD2DPointF(FLOAT fX = 0., FLOAT fY = 0.);
```

### <a name="parameters"></a>parameters

*pt*<br/>
源点

*fX*<br/>
源 X

*财年*<br/>
源 Y

## <a name="cd2dpointfoperator-cpoint"></a><a name="operator_cpoint"></a> CD2DPointF：： operator CPoint

将 CD2DPointF 转换为 CPoint 对象。

```
operator CPoint();
```

### <a name="return-value"></a>返回值

D2D 点的当前值。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
