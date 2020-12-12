---
description: 了解详细信息： CMFCRibbonSeparator 类
title: CMFCRibbonSeparator 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CMFCRibbonSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::AddToListBox
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::CopyFrom
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::GetRegularSize
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsSeparator
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::IsTabStop
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDraw
- AFXBASERIBBONELEMENT/CMFCRibbonSeparator::OnDrawOnList
helpviewer_keywords:
- CMFCRibbonSeparator [MFC], CMFCRibbonSeparator
- CMFCRibbonSeparator [MFC], AddToListBox
- CMFCRibbonSeparator [MFC], CopyFrom
- CMFCRibbonSeparator [MFC], GetRegularSize
- CMFCRibbonSeparator [MFC], IsSeparator
- CMFCRibbonSeparator [MFC], IsTabStop
- CMFCRibbonSeparator [MFC], OnDraw
- CMFCRibbonSeparator [MFC], OnDrawOnList
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
ms.openlocfilehash: db8e7f92089d1e6332fdb2ad057398c465c72f97
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321743"
---
# <a name="cmfcribbonseparator-class"></a>CMFCRibbonSeparator 类

实现功能区分隔符。

## <a name="syntax"></a>语法

```
class CMFCRibbonSeparator : public CMFCRibbonBaseElement
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|-|-|
|[CMFCRibbonSeparator::CMFCRibbonSeparator](#cmfcribbonseparator)|构造 `CMFCRibbonSeparator` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|-|-|
|[CMFCRibbonSeparator::AddToListBox](#addtolistbox)|将分隔符添加到 "**自定义**" 对话框的 "**命令**" 列表中。  (重写 [CMFCRibbonBaseElement：： AddToListBox](../../mfc/reference/cmfcribbonbaseelement-class.md#addtolistbox)。 ) |
|`CMFCRibbonSeparator::CreateObject`|由框架用于创建此类类型的动态实例。|
|`CMFCRibbonSeparator::GetThisClass`|由框架用于获取指向与此类类型相关联的 [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) 对象的指针。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|-|-|
|[CMFCRibbonSeparator：： CopyFrom](#copyfrom)|一种从另一个对象设置分隔符的成员变量的复制方法。|
|[CMFCRibbonSeparator：： GetRegularSize](#getregularsize)|返回分隔符的大小。|
|[CMFCRibbonSeparator::IsSeparator](#isseparator)|指示此是否为分隔符。|
|[CMFCRibbonSeparator::IsTabStop](#istabstop)|指示这是否为制表位。|
|[CMFCRibbonSeparator：： OnDraw](#ondraw)|由系统调用，用于在功能区或快速访问工具栏上绘制分隔符。|
|[CMFCRibbonSeparator::OnDrawOnList](#ondrawonlist)|由系统调用，用于在 **命令** 列表中绘制分隔符。|

## <a name="remarks"></a>备注

功能区分隔符是以逻辑方式分隔功能区元素的垂直或水平线条。 可以在功能区控件、主应用程序菜单、功能区状态栏和快速访问工具栏上绘制分隔符。

若要在应用程序中使用分隔符，请构造新的对象并将其添加到主应用程序菜单，如下所示：

```
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"),
    IDB_FILESMALL,
    IDB_FILELARGE);

...
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));
```

调用 [CMFCRibbonPanel：： AddSeparator](../../mfc/reference/cmfcribbonpanel-class.md#addseparator) 将分隔符添加到功能区面板。 分隔符由方法在内部进行分配和添加 `AddSeparator` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)

[CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)

## <a name="requirements"></a>要求

**标头：** afxbaseribbonelement.h

## <a name="cmfcribbonseparatoraddtolistbox"></a><a name="addtolistbox"></a> CMFCRibbonSeparator::AddToListBox

将分隔符添加到 "**自定义**" 对话框的 "**命令**" 列表中。

```
virtual int AddToListBox(
    CMFCRibbonCommandsListBox* pWndListBox,
    BOOL bDeep);
```

### <a name="parameters"></a>parameters

*pWndListBox*<br/>
中指向添加了分隔符的 **命令** 列表的指针。

*bDeep*<br/>
中掉.

### <a name="return-value"></a>返回值

*PWndListBox* 指定的列表框中的字符串的从零开始的索引。

## <a name="cmfcribbonseparatorcmfcribbonseparator"></a><a name="cmfcribbonseparator"></a> CMFCRibbonSeparator::CMFCRibbonSeparator

构造 `CMFCRibbonSeparator` 对象。

```
CMFCRibbonSeparator(BOOL bIsHoriz = FALSE);
```

### <a name="parameters"></a>parameters

*bIsHoriz*<br/>
中如果为 TRUE，则分隔符为水平;如果为 FALSE，则分隔符是垂直的。

### <a name="remarks"></a>备注

在应用程序菜单中使用水平分隔符。 在工具栏中使用垂直分隔符。

### <a name="example"></a>示例

下面的示例演示如何构造类的对象 `CMFCRibbonSeparator` 。

[!code-cpp[NVC_MFC_RibbonApp#19](../../mfc/reference/codesnippet/cpp/cmfcribbonseparator-class_1.cpp)]

## <a name="cmfcribbonseparatorcopyfrom"></a><a name="copyfrom"></a> CMFCRibbonSeparator：： CopyFrom

一种从另一个对象设置分隔符的成员变量的复制方法。

```
virtual void CopyFrom(const CMFCRibbonBaseElement& src);
```

### <a name="parameters"></a>parameters

*源*<br/>
中要从中进行复制的源功能区元素。

## <a name="cmfcribbonseparatorgetregularsize"></a><a name="getregularsize"></a> CMFCRibbonSeparator：： GetRegularSize

返回分隔符的大小。

```
virtual CSize GetRegularSize(CDC* pDC);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向设备内容的指针。

### <a name="return-value"></a>返回值

给定设备上下文的分隔符大小。

## <a name="cmfcribbonseparatorisseparator"></a><a name="isseparator"></a> CMFCRibbonSeparator::IsSeparator

指示此是否为分隔符。

```
virtual BOOL IsSeparator() const;
```

### <a name="return-value"></a>返回值

对于此类始终为 TRUE。

## <a name="cmfcribbonseparatoristabstop"></a><a name="istabstop"></a> CMFCRibbonSeparator::IsTabStop

指示这是否为制表位。

```
virtual BOOL IsTabStop() const;
```

### <a name="return-value"></a>返回值

对于此类始终为 FALSE。

### <a name="remarks"></a>备注

功能区分隔符不是制表位。

## <a name="cmfcribbonseparatorondraw"></a><a name="ondraw"></a> CMFCRibbonSeparator：： OnDraw

由系统调用，用于在功能区或快速访问工具栏上绘制分隔符。

```
virtual void OnDraw(CDC* pDC);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向设备上下文的指针。

## <a name="cmfcribbonseparatorondrawonlist"></a><a name="ondrawonlist"></a> CMFCRibbonSeparator::OnDrawOnList

由系统调用，用于在 **命令** 列表中绘制分隔符。

```
virtual void OnDrawOnList(
    CDC* pDC,
    CString strText,
    int nTextOffset,
    CRect rect,
    BOOL bIsSelected,
    BOOL bHighlighted);
```

### <a name="parameters"></a>parameters

*pDC*\
中指向设备上下文的指针。

*strText*\
中列表中显示的文本。

*nTextOffset*\
中文本与边框左边的间距。

*rect*\
中指定边框。

*bIsSelected*\
中掉.

*bHighlighted*\
中掉.

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[类](../../mfc/reference/mfc-classes.md)
