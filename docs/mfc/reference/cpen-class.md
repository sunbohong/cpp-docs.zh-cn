---
description: 了解详细信息： CPen 类
title: CPen 类
ms.date: 11/04/2016
f1_keywords:
- CPen
- AFXWIN/CPen
- AFXWIN/CPen::CPen
- AFXWIN/CPen::CreatePen
- AFXWIN/CPen::CreatePenIndirect
- AFXWIN/CPen::FromHandle
- AFXWIN/CPen::GetExtLogPen
- AFXWIN/CPen::GetLogPen
helpviewer_keywords:
- CPen [MFC], CPen
- CPen [MFC], CreatePen
- CPen [MFC], CreatePenIndirect
- CPen [MFC], FromHandle
- CPen [MFC], GetExtLogPen
- CPen [MFC], GetLogPen
ms.assetid: 93175a3a-d46c-4768-be8d-863254f97a5f
ms.openlocfilehash: b85e0de8a5ce9048851b3f0a8ee5a701e749f0af
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345142"
---
# <a name="cpen-class"></a>CPen 类

封装一个 Windows 图形设备接口 (GDI) 笔。

## <a name="syntax"></a>语法

```
class CPen : public CGdiObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CPen：： CPen](#cpen)|构造 `CPen` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CPen：： CreatePen](#createpen)|使用指定的样式、宽度和画笔特性创建逻辑修饰或几何钢笔，并将其附加到 `CPen` 对象。|
|[CPen：： CreatePenIndirect](#createpenindirect)|使用 [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen) 结构中给定的样式、宽度和颜色创建钢笔，并将其附加到 `CPen` 对象。|
|[CPen：： FromHandle](#fromhandle)|`CPen`给定 WINDOWS HPEN 时，返回指向对象的指针。|
|[CPen：： GetExtLogPen](#getextlogpen)|获取 [EXTLOGPEN](/windows/win32/api/wingdi/ns-wingdi-extlogpen) 基础结构。|
|[CPen：： GetLogPen](#getlogpen)|获取 [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen) 基础结构。|

### <a name="public-operators"></a>公共运算符

|名称|描述|
|----------|-----------------|
|[CPen：： operator HPEN](#operator_hpen)|返回附加到对象的 Windows 句柄 `CPen` 。|

## <a name="remarks"></a>备注

有关使用的详细信息 `CPen` ，请参阅 [图形对象](../../mfc/graphic-objects.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CGdiObject](../../mfc/reference/cgdiobject-class.md)

`CPen`

## <a name="requirements"></a>要求

**标头:** afxwin.h

## <a name="cpencpen"></a><a name="cpen"></a> CPen：： CPen

构造 `CPen` 对象。

```
CPen();

CPen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

CPen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>parameters

*nPenStyle*<br/>
指定笔样式。 此构造函数的第一个版本中的此参数可以是下列值之一：

- PS_SOLID 创建一支纯色。

- PS_DASH 创建一个虚线。 仅当笔宽度为1或更低时，在设备单位中才有效。

- PS_DOT 创建一个点虚线。 仅当笔宽度为1或更低时，在设备单位中才有效。

- PS_DASHDOT 创建一个带有交替虚线和点的笔。 仅当笔宽度为1或更低时，在设备单位中才有效。

- PS_DASHDOTDOT 创建一个带有交替虚线和双点的笔。 仅当笔宽度为1或更低时，在设备单位中才有效。

- PS_NULL 创建 NULL 笔。

- PS_INSIDEFRAME 创建一个在由指定了边框的 Windows GDI 输出函数生成的闭合形状框架内绘制线条的笔 (例如， `Ellipse`) 、、、 `Rectangle` `RoundRect` `Pie` 和 `Chord` 成员函数。 如果将此样式用于未指定边框的 Windows GDI 输出函数 (例如， `LineTo` 成员函数) ，则笔的绘图区域不受帧的限制。

构造函数的第二个版本 `CPen` 指定类型、样式、结束端和联接属性的组合。 每个类别的值都应使用按位 OR 运算符 ( # A0) 进行组合。 钢笔类型可以是以下值之一：

- PS_GEOMETRIC 创建一个几何笔。

- PS_COSMETIC 创建修饰笔。

   第二个版本的 `CPen` 构造函数为 *nPenStyle* 添加了以下笔样式：

- PS_ALTERNATE 创建一个用于设置其他每个像素的笔。  (此样式仅适用于修饰笔。 ) 

- PS_USERSTYLE 创建使用用户提供的样式数组的笔。

   结尾端可以是下列值之一：

- PS_ENDCAP_ROUND 的端帽为舍入。

- PS_ENDCAP_SQUARE 端帽为方形。

- PS_ENDCAP_FLAT 的结束端端。

   联接可以是以下值之一：

- PS_JOIN_BEVEL 联接是斜切的。

- 如果 PS_JOIN_MITER 联接在 [SetMiterLimit](/windows/win32/api/wingdi/nf-wingdi-setmiterlimit) 函数所设置的当前限制范围内，则会进行斜接。 如果联接超过此限制，则为倾斜。

- PS_JOIN_ROUND 联接是舍入的。

*nWidth*<br/>
指定笔的宽度。

- 对于第一个版本的构造函数，如果此值为0，则无论映射模式如何，设备单位中的宽度始终为1个像素。

- 对于第二个版本的构造函数，如果 *nPenStyle* PS_GEOMETRIC，则将在逻辑单元中提供宽度。 如果 PS_COSMETIC *nPenStyle* ，则必须将宽度设置为1。

*crColor*<br/>
包含用于笔的 RGB 颜色。

*pLogBrush*<br/>
指向 `LOGBRUSH` 结构。 如果 PS_COSMETIC *nPenStyle* ，则结构的 *lbColor* 成员指定了 `LOGBRUSH` 笔的颜色，并且必须将结构的 *lbStyle* 成员 `LOGBRUSH` 设置为 BS_SOLID。 如果 PS_GEOMETRIC *nPenStyle* ，则必须使用所有成员来指定笔的画笔属性。

*nStyleCount*<br/>
指定 *lpStyle* 数组的长度（以双字单位为单位）。 如果未 PS_USERSTYLE *nPenStyle* ，此值必须为零。

*lpStyle*<br/>
指向一组双字值。 第一个值指定用户定义样式中第一个短划线的长度，第二个值指定第一个空间的长度，依此类推。 如果未 PS_USERSTYLE *nPenStyle* ，则该指针必须为 NULL。

### <a name="remarks"></a>备注

如果使用不带参数的构造函数，则必须 `CPen` 使用 `CreatePen` 、 `CreatePenIndirect` 或 `CreateStockObject` 成员函数初始化生成的对象。

如果使用采用参数的构造函数，则不需要进行进一步的初始化。 如果遇到错误，带参数的构造函数可能会引发异常，而不带参数的构造函数将始终会成功。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#99](../../mfc/codesnippet/cpp/cpen-class_1.cpp)]

## <a name="cpencreatepen"></a><a name="createpen"></a> CPen：： CreatePen

使用指定的样式、宽度和画笔特性创建逻辑修饰或几何钢笔，并将其附加到 `CPen` 对象。

```
BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    COLORREF crColor);

BOOL CreatePen(
    int nPenStyle,
    int nWidth,
    const LOGBRUSH* pLogBrush,
    int nStyleCount = 0,
    const DWORD* lpStyle = NULL);
```

### <a name="parameters"></a>parameters

*nPenStyle*<br/>
指定笔的样式。 有关可能值的列表，请参阅 [CPen](#cpen)构造函数中的 *nPenStyle* 参数。

*nWidth*<br/>
指定笔的宽度。

- 对于的第一个版本 `CreatePen` ，如果此值为0，则无论映射模式如何，设备单位中的宽度始终为1个像素。

- 对于第二个版本的 `CreatePen` ，如果 *nPenStyle* PS_GEOMETRIC，则将在逻辑单元中给出宽度。 如果 PS_COSMETIC *nPenStyle* ，则必须将宽度设置为1。

*crColor*<br/>
包含用于笔的 RGB 颜色。

*pLogBrush*<br/>
指向 [LOGBRUSH](/windows/win32/api/wingdi/ns-wingdi-logbrush) 结构。 如果 PS_COSMETIC *nPenStyle* ，则 `lbColor` 结构的成员指定了笔的 `LOGBRUSH` 颜色，结构的 *lbStyle* 成员 `LOGBRUSH` 必须设置为 BS_SOLID。 如果 PS_GEOMETRIC nPenStyle，则必须使用所有成员来指定笔的画笔属性。

*nStyleCount*<br/>
指定 *lpStyle* 数组的长度（以双字单位为单位）。 如果未 PS_USERSTYLE *nPenStyle* ，此值必须为零。

*lpStyle*<br/>
指向一组双字值。 第一个值指定用户定义样式中第一个短划线的长度，第二个值指定第一个空间的长度，依此类推。 如果未 PS_USERSTYLE *nPenStyle* ，则该指针必须为 NULL。

### <a name="return-value"></a>返回值

如果成功，则为非零; 如果方法失败，则为零。

### <a name="remarks"></a>备注

的第一个版本 `CreatePen` 使用指定的样式、宽度和颜色初始化笔。 然后，可以选择该笔作为任何设备上下文的当前笔。

宽度大于1像素的笔应始终具有 PS_NULL、PS_SOLID 或 PS_INSIDEFRAME 样式。

如果笔的 PS_INSIDEFRAME 样式和颜色与逻辑颜色表中的颜色不符，则使用抖动颜色绘制笔。 PS_SOLID 笔样式不能用于创建抖动颜色的笔。 如果笔宽度小于或等于1，则样式 PS_INSIDEFRAME 与 PS_SOLID 相同。

第二个版本的 `CreatePen` 初始化具有指定样式、宽度和画笔特性的逻辑修饰笔或几何笔。 修饰笔的宽度始终为 1;几何笔的宽度始终以世界单位进行指定。 应用程序创建逻辑笔后，可以通过调用 [CDC：： SelectObject](../../mfc/reference/cdc-class.md#selectobject) 函数将该笔选择到设备上下文中。 在设备上下文中选择笔后，可将其用于绘制直线和曲线。

- 如果 *nPenStyle* PS_COSMETIC 并 PS_USERSTYLE，则 *lpStyle* 数组中的条目指定样式单位中的短划线和空格的长度。 样式单位由用于绘制线条的设备所定义。

- 如果 *nPenStyle* PS_GEOMETRIC 并 PS_USERSTYLE，则 *lpStyle* 数组中的条目指定逻辑单元中的短划线和空格的长度。

- 如果 PS_ALTERNATE *nPenStyle* ，将忽略样式单位，并设置每个其他像素。

当应用程序不再需要指定的笔时，它应调用 [CGdiObject：:D eleteobject](../../mfc/reference/cgdiobject-class.md#deleteobject) 成员函数或销毁该 `CPen` 对象，因此不再使用该资源。 在设备上下文中选择笔时，应用程序不应删除笔。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#100](../../mfc/codesnippet/cpp/cpen-class_2.cpp)]

## <a name="cpencreatepenindirect"></a><a name="createpenindirect"></a> CPen：： CreatePenIndirect

初始化一个笔，该笔具有在 *lpLogPen* 指向的结构中给定的样式、宽度和颜色。

```
BOOL CreatePenIndirect(LPLOGPEN lpLogPen);
```

### <a name="parameters"></a>parameters

*lpLogPen*<br/>
指向包含有关笔信息的 Windows [LOGPEN](/windows/win32/api/Wingdi/ns-wingdi-logpen) 结构。

### <a name="return-value"></a>返回值

如果该函数成功，则为非 0；否则为 0。

### <a name="remarks"></a>备注

宽度大于1像素的笔应始终具有 PS_NULL、PS_SOLID 或 PS_INSIDEFRAME 样式。

如果笔的 PS_INSIDEFRAME 样式和颜色与逻辑颜色表中的颜色不符，则使用抖动颜色绘制笔。 如果笔宽小于或等于1，则 PS_INSIDEFRAME 样式与 PS_SOLID 相同。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#101](../../mfc/codesnippet/cpp/cpen-class_3.cpp)]

## <a name="cpenfromhandle"></a><a name="fromhandle"></a> CPen：： FromHandle

返回一个指向对象的指针，该指针指向 `CPen` 给定 WINDOWS GDI 钢笔对象的句柄。

```
static CPen* PASCAL FromHandle(HPEN hPen);
```

### <a name="parameters"></a>parameters

*hPen*<br/>
`HPEN` Windows GDI 笔的句柄。

### <a name="return-value"></a>返回值

如果成功，则为指向对象的指针 `CPen` ; 否则为 NULL。

### <a name="remarks"></a>备注

如果 `CPen` 对象未附加到该句柄，则会创建并附加一个临时 `CPen` 对象。 此临时 `CPen` 对象仅在下一次应用程序的事件循环中有空闲时间时才有效，此时所有临时图形对象都会被删除。 换言之，只有在处理一条窗口消息的过程中，临时对象才有效。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#105](../../mfc/codesnippet/cpp/cpen-class_4.cpp)]

## <a name="cpengetextlogpen"></a><a name="getextlogpen"></a> CPen：： GetExtLogPen

获取 `EXTLOGPEN` 基础结构。

```
int GetExtLogPen(EXTLOGPEN* pLogPen);
```

### <a name="parameters"></a>parameters

*pLogPen*<br/>
指向包含有关笔信息的 [EXTLOGPEN](/windows/win32/api/wingdi/ns-wingdi-extlogpen) 结构。

### <a name="return-value"></a>返回值

如果成功，则不为 0；否则为 0。

### <a name="remarks"></a>备注

`EXTLOGPEN`结构定义了笔的样式、宽度和画笔特性。 例如，调用 `GetExtLogPen` 来匹配笔的特定样式。

有关笔属性的信息，请参阅 Windows SDK 中的以下主题：

- [GetObject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [EXTLOGPEN](/windows/win32/api/wingdi/ns-wingdi-extlogpen)

- [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen)

- [ExtCreatePen](/windows/win32/api/wingdi/nf-wingdi-extcreatepen)

### <a name="example"></a>示例

下面的代码示例演示了 `GetExtLogPen` 如何调用来检索笔的属性，然后创建一个具有相同颜色的新修饰笔。

[!code-cpp[NVC_MFCDocView#102](../../mfc/codesnippet/cpp/cpen-class_5.cpp)]

## <a name="cpengetlogpen"></a><a name="getlogpen"></a> CPen：： GetLogPen

获取 `LOGPEN` 基础结构。

```
int GetLogPen(LOGPEN* pLogPen);
```

### <a name="parameters"></a>parameters

*pLogPen*<br/>
指向 [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen) 结构以包含有关笔的信息。

### <a name="return-value"></a>返回值

如果成功，则不为 0；否则为 0。

### <a name="remarks"></a>备注

`LOGPEN`结构定义了笔的样式、颜色和模式。

例如，调用 `GetLogPen` 以匹配特定的钢笔样式。

有关笔属性的信息，请参阅 Windows SDK 中的以下主题：

- [GetObject](/windows/win32/api/wingdi/nf-wingdi-getobject)

- [LOGPEN](/windows/win32/api/wingdi/ns-wingdi-logpen)

### <a name="example"></a>示例

下面的代码示例演示 `GetLogPen` 如何调用来检索笔字符，然后创建一个具有相同颜色的新的纯色画笔。

[!code-cpp[NVC_MFCDocView#103](../../mfc/codesnippet/cpp/cpen-class_6.cpp)]

## <a name="cpenoperator-hpen"></a><a name="operator_hpen"></a> CPen：： operator HPEN

获取对象的附加 Windows GDI 句柄 `CPen` 。

```
operator HPEN() const;
```

### <a name="return-value"></a>返回值

如果成功，则为对象表示的 Windows GDI 对象的句柄 `CPen` ; 否则为 NULL。

### <a name="remarks"></a>备注

此运算符是支持直接使用 HPEN 对象的强制转换运算符。

有关使用图形对象的详细信息，请参阅文章 Windows SDK 中的 [图形对象](/windows/win32/gdi/graphic-objects) 。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#104](../../mfc/codesnippet/cpp/cpen-class_7.cpp)]

## <a name="see-also"></a>请参阅

[CGdiObject 类](../../mfc/reference/cgdiobject-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CBrush 类](../../mfc/reference/cbrush-class.md)
