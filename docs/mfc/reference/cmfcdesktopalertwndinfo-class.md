---
description: 了解详细信息： CMFCDesktopAlertWndInfo 类
title: CMFCDesktopAlertWndInfo 类
ms.date: 10/18/2018
f1_keywords:
- CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_hIcon
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_nURLCmdID
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strText
- AFXDESKTOPALERTDIALOG/CMFCDesktopAlertWndInfo::m_strURL
helpviewer_keywords:
- CMFCDesktopAlertWndInfo [MFC], m_hIcon
- CMFCDesktopAlertWndInfo [MFC], m_nURLCmdID
- CMFCDesktopAlertWndInfo [MFC], m_strText
- CMFCDesktopAlertWndInfo [MFC], m_strURL
ms.assetid: 5c9bb84e-6c96-4748-8e74-6951b6ae8e84
ms.openlocfilehash: 1c23e5b890e892df9bccce51542f2d36b3d6f7d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250681"
---
# <a name="cmfcdesktopalertwndinfo-class"></a>CMFCDesktopAlertWndInfo 类

`CMFCDesktopAlertWndInfo`类与[CMFCDesktopAlertWnd 类](../../mfc/reference/cmfcdesktopalertwnd-class.md)一起使用。 它指定在桌面警报窗口弹出时显示的控件。

## <a name="syntax"></a>语法

```
class CMFCDesktopAlertWndInfo
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|`CMFCDesktopAlertWndInfo::~CMFCDesktopAlertWndInfo`|析构函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo：： operator =](#operator_eq)||

### <a name="data-members"></a>数据成员

|名称|描述|
|----------|-----------------|
|[CMFCDesktopAlertWndInfo：： m_hIcon](#m_hicon)|显示的图标的句柄。|
|[CMFCDesktopAlertWndInfo：： m_nURLCmdID](#m_nurlcmdid)|与桌面警报窗口上的链接关联的命令 ID。|
|[CMFCDesktopAlertWndInfo：： m_strText](#m_strtext)|桌面上显示的文本。|
|[CMFCDesktopAlertWndInfo：： m_strURL](#m_strurl)|显示在 "桌面警报" 窗口中的链接。|

## <a name="remarks"></a>备注

`CMFCDesktopAlertWndInfo`类将传递给[CMFCDesktopAlertWnd：： Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)方法，以指定在桌面警报窗口的默认对话框上显示的元素。 默认对话框可以包含三个项：

- 一个图标，通过调用 [CMFCDesktopAlertWndInfo：： m_hIcon](#m_hicon)设置。

- 通过调用 [CMFCDesktopAlertWndInfo：： m_strText](#m_strtext)设置的标签或短信。

- 通过调用 [CMFCDesktopAlertWndInfo：： m_strURL](#m_strurl)来设置的链接。 若要设置在单击链接时执行的命令，请调用 [CMFCDesktopAlertWndInfo：： m_nURLCmdID](#m_nurlcmdid)。

如果默认对话框不足，则可以创建一个自定义对话框，并将其传递给 [CMFCDesktopAlertWnd：： create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create) 方法，而不是使用此类。 有关详细信息，请参阅 [CMFCDesktopAlertDialog 类](../../mfc/reference/cmfcdesktopalertdialog-class.md)。

## <a name="example"></a>示例

下面的示例演示如何使用类中的各种成员 `CMFCDesktopAlertWndInfo` 。 该示例演示了如何将句柄设置为显示的图标、桌面警报窗口上显示的文本、桌面警报窗口上显示的链接以及与桌面警报窗口上的链接关联的命令 ID。 此示例是 [桌面警报演示示例](../../overview/visual-cpp-samples.md)的一部分。

[!code-cpp[NVC_MFC_DesktopAlertDemo#3](../../mfc/reference/codesnippet/cpp/cmfcdesktopalertwndinfo-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CMFCDesktopAlertWndInfo](../../mfc/reference/cmfcdesktopalertwndinfo-class.md)

## <a name="requirements"></a>要求

**标头：** afxDesktopAlertDialog

## <a name="cmfcdesktopalertwndinfooperator"></a><a name="operator_eq"></a> CMFCDesktopAlertWndInfo：： operator =

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
CMFCDesktopAlertWndInfo& operator=(CMFCDesktopAlertWndInfo& src);
```

### <a name="parameters"></a>parameters

中 *src*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcdesktopalertwndinfom_hicon"></a><a name="m_hicon"></a> CMFCDesktopAlertWndInfo：： m_hIcon

显示的图标的句柄。

```
HICON m_hIcon;
```

### <a name="remarks"></a>备注

## <a name="cmfcdesktopalertwndinfom_nurlcmdid"></a><a name="m_nurlcmdid"></a> CMFCDesktopAlertWndInfo：： m_nURLCmdID

与桌面警报窗口上的链接关联的命令 ID。

```
UINT m_nURLCmdID;
```

### <a name="remarks"></a>备注

当用户单击 [CMFCDesktopAlertWndInfo：： m_strURL](#m_strurl)指定的链接时，命令 ID 将发送到弹出窗口的所有者。

## <a name="cmfcdesktopalertwndinfom_strtext"></a><a name="m_strtext"></a> CMFCDesktopAlertWndInfo：： m_strText

桌面上显示的文本。

```
CString m_strText;
```

### <a name="remarks"></a>备注

## <a name="cmfcdesktopalertwndinfom_strurl"></a><a name="m_strurl"></a> CMFCDesktopAlertWndInfo：： m_strURL

显示在 "桌面警报" 窗口中的链接。

```
CString m_strURL;
```

### <a name="remarks"></a>备注

当用户单击该链接时，具有 [CMFCDesktopAlertWndInfo：： m_nURLCmdID](#m_nurlcmdid) 命令 ID 的命令将发送到弹出窗口的所有者。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCDesktopAlertWnd 类](../../mfc/reference/cmfcdesktopalertwnd-class.md)<br/>
[CMFCDesktopAlertWnd：： Create](../../mfc/reference/cmfcdesktopalertwnd-class.md#create)<br/>
[CMFCDesktopAlertDialog 类](../../mfc/reference/cmfcdesktopalertdialog-class.md)
