---
description: 了解详细信息： CMultiPageDHtmlDialog 类
title: CMultiPageDHtmlDialog 类
ms.date: 03/27/2019
f1_keywords:
- CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog
- AFXDHTML/CMultiPageDHtmlDialog::CMultiPageDHtmlDialog
helpviewer_keywords:
- CMultiPageDHtmlDialog [MFC], CMultiPageDHtmlDialog
ms.assetid: 971accc1-824d-4df4-b4c1-b1a20e0f7e4f
ms.openlocfilehash: 1f7f8c2081687c71a98e427bb5396cfa47a73deb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331527"
---
# <a name="cmultipagedhtmldialog-class"></a>CMultiPageDHtmlDialog 类

多页对话框按顺序显示多个 HTML 页并处理每页中的事件。

## <a name="syntax"></a>语法

```
class CMultiPageDHtmlDialog : public CDHtmlDialog
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMultiPageDHtmlDialog：： CMultiPageDHtmlDialog](#cmultipagedhtmldialog)|) DHTML 对话框对象构造多页 (向导样式。|
|[CMultiPageDHtmlDialog：： ~ CMultiPageDHtmlDialog](#_dtorcmultipagedhtmldialog)|销毁多页 DHTML 对话框对象。|

## <a name="remarks"></a>备注

用于执行此操作的机制为 [DHTML 和 URL 事件映射](dhtml-event-maps.md)，其中包含每个页面的嵌入事件映射。

## <a name="example"></a>示例

此多页对话框假设有三个定义类似于向导的简单功能的 HTML 资源。 第一页包含 "**下一步** **" 按钮、** 第二个 **按钮和第** 三 **个按钮。** 按下某个按钮时，处理程序函数会调用 [CDHtmlDialog：： LoadFromResource](../../mfc/reference/cdhtmldialog-class.md#loadfromresource) 以加载适当的新页。

类声明的相关部分 (在 CMyMultiPageDlg 中) ：

[!code-cpp[NVC_MFCDocView#181](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_1.h)]

类实现 (在 CMyMultipageDlg) 中的相关部分：

[!code-cpp[NVC_MFCDocView#182](../../mfc/codesnippet/cpp/cmultipagedhtmldialog-class_2.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CDHtmlSinkHandlerBase2`

`CDHtmlSinkHandlerBase1`

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

`CDHtmlSinkHandler`

[CWnd](../../mfc/reference/cwnd-class.md)

`CDHtmlEventSink`

[CDialog](../../mfc/reference/cdialog-class.md)

[CDHtmlDialog](../../mfc/reference/cdhtmldialog-class.md)

`CMultiPageDHtmlDialog`

## <a name="requirements"></a>要求

**标头：** afxdhtml

## <a name="cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="cmultipagedhtmldialog"></a> CMultiPageDHtmlDialog：： CMultiPageDHtmlDialog

) DHTML 对话框对象构造多页 (向导样式。

```
CMultiPageDHtmlDialog(
    LPCTSTR lpszTemplateName,
    LPCTSTR szHtmlResID = NULL,
    CWnd* pParentWnd = NULL);

CMultiPageDHtmlDialog(
    UINT nIDTemplate,
    UINT nHtmlResID = 0,
    CWnd* pParentWnd = NULL);

CMultiPageDHtmlDialog();
```

### <a name="parameters"></a>parameters

*lpszTemplateName*<br/>
以 null 结尾的字符串，它是对话框模板资源的名称。

*szHtmlResID*<br/>
以 null 结尾的字符串，它是 HTML 资源的名称。

*pParentWnd*<br/>
一个指针，指向该对话框对象所属的) 类型为 [CWnd](../../mfc/reference/cwnd-class.md) 的父或所有者窗口对象 (。 如果为 NULL，则对话框对象的父窗口将设置为主应用程序窗口。

*nIDTemplate*<br/>
包含对话框模板资源的 ID 号。

*nHtmlResID*<br/>
包含 HTML 资源的 ID 号。

## <a name="cmultipagedhtmldialogcmultipagedhtmldialog"></a><a name="_dtorcmultipagedhtmldialog"></a> CMultiPageDHtmlDialog：： ~ CMultiPageDHtmlDialog

销毁多页 DHTML 对话框对象。

```
virtual ~CMultiPageDHtmlDialog();
```

## <a name="see-also"></a>请参阅

[CDHtmlDialog 类](../../mfc/reference/cdhtmldialog-class.md)
