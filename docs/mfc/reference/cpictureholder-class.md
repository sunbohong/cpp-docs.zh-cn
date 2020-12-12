---
description: 了解详细信息： CPictureHolder 类
title: CPictureHolder 类
ms.date: 11/04/2016
f1_keywords:
- CPictureHolder
- AFXCTL/CPictureHolder
- AFXCTL/CPictureHolder::CPictureHolder
- AFXCTL/CPictureHolder::CreateEmpty
- AFXCTL/CPictureHolder::CreateFromBitmap
- AFXCTL/CPictureHolder::CreateFromIcon
- AFXCTL/CPictureHolder::CreateFromMetafile
- AFXCTL/CPictureHolder::GetDisplayString
- AFXCTL/CPictureHolder::GetPictureDispatch
- AFXCTL/CPictureHolder::GetType
- AFXCTL/CPictureHolder::Render
- AFXCTL/CPictureHolder::SetPictureDispatch
- AFXCTL/CPictureHolder::m_pPict
helpviewer_keywords:
- CPictureHolder [MFC], CPictureHolder
- CPictureHolder [MFC], CreateEmpty
- CPictureHolder [MFC], CreateFromBitmap
- CPictureHolder [MFC], CreateFromIcon
- CPictureHolder [MFC], CreateFromMetafile
- CPictureHolder [MFC], GetDisplayString
- CPictureHolder [MFC], GetPictureDispatch
- CPictureHolder [MFC], GetType
- CPictureHolder [MFC], Render
- CPictureHolder [MFC], SetPictureDispatch
- CPictureHolder [MFC], m_pPict
ms.assetid: a4f59775-704a-41dd-b5bd-2e531c95127a
ms.openlocfilehash: 47eacb66191e21b300aaa0d06bc23155fabaf651
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97301472"
---
# <a name="cpictureholder-class"></a>CPictureHolder 类

实现图片属性，该属性允许用户在控件中显示图片。

## <a name="syntax"></a>语法

```
class CPictureHolder
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CPictureHolder：： CPictureHolder](#cpictureholder)|构造 `CPictureHolder` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CPictureHolder：： CreateEmpty](#createempty)|创建一个空的 `CPictureHolder` 对象。|
|[CPictureHolder：： CreateFromBitmap](#createfrombitmap)|`CPictureHolder`从位图创建对象。|
|[CPictureHolder：： CreateFromIcon](#createfromicon)|`CPictureHolder`从图标创建对象。|
|[CPictureHolder：： CreateFromMetafile](#createfrommetafile)|`CPictureHolder`从图元文件创建对象。|
|[CPictureHolder：： GetDisplayString](#getdisplaystring)|检索控件容器的属性浏览器中显示的字符串。|
|[CPictureHolder：： GetPictureDispatch](#getpicturedispatch)|返回 `CPictureHolder` 对象的 `IDispatch` 接口。|
|[CPictureHolder：： GetType](#gettype)|指示 `CPictureHolder` 对象是位图、图元文件还是图标。|
|[CPictureHolder：： Render](#render)|呈现图片。|
|[CPictureHolder：： SetPictureDispatch](#setpicturedispatch)|设置 `CPictureHolder` 对象的 `IDispatch` 接口。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CPictureHolder：： m_pPict](#m_ppict)|指向图片对象的指针。|

## <a name="remarks"></a>备注

`CPictureHolder` 没有基类。

使用 "股票头像" 属性，开发人员可以指定要显示的位图、图标或图元文件。

有关创建自定义图片属性的信息，请参阅文章 [MFC Activex 控件：在 Activex 控件中使用图片](../../mfc/mfc-activex-controls-using-pictures-in-an-activex-control.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CPictureHolder`

## <a name="requirements"></a>要求

**标头：** afxctl。h

## <a name="cpictureholdercpictureholder"></a><a name="cpictureholder"></a> CPictureHolder：： CPictureHolder

构造 `CPictureHolder` 对象。

```
CPictureHolder();
```

## <a name="cpictureholdercreateempty"></a><a name="createempty"></a> CPictureHolder：： CreateEmpty

创建一个空的 `CPictureHolder` 对象，并将其连接到一个 `IPicture` 接口。

```
BOOL CreateEmpty();
```

### <a name="return-value"></a>返回值

如果成功创建对象，则为非零值;否则为0。

## <a name="cpictureholdercreatefrombitmap"></a><a name="createfrombitmap"></a> CPictureHolder：： CreateFromBitmap

使用位图初始化中的图片对象 `CPictureHolder` 。

```
BOOL CreateFromBitmap(
    UINT idResource);

BOOL CreateFromBitmap(
    CBitmap* pBitmap,
    CPalette* pPal = NULL,
    BOOL bTransferOwnership = TRUE);

BOOL CreateFromBitmap(
    HBITMAP hbm,
    HPALETTE hpal = NULL,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>parameters

*idResource*<br/>
位图资源的资源 ID。

*pBitmap*<br/>
指向 [CBitmap](../../mfc/reference/cbitmap-class.md) 对象的指针。

*pPal*<br/>
指向 [CPalette](../../mfc/reference/cpalette-class.md) 对象的指针。

*bTransferOwnership*<br/>
指示图片对象是否将获取位图和调色板对象的所有权。

*hbm*<br/>
用于创建对象的位图的句柄 `CPictureHolder` 。

*hpal*<br/>
用于呈现位图的调色板的句柄。

### <a name="return-value"></a>返回值

如果成功创建对象，则为非零值;否则为0。

### <a name="remarks"></a>备注

如果 *bTransferOwnership* 为 TRUE，则调用方不应在此调用返回后以任何方式使用位图或调色板对象。 如果 *bTransferOwnership* 为 FALSE，则调用方负责确保位图和调色板对象在图片对象的生存期内保持有效。

## <a name="cpictureholdercreatefromicon"></a><a name="createfromicon"></a> CPictureHolder：： CreateFromIcon

使用图标初始化中的图片对象 `CPictureHolder` 。

```
BOOL CreateFromIcon(
    UINT idResource);

BOOL CreateFromIcon(
    HICON hIcon,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>parameters

*idResource*<br/>
位图资源的资源 ID。

*hIcon*<br/>
用于创建对象的图标的句柄 `CPictureHolder` 。

*bTransferOwnership*<br/>
指示图片对象是否将获得 icon 对象的所有权。

### <a name="return-value"></a>返回值

如果成功创建对象，则为非零值;否则为0。

### <a name="remarks"></a>备注

如果 *bTransferOwnership* 为 TRUE，则调用方不应在此调用返回后以任何方式使用 icon 对象。 如果 *bTransferOwnership* 为 FALSE，则调用方负责确保图标对象在图片对象的生存期内保持有效。

## <a name="cpictureholdercreatefrommetafile"></a><a name="createfrommetafile"></a> CPictureHolder：： CreateFromMetafile

使用图元文件初始化中的图片对象 `CPictureHolder` 。

```
BOOL CreateFromMetafile(
    HMETAFILE hmf,
    int xExt,
    int yExt,
    BOOL bTransferOwnership = FALSE);
```

### <a name="parameters"></a>parameters

*hmf*<br/>
用于创建对象的图元文件的句柄 `CPictureHolder` 。

*xExt*<br/>
图片的 X 范围。

*yExt*<br/>
图片的 Y 范围。

*bTransferOwnership*<br/>
指示图片对象是否将获取图元文件对象的所有权。

### <a name="return-value"></a>返回值

如果成功创建对象，则为非零值;否则为0。

### <a name="remarks"></a>备注

如果 *bTransferOwnership* 为 TRUE，则调用方不应在此调用返回后以任何方式使用图元文件对象。 如果 *bTransferOwnership* 为 FALSE，则调用方负责确保图元文件对象在图片对象的生存期内保持有效。

## <a name="cpictureholdergetdisplaystring"></a><a name="getdisplaystring"></a> CPictureHolder：： GetDisplayString

检索容器的属性浏览器中显示的字符串。

```
BOOL GetDisplayString(CString& strValue);
```

### <a name="parameters"></a>parameters

*strValue*<br/>
对用于保存显示字符串的 [CString](../../atl-mfc-shared/reference/cstringt-class.md) 的引用。

### <a name="return-value"></a>返回值

如果成功检索到该字符串，则为非零值;否则为0。

## <a name="cpictureholdergetpicturedispatch"></a><a name="getpicturedispatch"></a> CPictureHolder：： GetPictureDispatch

此函数返回指向 `CPictureHolder` 对象接口的指针 `IPictureDisp` 。

```
LPPICTUREDISP GetPictureDispatch();
```

### <a name="return-value"></a>返回值

指向 `CPictureHolder` 对象接口的指针 `IPictureDisp` 。

### <a name="remarks"></a>备注

完成后，调用方必须 `Release` 对此指针调用。

## <a name="cpictureholdergettype"></a><a name="gettype"></a> CPictureHolder：： GetType

指示图片是位图、图元文件还是图标。

```
short GetType();
```

### <a name="return-value"></a>返回值

指示图片类型的值。 可能的值及其含义如下：

|值|含义|
|-----------|-------------|
|PICTYPE_UNINITIALIZED|`CPictureHolder` 对象为 unititialized。|
|PICTYPE_NONE|`CPictureHolder` 对象为空。|
|PICTYPE_BITMAP|图片是位图。|
|PICTYPE_METAFILE|图片为图元文件。|
|PICTYPE_ICON|图片为图标。|

## <a name="cpictureholderm_ppict"></a><a name="m_ppict"></a> CPictureHolder：： m_pPict

指向 `CPictureHolder` 对象接口的指针 `IPicture` 。

```
LPPICTURE m_pPict;
```

## <a name="cpictureholderrender"></a><a name="render"></a> CPictureHolder：： Render

在 *rcRender* 引用的矩形中呈现图片。

```cpp
void Render(
    CDC* pDC,
    const CRect& rcRender,
    const CRect& rcWBounds);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
指向要在其中呈现图片的显示上下文的指针。

*rcRender*<br/>
要在其中呈现图片的矩形。

*rcWBounds*<br/>
一个矩形，表示呈现图片的对象的边框。 对于控件，此矩形是传递到 [COleControl：： OnDraw](../../mfc/reference/colecontrol-class.md#ondraw)的重写的 *rcBounds* 参数。

## <a name="cpictureholdersetpicturedispatch"></a><a name="setpicturedispatch"></a> CPictureHolder：： SetPictureDispatch

将 `CPictureHolder` 对象连接到 `IPictureDisp` 接口。

```cpp
void SetPictureDispatch(LPPICTUREDISP pDisp);
```

### <a name="parameters"></a>parameters

*pDisp*<br/>
指向新接口的指针 `IPictureDisp` 。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CFontHolder 类](../../mfc/reference/cfontholder-class.md)
