---
description: 了解详细信息： CSize 类
title: CSize 类
ms.date: 10/18/2018
f1_keywords:
- CSize
- ATLTYPES/ATL::CSize
- ATLTYPES/ATL::CSize::CSize
helpviewer_keywords:
- SIZE
- dimensions, MFC
- dimensions
- CSize class
ms.assetid: fb2cf85a-0bc1-46f8-892b-309c108b52ae
ms.openlocfilehash: 0a63a7e0c48948406bf5650a1b095713f701a325
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166637"
---
# <a name="csize-class"></a>CSize 类

类似于实现相对坐标或位置的 Windows [SIZE](/windows/win32/api/windef/ns-windef-size) 结构。

## <a name="syntax"></a>语法

```
class CSize : public tagSIZE
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CSize：： CSize](#csize)|构造 `CSize` 对象。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CSize：： operator-](#operator_-)|减去两个大小。|
|[CSize：： operator！ =](#operator_neq)|检查和大小之间的不相等 `CSize` 。|
|[CSize：： operator +](#operator_add)|添加两种大小。|
|[CSize：： operator + =](#operator_add_eq)|向添加大小 `CSize` 。|
|[CSize：： operator-=](#operator_-_eq)|从中减去一个大小 `CSize` 。|
|[CSize：： operator = =](#operator_eq_eq)|检查 `CSize` 和大小是否相等。|

## <a name="remarks"></a>备注

此类派生自 `SIZE` 结构。 这意味着，可以 `CSize` 在调用的参数中传递 `SIZE` ，该结构的数据成员可以 `SIZE` 访问数据成员 `CSize` 。

`cx` `cy` `SIZE` (和) 的和成员 `CSize` 是公共的。 此外，还 `CSize` 实现了成员函数以操作 `SIZE` 结构。

> [!NOTE]
> 有关 (如) 的共享实用工具类的详细信息 `CSize` ，请参阅 [共享类](../../atl-mfc-shared/atl-mfc-shared-classes.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

`tagSIZE`

`CSize`

## <a name="requirements"></a>要求

**标头：** atltypes

## <a name="csizecsize"></a><a name="csize"></a> CSize：： CSize

构造 `CSize` 对象。

```
CSize() throw();
CSize( int initCX, int initCY) throw();
CSize( SIZE initSize) throw();
CSize( POINT initPt) throw();
CSize( DWORD dwSize) throw();
```

### <a name="parameters"></a>parameters

*initCX*<br/>
设置的 `cx` 成员 `CSize` 。

*initCY*<br/>
设置的 `cy` 成员 `CSize` 。

*initSize*<br/>
[](/windows/win32/api/windef/ns-windef-size) `CSize` 用于初始化的大小结构或对象 `CSize` 。

*initPt*<br/>
[点](/windows/win32/api/windef/ns-windef-point) 结构或 `CPoint` 用于初始化的对象 `CSize` 。

*dwSize*<br/>
用于初始化的 DWORD `CSize` 。 低序位字是 `cx` 成员，高位字是 `cy` 成员。

### <a name="remarks"></a>备注

如果未提供任何参数， `cx` `cy` 则将其初始化为零。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#97](../../atl-mfc-shared/codesnippet/cpp/csize-class_1.cpp)]

## <a name="csizeoperator-"></a><a name="operator_eq_eq"></a> CSize：： operator = =

检查两个大小是否相等。

```
BOOL operator==(SIZE size) const throw();
```

### <a name="remarks"></a>备注

如果大小相等，则返回非零值 otherwize 0。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#98](../../atl-mfc-shared/codesnippet/cpp/csize-class_2.cpp)]

## <a name="csizeoperator-"></a><a name="operator_neq"></a> CSize：： operator！ =

检查两个大小是否不相等。

```
BOOL operator!=(SIZE size) const throw();
```

### <a name="remarks"></a>备注

如果大小不相等，则返回非零值，否则返回0。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#99](../../atl-mfc-shared/codesnippet/cpp/csize-class_3.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add_eq"></a> CSize：： operator + =

将大小添加到此 `CSize` 。

```cpp
void operator+=(SIZE size) throw();
```

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#100](../../atl-mfc-shared/codesnippet/cpp/csize-class_4.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-_eq"></a> CSize：： operator-=

从此中减去大小 `CSize` 。

```cpp
void operator-=(SIZE size) throw();
```

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#101](../../atl-mfc-shared/codesnippet/cpp/csize-class_5.cpp)]

## <a name="csizeoperator-"></a><a name="operator_add"></a> CSize：： operator +

这些运算符将此 `CSize` 值添加到参数的值。

```
CSize operator+(SIZE size) const throw();
CPoint operator+(POINT point) const throw();
CRect operator+(const RECT* lpRect) const throw();
```

### <a name="remarks"></a>备注

请参阅以下各个运算符的说明：

- **operator + (** *大小* **)**

  此操作会将两个 `CSize` 值相加。

- **operator + (** *点* **)**

  此操作偏移量 (按此值移动) [点](/windows/win32/api/windef/ns-windef-point) (或 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md)) 值 `CSize` 。 `cx` `cy` 此值的和成员 `CSize` 将添加到值的 `x` 和 `y` 数据成员中 `POINT` 。 它类似于采用[大小](/windows/win32/api/windef/ns-windef-size)参数的[CPoint：： operator +](../../atl-mfc-shared/reference/cpoint-class.md#operator_add)的版本。

- **operator + (** *lpRect* **)**

   此操作偏移量 (按此值移动) [RECT](/windows/win32/api/windef/ns-windef-rect) (或 [CRect](../../atl-mfc-shared/reference/crect-class.md)) 值 `CSize` 。 `cx` `cy` 此值的和成员 `CSize` 将添加到值的 `left` 、 `top` 、 `right` 和 `bottom` 数据成员中 `RECT` 。 它类似于采用[大小](/windows/win32/api/windef/ns-windef-size)参数的[CRect：： operator +](../../atl-mfc-shared/reference/crect-class.md#operator_add)的版本。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#102](../../atl-mfc-shared/codesnippet/cpp/csize-class_6.cpp)]

## <a name="csizeoperator--"></a><a name="operator_-"></a> CSize：： operator-

其中的前三个运算符将此 `CSize` 值减去到参数的值。

```
CSize operator-(SIZE size) const throw();
CPoint operator-(POINT point) const throw();
CRect operator-(const RECT* lpRect) const throw();
CSize operator-() const throw();
```

### <a name="remarks"></a>备注

第四个运算符（一元减号）更改值的符号 `CSize` 。 请参阅以下各个运算符的说明：

- **操作员 (** *大小* **)**

  此操作会将两个值相减 `CSize` 。

- **操作员 (** *点* **)**

  此操作偏移量 (通过此值的加法反转) [点](/windows/win32/api/windef/ns-windef-point) 或 [CPoint](../../atl-mfc-shared/reference/cpoint-class.md) 值移动 `CSize` 。 `cx`此值的和将 `cy` `CSize` 从 `x` 值的和 `y` 数据成员中减去 `POINT` 。 它类似于采用[大小](/windows/win32/api/windef/ns-windef-size)参数的[CPoint：： operator](../../atl-mfc-shared/reference/cpoint-class.md#operator_-)的版本。

- **操作员 (** *lpRect* **)**

  此操作偏移量 (通过此值的加法反转) [RECT](/windows/win32/api/windef/ns-windef-rect) 或 [CRect](../../atl-mfc-shared/reference/crect-class.md) 值移动 `CSize` 。 `cx` `cy` 此值的和成员 `CSize` 从 `left` 值的、 `top` 、 `right` 和 `bottom` 数据成员 `RECT` 中减去。 它类似于采用[大小](/windows/win32/api/windef/ns-windef-size)参数的[CRect：： operator](../../atl-mfc-shared/reference/crect-class.md#operator_-)的版本。

- **操作员 ( # B1**

  此操作返回此值的加法逆元 `CSize` 。

### <a name="example"></a>示例

[!code-cpp[NVC_ATLMFC_Utilities#103](../../atl-mfc-shared/codesnippet/cpp/csize-class_7.cpp)]

## <a name="see-also"></a>请参阅

[MFC 示例 MDI](../../overview/visual-cpp-samples.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CRect 类](../../atl-mfc-shared/reference/crect-class.md)<br/>
[CPoint 类](../../atl-mfc-shared/reference/cpoint-class.md)
