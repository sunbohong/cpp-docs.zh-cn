---
description: 了解详细信息： COleLinkingDoc 类
title: COleLinkingDoc 类
ms.date: 11/04/2016
f1_keywords:
- COleLinkingDoc
- AFXOLE/COleLinkingDoc
- AFXOLE/COleLinkingDoc::COleLinkingDoc
- AFXOLE/COleLinkingDoc::Register
- AFXOLE/COleLinkingDoc::Revoke
- AFXOLE/COleLinkingDoc::OnFindEmbeddedItem
- AFXOLE/COleLinkingDoc::OnGetLinkedItem
helpviewer_keywords:
- COleLinkingDoc [MFC], COleLinkingDoc
- COleLinkingDoc [MFC], Register
- COleLinkingDoc [MFC], Revoke
- COleLinkingDoc [MFC], OnFindEmbeddedItem
- COleLinkingDoc [MFC], OnGetLinkedItem
ms.assetid: 9f547f35-2f95-427f-b9c0-85c31940198b
ms.openlocfilehash: 10cf9bb81c4cbbd324b95a13dc2fa44548266583
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226904"
---
# <a name="colelinkingdoc-class"></a>COleLinkingDoc 类

支持链接到所包含的嵌入项的 OLE 容器文档的基类。

## <a name="syntax"></a>语法

```
class COleLinkingDoc : public COleDocument
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[COleLinkingDoc::COleLinkingDoc](#colelinkingdoc)|构造 `COleLinkingDoc` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[COleLinkingDoc：： Register](#register)|向 OLE 系统 Dll 注册文档。|
|[COleLinkingDoc：： Revoke](#revoke)|撤消文档的注册。|

### <a name="protected-methods"></a>受保护的方法

|名称|描述|
|----------|-----------------|
|[COleLinkingDoc::OnFindEmbeddedItem](#onfindembeddeditem)|查找指定的嵌入项。|
|[COleLinkingDoc::OnGetLinkedItem](#ongetlinkeditem)|查找指定的链接项。|

## <a name="remarks"></a>备注

支持链接到嵌入项的容器应用程序称为 "链接容器"。 [OCLIENT](../../overview/visual-cpp-samples.md)示例应用程序是链接容器的示例。

如果链接项的源是另一个文档中的嵌入项，则必须加载包含文档的，才能编辑嵌入项。 出于此原因，当用户想要编辑链接项的源时，链接容器必须能够由另一个容器应用程序启动。 应用程序还必须使用 [COleTemplateServer](../../mfc/reference/coletemplateserver-class.md) 类，以便在以编程方式启动时可以创建文档。

若要使容器成为链接容器，请从派生文档类， `COleLinkingDoc` 而不是 [COleDocument](../../mfc/reference/coledocument-class.md)。 与任何其他 OLE 容器一样，必须设计用于存储应用程序的本机数据以及嵌入项或链接项的类。 此外，还必须设计用于存储本机数据的数据结构。 如果 `CDocItem` 为应用程序的本机数据定义派生类，则可以使用由定义的接口 `COleDocument` 来存储本机数据以及您的 OLE 数据。

若要允许另一个容器以编程方式启动应用程序，请将 `COleTemplateServer` 对象声明为应用程序的 `CWinApp` 派生类的成员：

[!code-cpp[NVC_MFCOleContainer#23](../../mfc/codesnippet/cpp/colelinkingdoc-class_1.h)]

在 `InitInstance` 派生类的成员函数中 `CWinApp` ，创建一个文档模板，并将 `COleLinkingDoc` 派生类指定为文档类：

[!code-cpp[NVC_MFCOleContainer#24](../../mfc/codesnippet/cpp/colelinkingdoc-class_2.cpp)]

`COleTemplateServer`通过调用对象的成员函数，将对象连接到文档模板 `ConnectTemplate` ，并通过调用将所有类对象注册到 OLE 系统 `COleTemplateServer::RegisterAll` ：

[!code-cpp[NVC_MFCOleContainer#25](../../mfc/codesnippet/cpp/colelinkingdoc-class_3.cpp)]

有关派生的 `CWinApp` 类定义和函数的示例 `InitInstance` ，请参阅 OCLIENT。H 和 OCLIENT。MFC 示例 [OCLIENT](../../overview/visual-cpp-samples.md)中的 CPP。

有关使用的详细信息 `COleLinkingDoc` ，请参阅文章 [容器：实现容器](../../mfc/containers-implementing-a-container.md) 和 [容器：高级功能](../../mfc/containers-advanced-features.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CDocument](../../mfc/reference/cdocument-class.md)

[COleDocument](../../mfc/reference/coledocument-class.md)

`COleLinkingDoc`

## <a name="requirements"></a>要求

**标头：** afxole

## <a name="colelinkingdoccolelinkingdoc"></a><a name="colelinkingdoc"></a> COleLinkingDoc::COleLinkingDoc

构造 `COleLinkingDoc` 对象，而不开始与 OLE 系统 dll 的通信。

```
COleLinkingDoc();
```

### <a name="remarks"></a>备注

必须调用 `Register` 成员函数来通知 OLE 文档已打开。

## <a name="colelinkingdoconfindembeddeditem"></a><a name="onfindembeddeditem"></a> COleLinkingDoc::OnFindEmbeddedItem

由框架调用以确定文档是否包含具有指定名称的嵌入 OLE 项。

```
virtual COleClientItem* OnFindEmbeddedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>parameters

*lpszItemName*<br/>
指向所请求的嵌入 OLE 项的名称的指针。

### <a name="return-value"></a>返回值

指向指定项的指针;如果找不到该项，则为 NULL。

### <a name="remarks"></a>备注

默认实现会搜索具有指定名称的项的嵌入项列表， (名称比较) 区分大小写。 如果你有自己的方法来存储或命名嵌入的 OLE 项，请重写此函数。

## <a name="colelinkingdocongetlinkeditem"></a><a name="ongetlinkeditem"></a> COleLinkingDoc::OnGetLinkedItem

由框架调用，用于检查文档是否包含具有指定名称的链接服务器项。

```
virtual COleServerItem* OnGetLinkedItem(LPCTSTR lpszItemName);
```

### <a name="parameters"></a>parameters

*lpszItemName*<br/>
指向所请求链接的 OLE 项的名称的指针。

### <a name="return-value"></a>返回值

指向指定项的指针;如果找不到该项，则为 NULL。

### <a name="remarks"></a>备注

默认 `COleLinkingDoc` 实现始终返回 NULL。 此函数在派生类中被 `COleServerDoc` 重写，以便在名称比较 (区分大小) 写的情况下搜索具有指定名称的链接项的 OLE 服务器项列表。 如果已实现自己的方法来存储或检索链接服务器项，请重写此函数。

## <a name="colelinkingdocregister"></a><a name="register"></a> COleLinkingDoc：： Register

通知 OLE 系统 Dll 文档已打开。

```
BOOL Register(
    COleObjectFactory* pFactory,
    LPCTSTR lpszPathName);
```

### <a name="parameters"></a>parameters

*pFactory*<br/>
指向 OLE factory 对象 (的指针可以为 NULL) 。

*lpszPathName*<br/>
一个指针，指向容器文档的完全限定路径。

### <a name="return-value"></a>返回值

如果成功注册了文档，则为非零值;否则为0。

### <a name="remarks"></a>备注

创建或打开命名文件以向 OLE 系统 Dll 注册文档时调用此函数。 如果文档表示嵌入项，则无需调用此函数。

如果 `COleTemplateServer` 在应用程序中使用， `Register` 则会通过 `COleLinkingDoc` 的、和实现来调用 `OnNewDocument` `OnOpenDocument` `OnSaveDocument` 。

## <a name="colelinkingdocrevoke"></a><a name="revoke"></a> COleLinkingDoc：： Revoke

通知 OLE 系统 Dll 文档不再处于打开状态。

```cpp
void Revoke();
```

### <a name="remarks"></a>备注

调用此函数可撤消文档在 OLE 系统 Dll 中的注册。

你应在关闭命名文件时调用此函数，但通常不需要直接调用它。 `Revoke` 由、、和的 `COleLinkingDoc` 实现来调用 `OnCloseDocument` `OnNewDocument` `OnOpenDocument` `OnSaveDocument` 。

## <a name="see-also"></a>请参阅

[MFC 示例 OCLIENT](../../overview/visual-cpp-samples.md)<br/>
[COleDocument 类](../../mfc/reference/coledocument-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CDocTemplate 类](../../mfc/reference/cdoctemplate-class.md)
