---
description: 了解详细信息： CD2DGeometry 类
title: CD2DGeometry 类
ms.date: 11/04/2016
f1_keywords:
- CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::CD2DGeometry
- AFXRENDERTARGET/CD2DGeometry::Attach
- AFXRENDERTARGET/CD2DGeometry::CombineWithGeometry
- AFXRENDERTARGET/CD2DGeometry::CompareWithGeometry
- AFXRENDERTARGET/CD2DGeometry::ComputeArea
- AFXRENDERTARGET/CD2DGeometry::ComputeLength
- AFXRENDERTARGET/CD2DGeometry::ComputePointAtLength
- AFXRENDERTARGET/CD2DGeometry::Destroy
- AFXRENDERTARGET/CD2DGeometry::Detach
- AFXRENDERTARGET/CD2DGeometry::FillContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Get
- AFXRENDERTARGET/CD2DGeometry::GetBounds
- AFXRENDERTARGET/CD2DGeometry::GetWidenedBounds
- AFXRENDERTARGET/CD2DGeometry::IsValid
- AFXRENDERTARGET/CD2DGeometry::Outline
- AFXRENDERTARGET/CD2DGeometry::Simplify
- AFXRENDERTARGET/CD2DGeometry::StrokeContainsPoint
- AFXRENDERTARGET/CD2DGeometry::Tessellate
- AFXRENDERTARGET/CD2DGeometry::Widen
- AFXRENDERTARGET/CD2DGeometry::m_pGeometry
helpviewer_keywords:
- CD2DGeometry [MFC], CD2DGeometry
- CD2DGeometry [MFC], Attach
- CD2DGeometry [MFC], CombineWithGeometry
- CD2DGeometry [MFC], CompareWithGeometry
- CD2DGeometry [MFC], ComputeArea
- CD2DGeometry [MFC], ComputeLength
- CD2DGeometry [MFC], ComputePointAtLength
- CD2DGeometry [MFC], Destroy
- CD2DGeometry [MFC], Detach
- CD2DGeometry [MFC], FillContainsPoint
- CD2DGeometry [MFC], Get
- CD2DGeometry [MFC], GetBounds
- CD2DGeometry [MFC], GetWidenedBounds
- CD2DGeometry [MFC], IsValid
- CD2DGeometry [MFC], Outline
- CD2DGeometry [MFC], Simplify
- CD2DGeometry [MFC], StrokeContainsPoint
- CD2DGeometry [MFC], Tessellate
- CD2DGeometry [MFC], Widen
- CD2DGeometry [MFC], m_pGeometry
ms.assetid: 3f95054b-fdb8-4e87-87f2-9fc3df7279ec
ms.openlocfilehash: 2c902554ba5377ce9f7a4a481d4001a9ef7a47f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193443"
---
# <a name="cd2dgeometry-class"></a>CD2DGeometry 类

ID2D1Geometry 的包装器。

## <a name="syntax"></a>语法

```
class CD2DGeometry : public CD2DResource;
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CD2DGeometry：： CD2DGeometry](#cd2dgeometry)|构造 CD2DGeometry 对象。|
|[CD2DGeometry：： ~ CD2DGeometry](#_dtorcd2dgeometry)|析构函数。 当 D2D geometry 对象被销毁时调用。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CD2DGeometry：： Attach](#attach)|将现有资源接口附加到对象|
|[CD2DGeometry：： CombineWithGeometry](#combinewithgeometry)|将此几何图形与指定几何图形合并，并将结果存储在 ID2D1SimplifiedGeometrySink 中。|
|[CD2DGeometry：： CompareWithGeometry](#comparewithgeometry)|描述此几何与指定几何之间的交集。 使用指定的平展公差执行比较。|
|[CD2DGeometry：： ComputeArea](#computearea)|在几何图形由指定的矩阵转换并使用指定的公差平展之后计算该区域。|
|[CD2DGeometry：： ComputeLength](#computelength)|计算几何长度，就好像每个段被 unrolled 到一条直线。|
|[CD2DGeometry：： ComputePointAtLength](#computepointatlength)|在几何图形由指定的矩阵转换后，使用指定的公差按指定的矩阵转换后的指定距离，计算点和正切向量。|
|[CD2DGeometry：:D estroy](#destroy)|销毁 CD2DGeometry 对象。  (重写 [CD2DResource：:D estroy](../../mfc/reference/cd2dresource-class.md#destroy)。 ) |
|[CD2DGeometry：:D etach](#detach)|从对象分离资源接口|
|[CD2DGeometry：： FillContainsPoint](#fillcontainspoint)|指示根据指定的平展公差，几何图形是否包含指定的点。|
|[CD2DGeometry：： Get](#get)|返回 ID2D1Geometry 接口|
|[CD2DGeometry：： GetBounds](#getbounds)||
|[CD2DGeometry：： GetWidenedBounds](#getwidenedbounds)|在几何图形由指定的笔划宽度和样式加宽并由指定的矩阵转换后，获取该几何图形的边界。|
|[CD2DGeometry：： IsValid](#isvalid)|检查资源有效性 (重写 [CD2DResource：： IsValid](../../mfc/reference/cd2dresource-class.md#isvalid). ) |
|[CD2DGeometry：：镂空](#outline)|计算几何图形的轮廓并将结果写入 ID2D1SimplifiedGeometrySink。|
|[CD2DGeometry：：化简](#simplify)|创建仅包含行和 (（可选）) 三次方贝塞尔曲线并将结果写入 ID2D1SimplifiedGeometrySink 的几何图形的简化版本。|
|[CD2DGeometry：： StrokeContainsPoint](#strokecontainspoint)|确定几何图形的笔画是否包含给定指定笔画粗细、样式和转换的指定点。|
|[CD2DGeometry：：进行分割](#tessellate)|在使用指定的矩形转换和使用指定的容差平展几何图形后，创建一组覆盖该几何图形的顺时针方向的三角形。|
|[CD2DGeometry：：加宽](#widen)|在指定的矩阵转换并使用指定的公差平展后，使几何图形按指定的笔划扩大并将结果写入 ID2D1SimplifiedGeometrySink。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CD2DGeometry：： operator ID2D1Geometry *](#operator_id2d1geometry_star)|返回 ID2D1Geometry 接口|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CD2DGeometry：： m_pGeometry](#m_pgeometry)|指向 ID2D1Geometry 的指针。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CD2DResource](../../mfc/reference/cd2dresource-class.md)

`CD2DGeometry`

## <a name="requirements"></a>要求

**标头：** afxrendertarget

## <a name="cd2dgeometrycd2dgeometry"></a><a name="_dtorcd2dgeometry"></a> CD2DGeometry：： ~ CD2DGeometry

析构函数。 当 D2D geometry 对象被销毁时调用。

```
virtual ~CD2DGeometry();
```

## <a name="cd2dgeometryattach"></a><a name="attach"></a> CD2DGeometry：： Attach

将现有资源接口附加到对象

```cpp
void Attach(ID2D1Geometry* pResource);
```

### <a name="parameters"></a>parameters

*pResource*<br/>
现有的资源接口。 不能为 NULL

## <a name="cd2dgeometrycd2dgeometry"></a><a name="cd2dgeometry"></a> CD2DGeometry：： CD2DGeometry

构造 CD2DGeometry 对象。

```
CD2DGeometry(
    CRenderTarget* pParentTarget,
    BOOL bAutoDestroy = TRUE);
```

### <a name="parameters"></a>parameters

*pParentTarget*<br/>
指向呈现器目标的指针。

*bAutoDestroy*<br/>
指示对象将被所有者 (pParentTarget) 销毁。

## <a name="cd2dgeometrycombinewithgeometry"></a><a name="combinewithgeometry"></a> CD2DGeometry：： CombineWithGeometry

将此几何图形与指定几何图形合并，并将结果存储在 ID2D1SimplifiedGeometrySink 中。

```
BOOL CombineWithGeometry(
    CD2DGeometry& inputGeometry,
    D2D1_COMBINE_MODE combineMode,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>parameters

*inputGeometry*<br/>
要与此实例合并的几何图形。

*combineMode*<br/>
要执行的组合操作的类型。

*inputGeometryTransform*<br/>
组合之前要应用于 inputGeometry 的转换。

*geometrySink*<br/>
合并运算的结果。

*flatteningTolerance*<br/>
几何图形的多边形近似中两点间距离的上限。 值越小，生成的结果就越准确，但执行速度会变慢。

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="cd2dgeometrycomparewithgeometry"></a><a name="comparewithgeometry"></a> CD2DGeometry：： CompareWithGeometry

描述此几何与指定几何之间的交集。 使用指定的平展公差执行比较。

```
D2D1_GEOMETRY_RELATION CompareWithGeometry(
    CD2DGeometry& inputGeometry,
    const D2D1_MATRIX_3X2_F& inputGeometryTransform,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>parameters

*inputGeometry*<br/>
要测试的几何图形。

*inputGeometryTransform*<br/>
要应用于 inputGeometry 的转换。

*flatteningTolerance*<br/>
几何图形的多边形近似中两点间距离的上限。 值越小，生成的结果就越准确，但执行速度会变慢。

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="cd2dgeometrycomputearea"></a><a name="computearea"></a> CD2DGeometry：： ComputeArea

在几何图形由指定的矩阵转换并使用指定的公差平展之后计算该区域。

```
BOOL ComputeArea(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& area,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>parameters

*worldTransform*<br/>
在计算其区域前应用于此几何图形的转换。

*图*<br/>
此方法返回时，包含指向此几何图形的已转换平展版本区域的指针。 必须为此参数分配存储空间。

*flatteningTolerance*<br/>
几何图形的多边形近似中两点间距离的上限。 值越小，生成的结果就越准确，但执行速度会变慢。

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="cd2dgeometrycomputelength"></a><a name="computelength"></a> CD2DGeometry：： ComputeLength

计算几何长度，就好像每个段被 unrolled 到一条直线。

```
BOOL ComputeLength(
    const D2D1_MATRIX_3X2_F& worldTransform,
    FLOAT& length,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>parameters

*worldTransform*<br/>
要在计算其长度之前应用于几何图形的转换。

*length*<br/>
此方法返回时，包含指向几何图形长度的指针。 对于闭合的几何图形，长度包含隐式闭合段。 必须为此参数分配存储空间。

*flatteningTolerance*<br/>
几何图形的多边形近似中两点间距离的上限。 值越小，生成的结果就越准确，但执行速度会变慢。

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="cd2dgeometrycomputepointatlength"></a><a name="computepointatlength"></a> CD2DGeometry：： ComputePointAtLength

在几何图形由指定的矩阵转换后，使用指定的公差按指定的矩阵转换后的指定距离，计算点和正切向量。

```
BOOL ComputePointAtLength(
    FLOAT length,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DPointF& point,
    CD2DPointF& unitTangentVector,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>parameters

*length*<br/>
沿点和切线的几何图形要查找的距离。 如果此距离小于0，此方法将计算几何图形中的第一个点。 如果此距离大于几何图形的长度，此方法将计算几何图形中的最后一个点。

*worldTransform*<br/>
要在计算指定点和正切之前应用于几何图形的转换。

*情况*<br/>
沿几何图形指定距离的位置。 如果几何图形为空，则此点包含 NaN 作为其 x 和 y 值。

*unitTangentVector*<br/>
此方法返回时，包含一个指针，该指针指向沿几何图形上指定距离的正切向量。 如果几何图形为空，则此向量包含 NaN 作为其 x 和 y 值。 必须为此参数分配存储空间。

*flatteningTolerance*<br/>
几何图形的多边形近似中两点间距离的上限。 值越小，生成的结果就越准确，但执行速度会变慢。

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="cd2dgeometrydestroy"></a><a name="destroy"></a> CD2DGeometry：:D estroy

销毁 CD2DGeometry 对象。

```
virtual void Destroy();
```

## <a name="cd2dgeometrydetach"></a><a name="detach"></a> CD2DGeometry：:D etach

从对象分离资源接口

```
ID2D1Geometry* Detach();
```

### <a name="return-value"></a>返回值

指向已分离资源接口的指针。

## <a name="cd2dgeometryfillcontainspoint"></a><a name="fillcontainspoint"></a> CD2DGeometry：： FillContainsPoint

指示根据指定的平展公差，几何图形是否包含指定的点。

```
BOOL FillContainsPoint(
    CD2DPointF point,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>parameters

*情况*<br/>
要测试的点。

*worldTransform*<br/>
在测试包含之前应用于几何图形的转换。

*contains*<br/>
此方法返回时，包含一个布尔值，如果由几何图形填充的区域包含点，则该布尔值为 TRUE;否则为 FALSE。 必须为此参数分配存储空间。

*flatteningTolerance*<br/>
用于计算精确几何路径和路径交集的数值精度。 缺少填充量小于容差的点仍被视为内部点。 值越小，生成的结果就越准确，但执行速度会变慢。

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="cd2dgeometryget"></a><a name="get"></a> CD2DGeometry：： Get

返回 ID2D1Geometry 接口

```
ID2D1Geometry* Get();
```

### <a name="return-value"></a>返回值

指向 ID2D1Geometry 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dgeometrygetbounds"></a><a name="getbounds"></a> CD2DGeometry：： GetBounds

```
BOOL GetBounds(
const D2D1_MATRIX_3X2_F& worldTransform,
CD2DRectF& bounds) const;
```

### <a name="parameters"></a>parameters

*worldTransform*<br/>
*汇编*

### <a name="return-value"></a>返回值

## <a name="cd2dgeometrygetwidenedbounds"></a><a name="getwidenedbounds"></a> CD2DGeometry：： GetWidenedBounds

在几何图形由指定的笔划宽度和样式加宽并由指定的矩阵转换后，获取该几何图形的边界。

```
BOOL GetWidenedBounds(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    CD2DRectF& bounds,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>parameters

*strokeWidth*<br/>
通过对其轮廓进行描边使几何变宽的量。

*strokeStyle*<br/>
加宽几何图形的笔画样式。

*worldTransform*<br/>
要在转换几何图形后和对几何图形进行描边之后应用于几何图形的转换。

*汇编*<br/>
此方法返回时，包含加宽的几何图形的界限。 必须为此参数分配存储空间。

*flatteningTolerance*<br/>
几何图形的多边形近似中两点间距离的上限。 值越小，生成的结果就越准确，但执行速度会变慢。

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="cd2dgeometryisvalid"></a><a name="isvalid"></a> CD2DGeometry：： IsValid

检查资源有效性

```
virtual BOOL IsValid() const;
```

### <a name="return-value"></a>返回值

如果资源有效，则为 TRUE;否则为 FALSE。

## <a name="cd2dgeometrym_pgeometry"></a><a name="m_pgeometry"></a> CD2DGeometry：： m_pGeometry

指向 ID2D1Geometry 的指针。

```
ID2D1Geometry* m_pGeometry;
```

## <a name="cd2dgeometryoperator-id2d1geometry"></a><a name="operator_id2d1geometry_star"></a> CD2DGeometry：： operator ID2D1Geometry *

返回 ID2D1Geometry 接口

```
operator ID2D1Geometry*();
```

### <a name="return-value"></a>返回值

指向 ID2D1Geometry 接口的指针; 如果对象尚未初始化，则为 NULL。

## <a name="cd2dgeometryoutline"></a><a name="outline"></a> CD2DGeometry：：镂空

计算几何图形的轮廓并将结果写入 ID2D1SimplifiedGeometrySink。

```
BOOL Outline(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>parameters

*worldTransform*<br/>
要应用于几何轮廓的转换。

*geometrySink*<br/>
几何转换后的轮廓附加到的 ID2D1SimplifiedGeometrySink。

*flatteningTolerance*<br/>
几何图形的多边形近似中两点间距离的上限。 值越小，生成的结果就越准确，但执行速度会变慢。

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="cd2dgeometrysimplify"></a><a name="simplify"></a> CD2DGeometry：：化简

创建仅包含行和 (（可选）) 三次方贝塞尔曲线并将结果写入 ID2D1SimplifiedGeometrySink 的几何图形的简化版本。

```
BOOL Simplify(
    D2D1_GEOMETRY_SIMPLIFICATION_OPTION simplificationOption,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>parameters

*simplificationOption*<br/>
一个值，该值指定简化几何是否应包含曲线。

*worldTransform*<br/>
要应用于简化几何图形的转换。

*geometrySink*<br/>
简化几何追加到的 ID2D1SimplifiedGeometrySink。

*flatteningTolerance*<br/>
几何图形的多边形近似中两点间距离的上限。 值越小，生成的结果就越准确，但执行速度会变慢。

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="cd2dgeometrystrokecontainspoint"></a><a name="strokecontainspoint"></a> CD2DGeometry：： StrokeContainsPoint

确定几何图形的笔画是否包含给定指定笔画粗细、样式和转换的指定点。

```
BOOL StrokeContainsPoint(
    CD2DPointF point,
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    BOOL* contains,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>parameters

*情况*<br/>
要进行包容测试的点。

*strokeWidth*<br/>
要应用的笔划的粗细。

*strokeStyle*<br/>
要应用的笔划的样式。

*worldTransform*<br/>
要应用于描边几何图形的转换。

*contains*<br/>
此方法返回时，如果几何图形的笔划包含指定的点，则包含一个设置为 TRUE 的布尔值;否则为 FALSE。 必须为此参数分配存储空间。

*flatteningTolerance*<br/>
用于计算精确几何路径和路径交集的数值精度。 如果点缺少描边，则仍会将其视为内部点。 值越小，生成的结果就越准确，但执行速度会变慢。

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="cd2dgeometrytessellate"></a><a name="tessellate"></a> CD2DGeometry：：进行分割

在使用指定的矩形转换和使用指定的容差平展几何图形后，创建一组覆盖该几何图形的顺时针方向的三角形。

```
BOOL Tessellate(
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1TessellationSink* tessellationSink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>parameters

*worldTransform*<br/>
要应用于此几何图形的转换，或为 NULL。

*tessellationSink*<br/>
分割附加到的 ID2D1TessellationSink。

*flatteningTolerance*<br/>
几何图形的多边形近似中两点间距离的上限。 值越小，生成的结果就越准确，但执行速度会变慢。

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="cd2dgeometrywiden"></a><a name="widen"></a> CD2DGeometry：：加宽

在指定的矩阵转换并使用指定的公差平展后，使几何图形按指定的笔划扩大并将结果写入 ID2D1SimplifiedGeometrySink。

```
BOOL Widen(
    FLOAT strokeWidth,
    ID2D1StrokeStyle* strokeStyle,
    const D2D1_MATRIX_3X2_F& worldTransform,
    ID2D1SimplifiedGeometrySink* geometrySink,
    FLOAT flatteningTolerance = D2D1_DEFAULT_FLATTENING_TOLERANCE) const;
```

### <a name="parameters"></a>parameters

*strokeWidth*<br/>
要将几何图形加宽的量。

*strokeStyle*<br/>
要应用于几何图形的笔画样式，或为 NULL。

*worldTransform*<br/>
在扩大后要应用于几何图形的转换。

*geometrySink*<br/>
要向其追加加宽的几何图形的 ID2D1SimplifiedGeometrySink。

*flatteningTolerance*<br/>
几何图形的多边形近似中两点间距离的上限。 值越小，生成的结果就越准确，但执行速度会变慢。

### <a name="return-value"></a>返回值

如果该方法成功，则返回 TRUE。 否则，返回 FALSE。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)
