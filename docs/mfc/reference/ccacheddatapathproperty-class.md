---
description: 了解详细信息： CCachedDataPathProperty 类
title: CCachedDataPathProperty 类
ms.date: 11/04/2016
f1_keywords:
- CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::CCachedDataPathProperty
- AFXCTL/CCachedDataPathProperty::m_Cache
helpviewer_keywords:
- CCachedDataPathProperty [MFC], CCachedDataPathProperty
- CCachedDataPathProperty [MFC], m_Cache
ms.assetid: 0d81356b-4fe5-43f6-aed2-2eb5a5485706
ms.openlocfilehash: a61d2553afc4415da29399293843deb1be5f113d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122494"
---
# <a name="ccacheddatapathproperty-class"></a>CCachedDataPathProperty 类

实现异步传输并在内存文件中缓冲的 OLE 控件属性。

## <a name="syntax"></a>语法

```
class CCachedDataPathProperty : public CDataPathProperty
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CCachedDataPathProperty：： CCachedDataPathProperty](#ccacheddatapathproperty)|构造 `CCachedDataPathProperty` 对象。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CCachedDataPathProperty：： m_Cache](#m_cache)|`CMemFile` 要在其中缓存数据的对象。|

## <a name="remarks"></a>备注

内存文件存储在 RAM 中，而不是存储在磁盘上，适用于快速临时传输。

除了 `CAysncMonikerFile` 和之外 `CDataPathProperty` ， `CCachedDataPathProperty` 还提供了在 OLE 控件中使用异步名字对象的功能。 使用 `CCachedDataPathProperty` 对象，可以从 URL 或文件源异步传输数据，并通过公共变量将数据存储在内存文件中 `m_Cache` 。 所有数据都存储在内存文件中，除非你想要监视通知并做出响应，否则不需要替代 [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable) 。 例如，如果传输的是大型。GIF 文件，并且想要通知控件已到达的数据过多，并且应重绘其自身，请重写 `OnDataAvailable` 以发出通知。

类 `CCachedDataPathProperty` 派生自 `CDataPathProperty` 。

有关如何在 Internet 应用程序中使用异步名字对象和 ActiveX 控件的详细信息，请参阅以下主题：

- [Internet 优先步骤： ActiveX 控件](../../mfc/activex-controls-on-the-internet.md)

- [Internet 优先步骤：异步名字对象](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

[CDataPathProperty](../../mfc/reference/cdatapathproperty-class.md)

`CCachedDataPathProperty`

## <a name="requirements"></a>要求

**标头：** afxctl。h

## <a name="ccacheddatapathpropertyccacheddatapathproperty"></a><a name="ccacheddatapathproperty"></a> CCachedDataPathProperty：： CCachedDataPathProperty

构造 `CCachedDataPathProperty` 对象。

```
CCachedDataPathProperty(COleControl* pControl = NULL);

CCachedDataPathProperty(
    LPCTSTR lpszPath,
    COleControl* pControl = NULL);
```

### <a name="parameters"></a>parameters

*pControl*<br/>
指向要与此对象关联的 ActiveX 控件对象的指针 `CCachedDataPathProperty` 。

*lpszPath*<br/>
路径（可以是绝对的或相对的）用于创建引用属性的实际绝对位置的异步名字对象。 `CCachedDataPathProperty` 使用 Url，而不是文件名。 如果需要文件的 `CCachedDataPathProperty` 对象，请在路径前面添加 file://。

### <a name="remarks"></a>备注

由 `COleControl` *pControl* 指向的对象由派生类的 [开放](../../mfc/reference/cdatapathproperty-class.md#open) 和检索使用。 如果 *pControl* 为 NULL，则用于的控件 `Open` 应使用 [SetControl](../../mfc/reference/cdatapathproperty-class.md#setcontrol)进行设置。 如果 *lpszPath* 为 NULL，则可以通过传递路径， `Open` 也可以使用 [SetPath](../../mfc/reference/cdatapathproperty-class.md#setpath)进行设置。

## <a name="ccacheddatapathpropertym_cache"></a><a name="m_cache"></a> CCachedDataPathProperty：： m_Cache

包含缓存数据的内存文件的类名。

```
CMemFile m_Cache;
```

### <a name="remarks"></a>备注

内存文件存储在 RAM 中，而不是存储在磁盘上。

## <a name="see-also"></a>请参阅

[CDataPathProperty 类](../../mfc/reference/cdatapathproperty-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CDataPathProperty 类](../../mfc/reference/cdatapathproperty-class.md)
