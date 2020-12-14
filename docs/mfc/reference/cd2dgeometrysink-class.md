---
description: 了解详细信息： CD2DGeometrySink 类
title: CD2DGeometrySink 类
ms.date: 11/04/2016
f1_keywords:
- CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::CD2DGeometrySink
- AFXRENDERTARGET/CD2DGeometrySink::AddArc
- AFXRENDERTARGET/CD2DGeometrySink::AddBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddBeziers
- AFXRENDERTARGET/CD2DGeometrySink::AddLine
- AFXRENDERTARGET/CD2DGeometrySink::AddLines
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBezier
- AFXRENDERTARGET/CD2DGeometrySink::AddQuadraticBeziers
- AFXRENDERTARGET/CD2DGeometrySink::BeginFigure
- AFXRENDERTARGET/CD2DGeometrySink::Close
- AFXRENDERTARGET/CD2DGeometrySink::EndFigure
- AFXRENDERTARGET/CD2DGeometrySink::Get
- AFXRENDERTARGET/CD2DGeometrySink::IsValid
- AFXRENDERTARGET/CD2DGeometrySink::SetFillMode
- AFXRENDERTARGET/CD2DGeometrySink::SetSegmentFlags
- AFXRENDERTARGET/CD2DGeometrySink::m_pSink
helpviewer_keywords:
- CD2DGeometrySink [MFC], CD2DGeometrySink
- CD2DGeometrySink [MFC], AddArc
- CD2DGeometrySink [MFC], AddBezier
- CD2DGeometrySink [MFC], AddBeziers
- CD2DGeometrySink [MFC], AddLine
- CD2DGeometrySink [MFC], AddLines
- CD2DGeometrySink [MFC], AddQuadraticBezier
- CD2DGeometrySink [MFC], AddQuadraticBeziers
- CD2DGeometrySink [MFC], BeginFigure
- CD2DGeometrySink [MFC], Close
- CD2DGeometrySink [MFC], EndFigure
- CD2DGeometrySink [MFC], Get
- CD2DGeometrySink [MFC], IsValid
- CD2DGeometrySink [MFC], SetFillMode
- CD2DGeometrySink [MFC], SetSegmentFlags
- CD2DGeometrySink [MFC], m_pSink
ms.assetid: e5e07f41-0343-4ab1-9d6b-8c62ed33c04a
ms.openlocfilehash: e7916cdb39272e924a9d6ef6c0a8322d8ce6fb1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193417"
---
# <a name="cd2dgeometrysink-class"></a>CD2DGeometrySink 类

ID2D1GeometrySink 的包装器。

## <a name="syntax"></a>语法

```
class CD2DGeometrySink;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CD2DGeometrySink：： CD2DGeometrySink](#cd2dgeometrysink)|从 CD2DPathGeometry 对象构造 CD2DGeometrySink 对象。|
|[CD2DGeometrySink：： ~ CD2DGeometrySink](#_dtorcd2dgeometrysink)|析构函数。 当 D2D 几何图形接收器对象被销毁时调用。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CD2DGeometrySink：： AddArc](#addarc)|向路径几何图形添加一条弧线|
|[CD2DGeometrySink：： AddBezier](#addbezier)|在当前点和指定的终点之间创建三次贝塞尔曲线。|
|[CD2DGeometrySink：： AddBeziers](#addbeziers)|创建一系列三次方贝塞尔曲线，并将其添加到几何图形接收器。|
|[CD2DGeometrySink：： AddLine](#addline)|在当前点和指定的终点之间创建直线段，并将其添加到几何图形接收器。|
|[CD2DGeometrySink：： AddLines](#addlines)|使用指定的点创建一行序列，并将其添加到几何图形接收器。|
|[CD2DGeometrySink：： AddQuadraticBezier](#addquadraticbezier)|在当前点和指定的终点之间创建二次贝塞尔曲线。|
|[CD2DGeometrySink：： AddQuadraticBeziers](#addquadraticbeziers)|在单个调用中将一系列二次贝塞尔线段添加为数组。|
|[CD2DGeometrySink：： BeginFigure](#beginfigure)|在指定点开始一个新图形。|
|[CD2DGeometrySink：： Close](#close)|关闭几何图形接收器|
|[CD2DGeometrySink：： EndFigure](#endfigure)|结束当前图形;还可以关闭它。|
|[CD2DGeometrySink：： Get](#get)|返回 ID2D1GeometrySink 接口|
|[CD2DGeometrySink：： IsValid](#isvalid)|检查几何接收器有效性|
|[CD2DGeometrySink：： SetFillMode](#setfillmode)|指定方法，该方法用于确定哪些点在几何图形接收器所描述的几何图形内以及哪些点在外部。|
|[CD2DGeometrySink：： SetSegmentFlags](#setsegmentflags)|指定要应用于添加到几何图形接收器的新段的笔划和联接选项。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CD2DGeometrySink：： operator ID2D1GeometrySink *](#operator_id2d1geometrysink_star)|返回 ID2D1GeometrySink 接口|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CD2DGeometrySink：： m_pSink](#m_psink)|指向 ID2D1GeometrySink 的指针。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`CD2DGeometrySink`

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="_dtorcd2dgeometrysink"></a> CD2DGeometrySink：： ~ CD2DGeometrySink

析构函数。 当 D2D 几何图形接收器对象被销毁时调用。

```
virtual ~CD2DGeometrySink();
```

## <a name="cd2dgeometrysinkaddarc"></a><a name="addarc"></a> CD2DGeometrySink：： AddArc

向路径几何图形添加一条弧线

```cpp
void AddArc(const D2D1_ARC_SEGMENT& arc);
```

### <a name="parameters"></a>parameters

*分布*<br/>
要添加到图中的弧线段

## <a name="cd2dgeometrysinkaddbezier"></a><a name="addbezier"></a> CD2DGeometrySink：： AddBezier

在当前点和指定的终点之间创建三次贝塞尔曲线。

```cpp
void AddBezier(const D2D1_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>parameters

*条*<br/>
一个结构，该结构描述要添加的贝塞尔曲线的控制点和终结点。

## <a name="cd2dgeometrysinkaddbeziers"></a><a name="addbeziers"></a> CD2DGeometrySink：： AddBeziers

创建一系列三次方贝塞尔曲线，并将其添加到几何图形接收器。

```cpp
void AddBeziers(
    const CArray<D2D1_BEZIER_SEGMENT,
    D2D1_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>parameters

*贝塞尔*<br/>
描述要创建的贝塞尔曲线的贝塞尔线段的数组。 曲线从几何图形接收器的当前点绘制 (最后一条线段的终点，或由 BeginFigure 指定的位置) 到数组中第一条贝塞尔线段的终点。 如果数组包含其他贝塞尔线段，则每个后续贝塞尔线段都使用上一贝塞尔线段的终点作为起点。

## <a name="cd2dgeometrysinkaddline"></a><a name="addline"></a> CD2DGeometrySink：： AddLine

在当前点和指定的终点之间创建直线段，并将其添加到几何图形接收器。

```cpp
void AddLine(CD2DPointF point);
```

### <a name="parameters"></a>parameters

*情况*<br/>
要绘制的线条的终点。

## <a name="cd2dgeometrysinkaddlines"></a><a name="addlines"></a> CD2DGeometrySink：： AddLines

使用指定的点创建一行序列，并将其添加到几何图形接收器。

```cpp
void AddLines(
    const CArray<CD2DPointF,
    CD2DPointF>& points);
```

### <a name="parameters"></a>parameters

*热点*<br/>
用于描述要绘制的线条的一个或多个点的数组。 将从几何图形接收器的当前点绘制一条线， (最后一条线段的终点，或由 BeginFigure 指定的位置) 到数组中的第一个点。 如果数组包含其他点，则将从第一个点到数组的第二个点绘制一条线，从第二个点到第三个点，依此类推。 要绘制的线条的终点序列的数组。

## <a name="cd2dgeometrysinkaddquadraticbezier"></a><a name="addquadraticbezier"></a> CD2DGeometrySink：： AddQuadraticBezier

在当前点和指定的终点之间创建二次贝塞尔曲线。

```cpp
void AddQuadraticBezier(const D2D1_QUADRATIC_BEZIER_SEGMENT& bezier);
```

### <a name="parameters"></a>parameters

*条*<br/>
描述要添加的二次贝塞尔曲线控制点和终点的结构。

## <a name="cd2dgeometrysinkaddquadraticbeziers"></a><a name="addquadraticbeziers"></a> CD2DGeometrySink：： AddQuadraticBeziers

在单个调用中将一系列二次贝塞尔线段添加为数组。

```cpp
void AddQuadraticBeziers(
    const CArray<D2D1_QUADRATIC_BEZIER_SEGMENT,
    D2D1_QUADRATIC_BEZIER_SEGMENT>& beziers);
```

### <a name="parameters"></a>parameters

*贝塞尔*<br/>
一系列二次贝塞尔线段的数组。

## <a name="cd2dgeometrysinkbeginfigure"></a><a name="beginfigure"></a> CD2DGeometrySink：： BeginFigure

在指定点开始一个新图形。

```cpp
void BeginFigure(
    CD2DPointF startPoint,
    D2D1_FIGURE_BEGIN figureBegin);
```

### <a name="parameters"></a>parameters

*startPoint*<br/>
开始新图形的点。

*figureBegin*<br/>
新图形是空白还是填充。

## <a name="cd2dgeometrysinkcd2dgeometrysink"></a><a name="cd2dgeometrysink"></a> CD2DGeometrySink：： CD2DGeometrySink

从 CD2DPathGeometry 对象构造 CD2DGeometrySink 对象。

```
CD2DGeometrySink(CD2DPathGeometry& pathGeometry);
```

### <a name="parameters"></a>parameters

*System.windows.media.pathgeometry>*<br/>
现有的 CD2DPathGeometry 对象。

## <a name="cd2dgeometrysinkclose"></a><a name="close"></a> CD2DGeometrySink：： Close

关闭几何图形接收器

```
BOOL Close();
```

### <a name="return-value"></a>返回值

如果成功，则为非零值;否则为 FALSE。

## <a name="cd2dgeometrysinkendfigure"></a><a name="endfigure"></a> CD2DGeometrySink：： EndFigure

结束当前图形;还可以关闭它。

```cpp
void EndFigure(D2D1_FIGURE_END figureEnd);
```

### <a name="parameters"></a>parameters

*figureEnd*<br/>
一个指示当前图形是否关闭的值。 如果图形已关闭，则在当前点与 BeginFigure 指定的起始点之间绘制一条线。

## <a name="cd2dgeometrysinkget"></a><a name="get"></a> CD2DGeometrySink：： Get

返回 ID2D1GeometrySink 接口

```
ID2D1GeometrySink* Get();
```

### <a name="return-value"></a>返回值

指向 ID2D1GeometrySink 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dgeometrysinkisvalid"></a><a name="isvalid"></a> CD2DGeometrySink：： IsValid

检查几何接收器有效性

```
BOOL IsValid() const;
```

### <a name="return-value"></a>返回值

如果几何图形接收器有效，则为 TRUE;否则为 FALSE。

## <a name="cd2dgeometrysinkm_psink"></a><a name="m_psink"></a> CD2DGeometrySink：： m_pSink

指向 ID2D1GeometrySink 的指针。

```
ID2D1GeometrySink* m_pSink;
```

## <a name="cd2dgeometrysinkoperator-id2d1geometrysink"></a><a name="operator_id2d1geometrysink_star"></a> CD2DGeometrySink：： operator ID2D1GeometrySink *

返回 ID2D1GeometrySink 接口

```
operator ID2D1GeometrySink*();
```

### <a name="return-value"></a>返回值

指向 ID2D1GeometrySink 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dgeometrysinksetfillmode"></a><a name="setfillmode"></a> CD2DGeometrySink：： SetFillMode

指定方法，该方法用于确定哪些点在几何图形接收器所描述的几何图形内以及哪些点在外部。

```cpp
void SetFillMode(D2D1_FILL_MODE fillMode);
```

### <a name="parameters"></a>parameters

*fillMode*<br/>
用于确定给定点是否是几何图形的一部分的方法。

## <a name="cd2dgeometrysinksetsegmentflags"></a><a name="setsegmentflags"></a> CD2DGeometrySink：： SetSegmentFlags

指定要应用于添加到几何图形接收器的新段的笔划和联接选项。

```cpp
void SetSegmentFlags(D2D1_PATH_SEGMENT vertexFlags);
```

### <a name="parameters"></a>parameters

*vertexFlags*<br/>
要应用于添加到几何图形接收器的新段的笔划和联接选项。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
