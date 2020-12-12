---
description: 了解详细信息： CMFCLinkCtrl 类
title: CMFCLinkCtrl 类
ms.date: 11/04/2016
f1_keywords:
- CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl
- AFXLINKCTRL/CMFCLinkCtrl::SetURL
- AFXLINKCTRL/CMFCLinkCtrl::SetURLPrefix
- AFXLINKCTRL/CMFCLinkCtrl::SizeToContent
- AFXLINKCTRL/CMFCLinkCtrl::OnDrawFocusRect
helpviewer_keywords:
- CMFCLinkCtrl [MFC], SetURL
- CMFCLinkCtrl [MFC], SetURLPrefix
- CMFCLinkCtrl [MFC], SizeToContent
- CMFCLinkCtrl [MFC], OnDrawFocusRect
ms.assetid: 80f3874d-7cc8-410e-9ff1-62a225f5034b
ms.openlocfilehash: 6951f086ac99c4b8a8260a79ee08d54476694350
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265215"
---
# <a name="cmfclinkctrl-class"></a>CMFCLinkCtrl 类

`CMFCLinkCtrl`类在单击按钮时，将按钮显示为超链接并调用链接的目标。

## <a name="syntax"></a>语法

```
class CMFCLinkCtrl : public CMFCButton
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCLinkCtrl：： SetURL](#seturl)|显示指定的 URL 作为按钮文本。|
|[CMFCLinkCtrl::SetURLPrefix](#seturlprefix)|设置隐式协议 (例如，URL 的 "http：" ) 。|
|[CMFCLinkCtrl：： System.windows.window.sizetocontent](#sizetocontent)|调整按钮的大小以包含按钮文本或位图。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[CMFCLinkCtrl::OnDrawFocusRect](#ondrawfocusrect)|在绘制按钮的聚焦框之前由框架调用。|

## <a name="remarks"></a>备注

单击从类派生的按钮时 `CMFCLinkCtrl` ，框架会将该按钮的 URL 作为参数传递给 `ShellExecute` 方法。 然后， `ShellExecute` 方法会打开 URL 的目标。

## <a name="example"></a>示例

下面的示例演示如何设置对象的大小 `CMFCLinkCtrl` ，以及如何在对象中设置 url 和工具提示 `CMFCLinkCtrl` 。 此示例是 [新控件示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_NewControls#9](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_1.h)]
[!code-cpp[NVC_MFC_NewControls#10](../../mfc/reference/codesnippet/cpp/cmfclinkctrl-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CButton](../../mfc/reference/cbutton-class.md)

[CMFCButton](../../mfc/reference/cmfcbutton-class.md)

[CMFCLinkCtrl](../../mfc/reference/cmfclinkctrl-class.md)

## <a name="requirements"></a>要求

**标头：** afxlinkctrl

## <a name="cmfclinkctrlondrawfocusrect"></a><a name="ondrawfocusrect"></a> CMFCLinkCtrl::OnDrawFocusRect

在绘制按钮的聚焦框之前由框架调用。

```
virtual void OnDrawFocusRect(
    CDC* pDC,
    const CRect& rectClient);
```

### <a name="parameters"></a>parameters

*pDC*<br/>
中指向设备上下文的指针。

*rectClient*<br/>
中限定链接控件的矩形。

### <a name="remarks"></a>备注

如果要使用自己的代码绘制按钮的聚焦框，请重写此方法。

## <a name="cmfclinkctrlseturl"></a><a name="seturl"></a> CMFCLinkCtrl：： SetURL

显示指定的 URL 作为按钮文本。

```cpp
void SetURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>parameters

*lpszURL*<br/>
中要显示的按钮文本。

### <a name="remarks"></a>备注

## <a name="cmfclinkctrlseturlprefix"></a><a name="seturlprefix"></a> CMFCLinkCtrl::SetURLPrefix

设置隐式协议 (例如，URL 的 "http：" ) 。

```cpp
void SetURLPrefix(LPCTSTR lpszPrefix);
```

### <a name="parameters"></a>parameters

*lpszPrefix*<br/>
中URL 协议的前缀。

### <a name="remarks"></a>备注

使用此方法可设置 URL 前缀。 该前缀不显示在按钮的图符上，但你可以使用它来帮助浏览到 URL 的目标。

## <a name="cmfclinkctrlsizetocontent"></a><a name="sizetocontent"></a> CMFCLinkCtrl：： System.windows.window.sizetocontent

调整按钮的大小以包含按钮文本或位图。

```
virtual CSize SizeToContent(
    BOOL bVCenter=FALSE,
    BOOL bHCenter=FALSE);
```

### <a name="parameters"></a>parameters

*bVCenter*<br/>
中如果为 TRUE，则在链接控件的顶部和底部之间垂直居中放置按钮文本和位图;否则为 FALSE。 默认值是 FALSE。

*bHCenter*<br/>
中如果为 TRUE，则在链接控件的左侧和右侧之间水平居中放置按钮文本和位图;否则为 FALSE。 默认值是 FALSE。

### <a name="return-value"></a>返回值

一个 [CSize](../../atl-mfc-shared/reference/csize-class.md) 对象，它包含链接控件的新大小。

### <a name="remarks"></a>备注

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CLinkCtrl 类](../../mfc/reference/clinkctrl-class.md)<br/>
[CMFCButton 类](../../mfc/reference/cmfcbutton-class.md)
