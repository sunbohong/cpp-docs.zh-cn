---
description: 了解详细信息： CDataPathProperty 类
title: CDataPathProperty 类
ms.date: 11/04/2016
f1_keywords:
- CDataPathProperty
- AFXCTL/CDataPathProperty
- AFXCTL/CDataPathProperty::CDataPathProperty
- AFXCTL/CDataPathProperty::GetControl
- AFXCTL/CDataPathProperty::GetPath
- AFXCTL/CDataPathProperty::Open
- AFXCTL/CDataPathProperty::ResetData
- AFXCTL/CDataPathProperty::SetControl
- AFXCTL/CDataPathProperty::SetPath
helpviewer_keywords:
- CDataPathProperty [MFC], CDataPathProperty
- CDataPathProperty [MFC], GetControl
- CDataPathProperty [MFC], GetPath
- CDataPathProperty [MFC], Open
- CDataPathProperty [MFC], ResetData
- CDataPathProperty [MFC], SetControl
- CDataPathProperty [MFC], SetPath
ms.assetid: 1f96efdb-54e4-460b-862c-eba5d4103488
ms.openlocfilehash: 7d9ff9f380fd44d5261374879bab63c9925c4442
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247951"
---
# <a name="cdatapathproperty-class"></a>CDataPathProperty 类

实现可异步加载的 OLE 控件属性。

## <a name="syntax"></a>语法

```
class CDataPathProperty : public CAsyncMonikerFile
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CDataPathProperty：： CDataPathProperty](#cdatapathproperty)|构造 `CDataPathProperty` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CDataPathProperty：： GetControl](#getcontrol)|检索与对象关联的异步 OLE 控件 `CDataPathProperty` 。|
|[CDataPathProperty：： GetPath](#getpath)|检索属性的路径名。|
|[CDataPathProperty：： Open](#open)|开始加载关联 ActiveX (OLE) 控件的异步属性。|
|[CDataPathProperty：： ResetData](#resetdata)|调用 `CAsyncMonikerFile::OnDataAvailable` 以通知容器控件属性已更改。|
|[CDataPathProperty：： SetControl](#setcontrol)|设置与属性关联的异步 ActiveX (OLE) 控件。|
|[CDataPathProperty：： SetPath](#setpath)|设置属性的路径名。|

## <a name="remarks"></a>备注

可以在同步启动之后加载异步属性。

类 `CDataPathProperty` 派生自 `CAysncMonikerFile` 。 若要在 OLE 控件中实现异步属性，请从派生一个类， `CDataPathProperty` 然后重写 [OnDataAvailable](../../mfc/reference/casyncmonikerfile-class.md#ondataavailable)。

有关如何在 Internet 应用程序中使用异步名字对象和 ActiveX 控件的详细信息，请参阅以下文章：

- [Internet 优先步骤： ActiveX 控件](../../mfc/activex-controls-on-the-internet.md)

- [Internet 优先步骤：异步名字对象](../../mfc/asynchronous-monikers-on-the-internet.md)

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CFile](../../mfc/reference/cfile-class.md)

[COleStreamFile](../../mfc/reference/colestreamfile-class.md)

[CMonikerFile](../../mfc/reference/cmonikerfile-class.md)

[CAsyncMonikerFile](../../mfc/reference/casyncmonikerfile-class.md)

`CDataPathProperty`

## <a name="requirements"></a>要求

**标头：** afxctl。h

## <a name="cdatapathpropertycdatapathproperty"></a><a name="cdatapathproperty"></a> CDataPathProperty：： CDataPathProperty

构造 `CDataPathProperty` 对象。

```
CDataPathProperty(COleControl* pControl = NULL);
CDataPathProperty(LPCTSTR lpszPath, COleControl* pControl = NULL);
```

### <a name="parameters"></a>parameters

*pControl*<br/>
一个指针，指向要与此对象关联的 OLE 控件对象 `CDataPathProperty` 。

*lpszPath*<br/>
路径（可以是绝对的或相对的）用于创建引用属性的实际绝对位置的异步名字对象。 `CDataPathProperty` 使用 Url，而不是文件名。 如果需要文件的 `CDataPathProperty` 对象，请在路径前面添加 `file://` 。

### <a name="remarks"></a>备注

由 `COleControl` *pControl* 指向的对象由用于 `Open` 派生类的和检索。 如果 *pControl* 为 NULL，则用于的控件 `Open` 应使用设置 `SetControl` 。 如果 *lpszPath* 为 NULL，则可以通过传递路径， `Open` 也可以使用对其进行设置 `SetPath` 。

## <a name="cdatapathpropertygetcontrol"></a><a name="getcontrol"></a> CDataPathProperty：： GetControl

调用此成员函数以检索 `COleControl` 与对象关联的对象 `CDataPathProperty` 。

```
COleControl* GetControl();
```

### <a name="return-value"></a>返回值

返回一个指针，该指针指向与对象关联的 OLE 控件 `CDataPathProperty` 。 如果未关联控件，则为 NULL。

## <a name="cdatapathpropertygetpath"></a><a name="getpath"></a> CDataPathProperty：： GetPath

调用此成员函数以检索路径，在 `CDataPathProperty` 构造对象时设置，或在中指定对象时设置 `Open` ，或者在以前对成员函数的调用中指定 `SetPath` 。

```
CString GetPath() const;
```

### <a name="return-value"></a>返回值

返回属性本身的路径名。 如果未指定路径，则可以为空。

## <a name="cdatapathpropertyopen"></a><a name="open"></a> CDataPathProperty：： Open

调用此成员函数以启动加载关联控件的异步属性。

```
virtual BOOL Open(
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    COleControl* pControl,
    CFileException* pError = NULL);

virtual BOOL Open(
    LPCTSTR lpszPath,
    CFileException* pError = NULL);

virtual BOOL Open(CFileException* pError = NULL);
```

### <a name="parameters"></a>parameters

*pControl*<br/>
一个指针，指向要与此对象关联的 OLE 控件对象 `CDataPathProperty` 。

*pError*<br/>
指向文件异常的指针。 出现错误时，将设置为原因。

*lpszPath*<br/>
路径（可以是绝对的或相对的）用于创建引用属性的实际绝对位置的异步名字对象。 `CDataPathProperty` 使用 Url，而不是文件名。 如果需要文件的 `CDataPathProperty` 对象，请在路径前面添加 `file://` 。

### <a name="return-value"></a>返回值

如果成功，则不为 0；否则为 0。

### <a name="remarks"></a>备注

函数尝试 `IBindHost` 从控件获取接口。

在 `Open` 不使用路径调用之前，必须设置该属性的路径的值。 这可以在构造对象时或通过调用 `SetPath` 成员函数时完成。

在 `Open` 不使用控件调用之前，ActiveX 控件 (以前称为 OLE 控件) 可以与对象相关联。 这可以在构造对象时或通过调用来完成 `SetControl` 。

还提供了 [CAsyncMonikerFile：： Open](../../mfc/reference/casyncmonikerfile-class.md#open) 的所有重载 `CDataPathProperty` 。

## <a name="cdatapathpropertyresetdata"></a><a name="resetdata"></a> CDataPathProperty：： ResetData

调用此函数以 `CAsyncMonikerFile::OnDataAvailable` 通知容器控件属性已更改，并且异步加载的所有信息将不再有用。

```
virtual void ResetData();
```

### <a name="remarks"></a>备注

应重新启动打开。 对于不同默认值，派生类可以重写此函数。

## <a name="cdatapathpropertysetcontrol"></a><a name="setcontrol"></a> CDataPathProperty：： SetControl

调用此成员函数可将异步 OLE 控件与对象相关联 `CDataPathProperty` 。

```cpp
void SetControl(COleControl* pControl);
```

### <a name="parameters"></a>parameters

*pControl*<br/>
一个指针，指向要与属性关联的异步 OLE 控件。

## <a name="cdatapathpropertysetpath"></a><a name="setpath"></a> CDataPathProperty：： SetPath

调用此成员函数以设置属性的路径名。

```cpp
void SetPath(LPCTSTR lpszPath);
```

### <a name="parameters"></a>parameters

*lpszPath*<br/>
路径（可以是绝对的或相对的）到异步加载的属性。 `CDataPathProperty` 使用 Url，而不是文件名。 如果需要文件的 `CDataPathProperty` 对象，请在路径前面添加 `file://` 。

## <a name="see-also"></a>请参阅

[MFC 示例图像](../../overview/visual-cpp-samples.md)<br/>
[CAsyncMonikerFile 类](../../mfc/reference/casyncmonikerfile-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CAsyncMonikerFile 类](../../mfc/reference/casyncmonikerfile-class.md)
