---
description: 了解详细信息： CHtmlEditDoc 类
title: CHtmlEditDoc 类
ms.date: 11/04/2016
f1_keywords:
- CHtmlEditDoc
- AFXHTML/CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::CHtmlEditDoc
- AFXHTML/CHtmlEditDoc::GetView
- AFXHTML/CHtmlEditDoc::IsModified
- AFXHTML/CHtmlEditDoc::OpenURL
helpviewer_keywords:
- CHtmlEditDoc [MFC], CHtmlEditDoc
- CHtmlEditDoc [MFC], GetView
- CHtmlEditDoc [MFC], IsModified
- CHtmlEditDoc [MFC], OpenURL
ms.assetid: b2cca61f-e5d6-4099-b0d1-46bf85f0bd64
ms.openlocfilehash: 5fb8187ff7925efc5bdfa6a0079a8ec4b186ae63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97115308"
---
# <a name="chtmleditdoc-class"></a>CHtmlEditDoc 类

借助 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)，可以在 MFC 文档视图体系结构的上下文中提供 WebBrowser 编辑平台的功能。

## <a name="syntax"></a>语法

```
class AFX_NOVTABLE CHtmlEditDoc : public CDocument
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CHtmlEditDoc::CHtmlEditDoc](#chtmleditdoc)|构造 `CHtmlEditDoc` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CHtmlEditDoc：： GetView](#getview)|检索 `CHtmlEditView` 附加到此文档的对象。|
|[CHtmlEditDoc::IsModified](#ismodified)|返回关联视图的 WebBrowser 控件是否包含用户已修改的文档。|
|[CHtmlEditDoc：： OpenURL](#openurl)|打开 URL。|

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

`CHtmlEditDoc`

## <a name="requirements"></a>要求

**标头：** afxhtml.h

## <a name="chtmleditdocchtmleditdoc"></a><a name="chtmleditdoc"></a> CHtmlEditDoc::CHtmlEditDoc

构造 `CHtmlEditDoc` 对象。

```
CHtmlEditDoc();
```

## <a name="chtmleditdocgetview"></a><a name="getview"></a> CHtmlEditDoc：： GetView

检索附加到此文档的 [CHtmlEditView](../../mfc/reference/chtmleditview-class.md) 对象。

```
virtual CHtmlEditView* GetView() const;
```

### <a name="return-value"></a>返回值

返回指向文档的对象的指针 `CHtmlEditView` 。

## <a name="chtmleditdocismodified"></a><a name="ismodified"></a> CHtmlEditDoc::IsModified

返回关联视图的 WebBrowser 控件是否包含用户已修改的文档。

```
virtual BOOL IsModified();
```

## <a name="chtmleditdocopenurl"></a><a name="openurl"></a> CHtmlEditDoc：： OpenURL

打开 URL。

```
virtual BOOL OpenURL(LPCTSTR lpszURL);
```

### <a name="parameters"></a>parameters

*lpszURL*<br/>
要打开的 URL。

### <a name="return-value"></a>返回值

如果成功，则返回 TRUE，否则返回 FALSE。

## <a name="see-also"></a>请参阅

[HTMLEdit 示例](../../overview/visual-cpp-samples.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)
