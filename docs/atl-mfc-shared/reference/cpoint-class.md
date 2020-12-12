---
description: 了解详细信息： CPoint 类
title: CPoint 类
ms.date: 11/04/2016
f1_keywords:
- CPoint
- ATLTYPES/ATL::CPoint
- ATLTYPES/ATL::CPoint::CPoint
- ATLTYPES/ATL::CPoint::Offset
helpviewer_keywords:
- LPPOINT structure
- POINT structure
- CPoint class
ms.assetid: a6d4db93-35cc-444d-9221-c3e160f6edaa
ms.openlocfilehash: 9d1c6ecb628e4d47d80503bb7a441efc4deb1252
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166754"
---
# <a name="cpoint-class"></a>CPoint 类

类似于 Windows `POINT` 结构。

## <a name="syntax"></a>语法

```
class CPoint : public tagPOINT
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CPoint：： CPoint](#cpoint)|构造一个 `CPoint`。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CPoint：： Offset](#offset)|将值添加到的 `x` 和 `y` 成员 `CPoint` 。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CPoint：： operator-](#operator_-)|返回和大小的差 `CPoint` ，或点的求反或两个点之间的大小差或负大小的偏移量。|
|[CPoint：： operator！ =](#operator_neq)|检查两个点之间是否不相等。|
|[CPoint：： operator +](#operator_add)|返回 `CPoint` 与大小或点的和，或 `CRect` 大小的偏移量。|
|[CPoint：： operator + =](#operator_add_eq)|`CPoint`添加大小或点后的偏移量。|
|[CPoint：： operator-=](#operator_-_eq)|`CPoint`通过减去大小或点来偏移。|
|[CPoint：： operator = =](#operator_eq_eq)|检查两个点之间是否相等。|

## <a name="remarks"></a>备注

它还包括用于处理 `CPoint` 和 [点](/windows/win32/api/windef/ns-windef-point) 结构的成员函数。

`CPoint`对象可以在使用结构的任何位置使用 `POINT` 。 此类的与 "size" 交互的运算符接受 [CSize](../../atl-mfc-shared/reference/csize-class.md) 对象或 [大小](/windows/win32/api/windef/ns-windef-size) 结构，因为这两个对象是可互换的。

> [!NOTE]
> 此类派生自 `tagPOINT` 结构。  (该名称 `tagPOINT` 是不太常用的 `POINT` 结构名称。 ) 这意味着结构的数据成员 `POINT` `x` 和 `y` 可访问的数据成员 `CPoint` 。

> [!NOTE]
> 有关 (如) 的共享实用工具类的详细信息 `CPoint` ，请参阅 [共享类](../../atl-mfc-shared/atl-mfc-shared-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

`tagPOINT`

`CPoint`

## <a name="requirements"></a>要求

**标头：** atltypes

## <a name="cpointcpoint"></a><a name="cpoint"></a> CPoint：： CPoint

构造 `CPoint` 对象。

```
CPoint() throw();
CPoint(int initX, int initY) throw();
CPoint(POINT initPt) throw();
CPoint(SIZE initSize) throw();
CPoint(LPARAM dwPoint) throw();
```

### <a name="parameters"></a>parameters

*initX*<br/>
指定 `x` 的 `CPoint` 成员的值。

*initY*<br/>
指定 `y` 的 `CPoint` 成员的值。

*initPt*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point) 结构或 `CPoint` 指定用于初始化的值的 `CPoint` 。

*initSize*<br/>
指定用于初始化的值的[大小](/windows/win32/api/windef/ns-windef-size)结构或[CSize](../../atl-mfc-shared/reference/csize-class.md) `CPoint` 。

*dwPoint*<br/>
将 `x` 成员设置为 *dwPoint* 的低序位字，并将成员设置为 `y` *dwPoint* 的高序位字。

### <a name="remarks"></a>备注

如果未提供自变量，则 `x` 和 `y` 成员将设置为 0。

### <a name="example"></a>示例

```cpp
CPoint   ptTopLeft(0, 0);
// works from a POINT, too

POINT   ptHere;
ptHere.x = 35;
ptHere.y = 95;

CPoint   ptMFCHere(ptHere);

// works from a SIZE
SIZE   sHowBig;
sHowBig.cx = 300;
sHowBig.cy = 10;

CPoint ptMFCBig(sHowBig);
// or from a DWORD

DWORD   dwSize;
dwSize = MAKELONG(35, 95);

CPoint ptFromDouble(dwSize);
ASSERT(ptFromDouble == ptMFCHere);
```

## <a name="cpointoffset"></a><a name="offset"></a> CPoint：： Offset

将值添加到的 `x` 和 `y` 成员 `CPoint` 。

```cpp
void Offset(int xOffset, int yOffset) throw();
void Offset(POINT point) throw();
void Offset(SIZE size) throw();
```

### <a name="parameters"></a>parameters

*xOffset*<br/>
指定的成员的偏移量 `x` `CPoint` 。

*yOffset*<br/>
指定的成员的偏移量 `y` `CPoint` 。

*情况*<br/>
指定 ( [点](/windows/win32/api/windef/ns-windef-point) 或 `CPoint`) 偏移量 `CPoint` 。

*大小*<br/>
指定 ( [大小](/windows/win32/api/windef/ns-windef-size) 或 [CSize](../../atl-mfc-shared/reference/csize-class.md)) 偏移量 `CPoint` 。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#28](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_1.cpp)]

## <a name="cpointoperator-"></a><a name="operator_eq_eq"></a> CPoint：： operator = =

检查两个点之间是否相等。

```
BOOL operator==(POINT point) const throw();
```

### <a name="parameters"></a>parameters

*情况*<br/>
包含 [点](/windows/win32/api/windef/ns-windef-point) 结构或 `CPoint` 对象。

### <a name="return-value"></a>返回值

如果点相等，则为非零值;否则为0。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#29](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_2.cpp)]

## <a name="cpointoperator-"></a><a name="operator_neq"></a> CPoint：： operator！ =

检查两个点之间是否不相等。

```
BOOL operator!=(POINT point) const throw();
```

### <a name="parameters"></a>parameters

*情况*<br/>
包含 [点](/windows/win32/api/windef/ns-windef-point) 结构或 `CPoint` 对象。

### <a name="return-value"></a>返回值

如果点不相等，则为非零值;否则为0。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#30](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_3.cpp)]

## <a name="cpointoperator-"></a><a name="operator_add_eq"></a> CPoint：： operator + =

第一个重载向添加一个大小 `CPoint` 。

```cpp
void operator+=(SIZE size) throw();
void operator+=(POINT point) throw();
```

### <a name="parameters"></a>parameters

*大小*<br/>
包含 [大小](/windows/win32/api/windef/ns-windef-size) 结构或 [CSize](../../atl-mfc-shared/reference/csize-class.md) 对象。

*情况*<br/>
包含 [点](/windows/win32/api/windef/ns-windef-point) 结构或 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 对象。

### <a name="remarks"></a>备注

第二个重载将一个点添加到 `CPoint` 。

在这两种情况下，加法都是通过将 `x` 右操作数的 (或 `cx`) 成员添加到 `x` 的成员 `CPoint` 并将 `y` 右操作数的 (或 `cy`) 成员添加到的 `y` 成员 `CPoint` 来完成的。

例如，将添加 `CPoint(5, -7)` 到包含 `CPoint(30, 40)` 变量更改的变量 `CPoint(35, 33)` 。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#31](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_4.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-_eq"></a> CPoint：： operator-=

第一个重载从中减去一个大小 `CPoint` 。

```cpp
void operator-=(SIZE size) throw();
void operator-=(POINT point) throw();
```

### <a name="parameters"></a>parameters

*大小*<br/>
包含 [大小](/windows/win32/api/windef/ns-windef-size) 结构或 [CSize](../../atl-mfc-shared/reference/csize-class.md) 对象。

*情况*<br/>
包含 [点](/windows/win32/api/windef/ns-windef-point) 结构或 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 对象。

### <a name="remarks"></a>备注

第二个重载从中减去一个点 `CPoint` 。

在这两种情况下，可通过 `x` 从的成员减去右侧操作数的 (或 `cx`) 成员， `x` `CPoint` 并 `y` `cy` 从的成员减去右侧操作数的 (或) 成员 `y` `CPoint` 来实现减法运算。

例如， `CPoint(5, -7)` 从包含 `CPoint(30, 40)` 变量更改的变量中减去 `CPoint(25, 47)` 。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#32](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_5.cpp)]

## <a name="cpointoperator-"></a><a name="operator_add"></a> CPoint：： operator +

使用此运算符可 `CPoint` 由 `CPoint` 或对象偏移 `CSize` ，或用于的偏移量 `CRect` `CPoint` 。

```
CPoint operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="parameters"></a>parameters

*大小*<br/>
包含 [大小](/windows/win32/api/windef/ns-windef-size) 结构或 [CSize](../../atl-mfc-shared/reference/csize-class.md) 对象。

*情况*<br/>
包含 [点](/windows/win32/api/windef/ns-windef-point) 结构或 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 对象。

*lpRect*<br/>
包含指向 [RECT](/windows/win32/api/windef/ns-windef-rect) 结构或 [CRect](../../atl-mfc-shared/reference/crect-class.md) 对象的指针。

### <a name="return-value"></a>返回值

`CPoint`偏移大小、由 `CPoint` 点偏移或由点偏移的偏移量 `CRect` 。

### <a name="remarks"></a>备注

例如，使用前两个重载之一来使点与点 `CPoint(25, -19)` 或大小偏移， `CPoint(15, 5)` `CSize(15, 5)` 返回值 `CPoint(40, -14)` 。

将矩形添加到某个点后，该矩形会在偏移后 `x` 返回 `y` 在该点中指定的和值。 例如，使用最后一个重载通过点偏移矩形会 `CRect(125, 219, 325, 419)` `CPoint(25, -19)` 返回 `CRect(150, 200, 350, 400)` 。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#33](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_6.cpp)]

## <a name="cpointoperator--"></a><a name="operator_-"></a> CPoint：： operator-

使用前两个重载之一来 `CPoint` 从中减去或 `CSize` 对象 `CPoint` 。

```
CSize operator-(POINT point) const throw();
CPoint operator-(SIZE size) const throw();
CRect operator-(const RECT* lpRect) const throw();
CPoint operator-() const throw();
```

### <a name="parameters"></a>parameters

*情况*<br/>
[POINT](/windows/win32/api/windef/ns-windef-point)结构或[CPoint](../../atl-mfc-shared/reference/cpoint-class.md)对象。

*大小*<br/>
[大小](/windows/win32/api/windef/ns-windef-size)结构或[CSize](../../atl-mfc-shared/reference/csize-class.md)对象。

*lpRect*<br/>
指向 [RECT](/windows/win32/api/windef/ns-windef-rect) 结构或 [CRect](../../atl-mfc-shared/reference/crect-class.md) 对象的指针。

### <a name="return-value"></a>返回值

一个， `CSize` 它是两个点之间的差异， `CPoint` 偏移一个大小的求反，一个是一个点的取反的偏移量， `CRect` 或者是一个点的 `CPoint` 求反。

### <a name="remarks"></a>备注

第三个重载 `CRect` 按的求反 `CPoint` 。 最后，使用一元运算符进行反运算 `CPoint` 。

例如，使用第一个重载查找两个点之间的差异 `CPoint(25, -19)` ，并 `CPoint(15, 5)` 返回 `CSize(10, -24)` 。

`CSize`从中减去与 `CPoint` 上述相同的计算，但返回 `CPoint` 对象，而不是 `CSize` 对象。 例如，使用第二个重载查找点和大小之间的差异 `CPoint(25, -19)` `CSize(15, 5)` `CPoint(10, -24)` 。

从某个点减去一个矩形将以该 `x` 点中指定的和值的负值作为偏移量 `y` 。 例如，使用最后一个重载 `CRect(125, 200, 325, 400)` 按点偏移矩形时 `CPoint(25, -19)` 返回 `CRect(100, 219, 300, 419)` 。

使用一元运算符对某个点求反。 例如，将一元运算符与点一起使用时，将 `CPoint(25, -19)` 返回 `CPoint(-25, 19)` 。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#34](../../atl-mfc-shared/codesnippet/cpp/cpoint-class_7.cpp)]

## <a name="see-also"></a>请参阅

[MFC 示例 MDI](../../overview/visual-cpp-samples.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[点结构](/windows/win32/api/windef/ns-windef-point)<br/>
[CRect 类](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CSize 类](../../atl-mfc-shared/reference/csize-class.md)
