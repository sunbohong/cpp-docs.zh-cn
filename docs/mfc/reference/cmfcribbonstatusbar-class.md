---
description: 了解详细信息： CMFCRibbonStatusBar 类
title: CMFCRibbonStatusBar 类
ms.date: 11/04/2016
f1_keywords:
- CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddDynamicElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::AddSeparator
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::Create
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::CreateEx
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindByID
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::FindElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExCount
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetExtendedArea
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::GetSpace
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsBottomFrame
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsExtendedElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::IsInformationMode
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RecalcLayout
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveAll
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::RemoveElement
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::SetInformation
- AFXRIBBONSTATUSBAR/CMFCRibbonStatusBar::OnDrawInformation
helpviewer_keywords:
- CMFCRibbonStatusBar [MFC], AddDynamicElement
- CMFCRibbonStatusBar [MFC], AddElement
- CMFCRibbonStatusBar [MFC], AddExtendedElement
- CMFCRibbonStatusBar [MFC], AddSeparator
- CMFCRibbonStatusBar [MFC], Create
- CMFCRibbonStatusBar [MFC], CreateEx
- CMFCRibbonStatusBar [MFC], FindByID
- CMFCRibbonStatusBar [MFC], FindElement
- CMFCRibbonStatusBar [MFC], GetCount
- CMFCRibbonStatusBar [MFC], GetElement
- CMFCRibbonStatusBar [MFC], GetExCount
- CMFCRibbonStatusBar [MFC], GetExElement
- CMFCRibbonStatusBar [MFC], GetExtendedArea
- CMFCRibbonStatusBar [MFC], GetSpace
- CMFCRibbonStatusBar [MFC], IsBottomFrame
- CMFCRibbonStatusBar [MFC], IsExtendedElement
- CMFCRibbonStatusBar [MFC], IsInformationMode
- CMFCRibbonStatusBar [MFC], RecalcLayout
- CMFCRibbonStatusBar [MFC], RemoveAll
- CMFCRibbonStatusBar [MFC], RemoveElement
- CMFCRibbonStatusBar [MFC], SetInformation
- CMFCRibbonStatusBar [MFC], OnDrawInformation
ms.assetid: 921eb57f-3b40-49fa-a38c-3f2fb6dc2893
ms.openlocfilehash: 01436d535b410fd4a6c70f52760908e3547b7af8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264994"
---
# <a name="cmfcribbonstatusbar-class"></a>CMFCRibbonStatusBar 类

`CMFCRibbonStatusBar`类实现可显示功能区元素的状态栏控件。

## <a name="syntax"></a>语法

```
class CMFCRibbonStatusBar : public CMFCRibbonBar
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCRibbonStatusBar::AddDynamicElement](#adddynamicelement)|将动态元素添加到功能区状态栏。|
|[CMFCRibbonStatusBar::AddElement](#addelement)|将新的功能区元素添加到功能区状态栏。|
|[CMFCRibbonStatusBar::AddExtendedElement](#addextendedelement)|将功能区元素添加到功能区状态栏的扩展区域中。|
|[CMFCRibbonStatusBar::AddSeparator](#addseparator)|将分隔符添加到功能区状态栏。|
|[CMFCRibbonStatusBar：： Create](#create)|创建功能区状态栏。|
|[CMFCRibbonStatusBar：： CreateEx](#createex)|创建具有扩展样式的功能区状态栏。|
|[CMFCRibbonStatusBar：： FindByID](#findbyid)||
|[CMFCRibbonStatusBar::FindElement](#findelement)|返回一个指向元素的指针，该元素具有指定的命令 ID。|
|[CMFCRibbonStatusBar：： GetCount](#getcount)|返回位于功能区状态栏的主区域中的元素数。|
|[CMFCRibbonStatusBar：： GetElement](#getelement)|返回指向位于指定索引处的元素的指针。|
|[CMFCRibbonStatusBar::GetExCount](#getexcount)|返回位于功能区状态栏扩展区域中的元素数。|
|[CMFCRibbonStatusBar::GetExElement](#getexelement)|返回指向元素的指针，该元素位于功能区状态栏扩展区域中的指定索引处。|
|[CMFCRibbonStatusBar::GetExtendedArea](#getextendedarea)||
|[CMFCRibbonStatusBar::GetSpace](#getspace)||
|[CMFCRibbonStatusBar::IsBottomFrame](#isbottomframe)||
|[CMFCRibbonStatusBar::IsExtendedElement](#isextendedelement)||
|[CMFCRibbonStatusBar::IsInformationMode](#isinformationmode)|确定是否为功能区状态栏启用信息模式。|
|[CMFCRibbonStatusBar：： RecalcLayout](#recalclayout)| (重写 [CMFCRibbonBar：： RecalcLayout](../../mfc/reference/cmfcribbonbar-class.md#recalclayout)。 ) |
|[CMFCRibbonStatusBar：： RemoveAll](#removeall)|从功能区状态栏中移除所有元素。|
|[CMFCRibbonStatusBar：： RemoveElement](#removeelement)|从功能区状态栏中移除具有指定命令 ID 的元素。|
|[CMFCRibbonStatusBar::SetInformation](#setinformation)|启用或禁用功能区状态栏的信息模式。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CMFCRibbonStatusBar::OnDrawInformation](#ondrawinformation)|当启用信息模式时，显示在功能区状态栏上显示的信息字符串。|

## <a name="remarks"></a>备注

用户可以通过使用功能区状态栏的内置上下文菜单来更改功能区状态栏上的功能区元素的可见性。 您可以动态添加或删除元素。

功能区状态栏有两个区域：一个主区域和一个扩展区域。 扩展区域显示在功能区状态栏的右侧，并以不同于主要区域的颜色显示。

通常，状态栏的主要区域显示状态通知，并且扩展区域显示视图控件。 当用户调整功能区状态栏时，扩展区域会尽可能长地保持可见。

## <a name="example"></a>示例

下面的示例演示了如何使用 `CMFCRibbonStatusBar` 类中的各种方法。 该示例演示如何将新的功能区元素添加到功能区状态栏，将功能区元素添加到功能区状态栏的扩展区域，添加分隔符，并为功能区状态栏启用常规模式。

[!code-cpp[NVC_MFC_RibbonApp#15](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_1.cpp)]
[!code-cpp[NVC_MFC_RibbonApp#16](../../mfc/reference/codesnippet/cpp/cmfcribbonstatusbar-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CBasePane](../../mfc/reference/cbasepane-class.md)

[CPane](../../mfc/reference/cpane-class.md)

[CMFCRibbonBar](../../mfc/reference/cmfcribbonbar-class.md)

[CMFCRibbonStatusBar](../../mfc/reference/cmfcribbonstatusbar-class.md)

## <a name="requirements"></a>要求

**标头：** afxribbonstatusbar

## <a name="cmfcribbonstatusbaradddynamicelement"></a><a name="adddynamicelement"></a> CMFCRibbonStatusBar::AddDynamicElement

将动态元素添加到功能区状态栏。

```cpp
void AddDynamicElement(CMFCRibbonBaseElement* pElement);
```

### <a name="parameters"></a>parameters

*pElement*<br/>
中指向动态元素的指针。

### <a name="remarks"></a>备注

与常规元素不同，动态元素不可自定义，状态栏的 "自定义" 菜单不会显示它们。

## <a name="cmfcribbonstatusbaraddelement"></a><a name="addelement"></a> CMFCRibbonStatusBar::AddElement

将新的功能区元素添加到功能区状态栏。

```cpp
void AddElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>parameters

*pElement*<br/>
中指向已添加元素的指针。

*lpszLabel*<br/>
中元素的文本标签。

*bIsVisible*<br/>
中如果要将元素添加为可见，则为 TRUE; 如果要将元素添加为隐藏，则为 FALSE。

## <a name="cmfcribbonstatusbaraddextendedelement"></a><a name="addextendedelement"></a> CMFCRibbonStatusBar::AddExtendedElement

将功能区元素添加到功能区状态栏的扩展区域中。

```cpp
void AddExtendedElement(
    CMFCRibbonBaseElement* pElement,
    LPCTSTR lpszLabel,
    BOOL bIsVisible=TRUE);
```

### <a name="parameters"></a>parameters

*pElement*<br/>
中指向已添加元素的指针。

*lpszLabel*<br/>
中元素的文本标签。

*bIsVisible*<br/>
中如果要将元素添加为可见，则为 TRUE; 如果要将元素添加为隐藏，则为 FALSE。

### <a name="remarks"></a>备注

扩展区域位于状态栏控件的右侧。

## <a name="cmfcribbonstatusbaraddseparator"></a><a name="addseparator"></a> CMFCRibbonStatusBar::AddSeparator

将分隔符添加到功能区状态栏。

```cpp
void AddSeparator();
```

### <a name="remarks"></a>备注

该框架在方法 [CMFCRibbonStatusBar：： AddElement](#addelement)后面添加一个分隔符。 插入最后一个元素。

## <a name="cmfcribbonstatusbarcreate"></a><a name="create"></a> CMFCRibbonStatusBar：： Create

创建功能区状态栏。

```
BOOL Create(
    CWnd* pParentWnd,
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,
    UINT nID=AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>parameters

*pParentWnd*<br/>
中指向父窗口的指针。

*dwStyle*<br/>
中控件样式的逻辑或组合。

*nID*<br/>
中状态栏的控件 ID。

### <a name="return-value"></a>返回值

如果成功创建状态栏，则为 TRUE; 否则为 FALSE。

## <a name="cmfcribbonstatusbarcreateex"></a><a name="createex"></a> CMFCRibbonStatusBar：： CreateEx

创建具有扩展样式的功能区状态栏。

```
BOOL CreateEx(
    CWnd* pParentWnd,
    DWORD dwCtrlStyle=0,
    DWORD dwStyle=WS_CHILD|WS_VISIBLE|CBRS_BOTTOM,
    UINT nID=AFX_IDW_STATUS_BAR);
```

### <a name="parameters"></a>parameters

*pParentWnd*<br/>
指向父窗口的指针。

*dwCtrlStyle*<br/>
用于创建状态栏对象的其他样式的逻辑或组合。

*dwStyle*<br/>
状态栏的控件样式。

*nID*<br/>
状态栏的控件 ID。

### <a name="return-value"></a>返回值

如果成功创建状态栏，则为 TRUE; 否则为 FALSE。

## <a name="cmfcribbonstatusbarfindbyid"></a><a name="findbyid"></a> CMFCRibbonStatusBar：： FindByID

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
CMFCRibbonBaseElement* FindByID(UINT uiCmdID, BOOL = TRUE);
```

### <a name="parameters"></a>parameters

中 *uiCmdID*<br/>
中 *BOOL*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcribbonstatusbarfindelement"></a><a name="findelement"></a> CMFCRibbonStatusBar::FindElement

返回一个指向元素的指针，该元素具有指定的命令 ID。

```
CMFCRibbonBaseElement* FindElement(UINT uiID);
```

### <a name="parameters"></a>parameters

*uiID*<br/>
中元素的 ID。

### <a name="return-value"></a>返回值

指向元素的指针，该元素具有指定的命令 ID。 如果没有此类元素，则为 NULL。

## <a name="cmfcribbonstatusbargetcount"></a><a name="getcount"></a> CMFCRibbonStatusBar：： GetCount

返回位于功能区状态栏的主区域中的元素数。

```
int GetCount() const;
```

### <a name="return-value"></a>返回值

位于功能区状态栏的主区域中的元素数。

## <a name="cmfcribbonstatusbargetelement"></a><a name="getelement"></a> CMFCRibbonStatusBar：： GetElement

返回指向位于指定索引处的元素的指针。

```
CMFCRibbonBaseElement* GetElement(int nIndex);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
中指定元素的从零开始的索引，该元素位于状态栏控件的主区域中。

### <a name="return-value"></a>返回值

指向位于指定索引处的元素的指针。 如果索引为负数或超出状态栏中的元素数，则为 NULL。

### <a name="remarks"></a>备注

## <a name="cmfcribbonstatusbargetexcount"></a><a name="getexcount"></a> CMFCRibbonStatusBar::GetExCount

返回位于功能区状态栏扩展区域中的元素数。

```
int GetExCount() const;
```

### <a name="return-value"></a>返回值

位于功能区状态栏扩展区域中的元素数。

## <a name="cmfcribbonstatusbargetexelement"></a><a name="getexelement"></a> CMFCRibbonStatusBar::GetExElement

返回指向元素的指针，该元素位于功能区状态栏扩展区域中的指定索引处。 扩展区域位于状态栏控件的右侧。

```
CMFCRibbonBaseElement* GetExElement(int nIndex);
```

### <a name="parameters"></a>parameters

*nIndex*<br/>
中指定位于状态栏控件的扩展区域中的元素的索引（索引从零开始）。

### <a name="return-value"></a>返回值

一个指向元素的指针，该元素位于功能区状态栏扩展区域中的指定索引处。 如果 *nIndex* 为负数或超出功能区状态栏的扩展区域中的元素数，则为 NULL。

### <a name="remarks"></a>备注

## <a name="cmfcribbonstatusbargetextendedarea"></a><a name="getextendedarea"></a> CMFCRibbonStatusBar::GetExtendedArea

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
virtual BOOL GetExtendedArea(CRect& rect) const;
```

### <a name="parameters"></a>parameters

中 *rect*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcribbonstatusbargetspace"></a><a name="getspace"></a> CMFCRibbonStatusBar::GetSpace

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
int GetSpace() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcribbonstatusbarisbottomframe"></a><a name="isbottomframe"></a> CMFCRibbonStatusBar::IsBottomFrame

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
BOOL IsBottomFrame() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcribbonstatusbarisextendedelement"></a><a name="isextendedelement"></a> CMFCRibbonStatusBar::IsExtendedElement

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
BOOL IsExtendedElement(CMFCRibbonBaseElement* pElement) const;
```

### <a name="parameters"></a>parameters

中 *pElement*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcribbonstatusbarisinformationmode"></a><a name="isinformationmode"></a> CMFCRibbonStatusBar::IsInformationMode

确定是否为功能区状态栏启用信息模式。

```
BOOL IsInformationMode() const;
```

### <a name="return-value"></a>返回值

如果状态栏可以在信息模式下工作，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

在 "信息模式" 中，状态栏将隐藏所有常规窗格并显示消息字符串。

## <a name="cmfcribbonstatusbarondrawinformation"></a><a name="ondrawinformation"></a> CMFCRibbonStatusBar::OnDrawInformation

当启用信息模式时，显示在功能区状态栏上显示的字符串。

```
virtual void OnDrawInformation(
    CDC* pDC,
    CString& strInfo,
    CRect rectInfo);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向设备上下文的指针。

*strInfo*<br/>
中信息字符串。

*rectInfo*<br/>
中边框。

### <a name="remarks"></a>备注

如果要自定义状态栏上信息字符串的外观，请在派生类中重写此方法。 使用 [CMFCRibbonStatusBar：： SetInformation](#setinformation) 方法将状态栏置于信息模式。 在此模式下，状态栏将隐藏所有窗格，并显示由 *strInfo* 指定的信息字符串。

## <a name="cmfcribbonstatusbarrecalclayout"></a><a name="recalclayout"></a> CMFCRibbonStatusBar：： RecalcLayout

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
virtual void RecalcLayout();
```

### <a name="remarks"></a>备注

## <a name="cmfcribbonstatusbarremoveall"></a><a name="removeall"></a> CMFCRibbonStatusBar：： RemoveAll

从功能区状态栏中移除所有元素。

```cpp
void RemoveAll();
```

## <a name="cmfcribbonstatusbarremoveelement"></a><a name="removeelement"></a> CMFCRibbonStatusBar：： RemoveElement

从功能区状态栏中移除具有指定命令 ID 的元素。

```
BOOL RemoveElement(UINT uiID);
```

### <a name="parameters"></a>parameters

*uiID*<br/>
中要从状态栏中移除的元素的 ID。

### <a name="return-value"></a>返回值

如果删除具有指定 *uiID* 的元素，则为 TRUE。 否则为 FALSE。

## <a name="cmfcribbonstatusbarsetinformation"></a><a name="setinformation"></a> CMFCRibbonStatusBar::SetInformation

启用或禁用功能区状态栏的信息模式。

```cpp
void SetInformation(LPCTSTR lpszInfo);
```

### <a name="parameters"></a>parameters

*lpszInfo*<br/>
中信息字符串。

### <a name="remarks"></a>备注

使用此方法将状态栏置于信息模式。 在此模式下，状态栏将隐藏所有窗格，并显示由 *lpszInfo* 指定的信息字符串。

当 lpszInfo 为 NULL 时，状态栏将恢复为正常模式。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCRibbonBar 类](../../mfc/reference/cmfcribbonbar-class.md)<br/>
[CMFCRibbonBaseElement 类](../../mfc/reference/cmfcribbonbaseelement-class.md)<br/>
[CMFCRibbonBar 类](../../mfc/reference/cmfcribbonbar-class.md)
