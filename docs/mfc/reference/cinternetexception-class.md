---
description: 了解详细信息： CInternetException 类
title: CInternetException 类
ms.date: 11/04/2016
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
helpviewer_keywords:
- CInternetException [MFC], CInternetException
- CInternetException [MFC], m_dwContext
- CInternetException [MFC], m_dwError
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
ms.openlocfilehash: d46c2eca7f7f568b0296d6ced567d33b49ba4cb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209940"
---
# <a name="cinternetexception-class"></a>CInternetException 类

表示与 Internet 操作相关的异常条件。

## <a name="syntax"></a>语法

```
class CInternetException : public CException
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CInternetException：： CInternetException](#cinternetexception)|构造 `CInternetException` 对象。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CInternetException：： m_dwContext](#m_dwcontext)|与引起异常的操作相关联的上下文值。|
|[CInternetException：： m_dwError](#m_dwerror)|导致异常的错误。|

## <a name="remarks"></a>备注

`CInternetException`类包含两个公共数据成员：一个包含与异常关联的错误代码，另一个包含与错误关联的 Internet 应用程序的上下文标识符。

有关 Internet 应用程序的上下文标识符的详细信息，请参阅文章 [带有 WinInet 的 Internet 编程](../../mfc/win32-internet-extensions-wininet.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CInternetException`

## <a name="requirements"></a>要求

**标头：** afxinet。h

## <a name="cinternetexceptioncinternetexception"></a><a name="cinternetexception"></a> CInternetException：： CInternetException

当创建对象时，将调用此成员函数 `CInternetException` 。

```
CInternetException(DWORD dwError);
```

### <a name="parameters"></a>parameters

*dwError*<br/>
导致异常的错误。

### <a name="remarks"></a>备注

若要引发 CInternetException，请调用 MFC global 函数 [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception)。

## <a name="cinternetexceptionm_dwcontext"></a><a name="m_dwcontext"></a> CInternetException：： m_dwContext

与相关的 Internet 操作关联的上下文值。

```
DWORD_PTR m_dwContext;
```

### <a name="remarks"></a>备注

上下文标识符最初在 [CInternetSession](../../mfc/reference/cinternetsession-class.md) 中指定，由 MFC 传递到 [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)和 [CInternetFile](../../mfc/reference/cinternetfile-class.md)派生类。 可以重写此默认值，并将任何 *dwContext* 参数指定为你选择的值。 *dwContext* 与给定对象的任何操作相关联。 *dwContext* 标识由 [CInternetSession：： OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback)返回的操作的状态信息。

## <a name="cinternetexceptionm_dwerror"></a><a name="m_dwerror"></a> CInternetException：： m_dwError

导致异常的错误。

```
DWORD m_dwError;
```

### <a name="remarks"></a>备注

此错误值可能是系统错误代码，在 WINERROR.H 中找到。H，或来自 WININET 的错误值。

有关 Win32 错误代码的列表，请参阅 [错误代码](/windows/win32/Debug/system-error-codes)。 有关 Internet 特定错误消息的列表，请参阅。 这两个主题在 Windows SDK 中。

## <a name="see-also"></a>请参阅

[CException 类](../../mfc/reference/cexception-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CException 类](../../mfc/reference/cexception-class.md)
