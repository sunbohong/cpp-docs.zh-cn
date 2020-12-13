---
description: 了解详细信息： CSimpleException 类
title: CSimpleException 类
ms.date: 11/04/2016
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
helpviewer_keywords:
- CSimpleException [MFC], CSimpleException
- CSimpleException [MFC], GetErrorMessage
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
ms.openlocfilehash: 8070604e05fa59f7fcdfef6dcaad12ab0497da9f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342813"
---
# <a name="csimpleexception-class"></a>CSimpleException 类

此类是资源重要的 MFC 异常的基类。

## <a name="syntax"></a>语法

```
class AFX_NOVTABLE CSimpleException : public CException
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CSimpleException::CSimpleException](#csimpleexception)|构造函数。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSimpleException::GetErrorMessage](#geterrormessage)|提供有关已发生的错误的文本。|

## <a name="remarks"></a>备注

`CSimpleException` 是资源关键的 MFC 异常的基类，并处理错误消息的所有权和初始化。 以下类用作 `CSimpleException` 其基类：

|名称|描述|
|-|-|
|[CMemoryException 类](../../mfc/reference/cmemoryexception-class.md)|内存不足异常|
|[CNotSupportedException 类](../../mfc/reference/cnotsupportedexception-class.md)|请求不受支持的操作|
|[CResourceException 类](../../mfc/reference/cresourceexception-class.md)|Windows 资源找不到或不可创建|
|[CUserException 类](../../mfc/reference/cuserexception-class.md)|指示找不到资源的异常|
|[CInvalidArgException 类](../../mfc/reference/cinvalidargexception-class.md)|指示无效参数的异常|

由于 `CSimpleException` 是抽象基类，因此不能 `CSimpleException` 直接声明对象。 相反，您必须声明派生对象，例如上表中的对象。 如果要声明自己的派生类，请使用以前的类作为模型。

有关详细信息，请参阅 [CException 类](../../mfc/reference/cexception-class.md) 主题和 [异常处理 (MFC) ](../../mfc/exception-handling-in-mfc.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CSimpleException`

## <a name="requirements"></a>要求

**标头：** afx

## <a name="csimpleexceptioncsimpleexception"></a><a name="csimpleexception"></a> CSimpleException::CSimpleException

构造函数。

```
CSimpleException();
explicit CSimpleException(BOOL bAutoDelete);
```

### <a name="parameters"></a>parameters

*bAutoDelete*<br/>
如果 `CSimpleException` 已在堆上分配了对象的内存，则指定 TRUE。 这将导致在 `CSimpleException` `Delete` 调用成员函数删除异常时删除该对象。 如果 `CSimpleException` 对象位于堆栈上或是全局对象，则指定 FALSE。 在这种情况下， `CSimpleException` `Delete` 调用成员函数时不会删除对象。

### <a name="remarks"></a>备注

通常不需要直接调用此构造函数。 引发异常的函数应创建 `CException` 派生类的实例并调用其构造函数，或者应使用其中一种 MFC 引发函数（如 [AfxThrowFileException](exception-processing.md#afxthrowfileexception)）来引发预定义类型。

## <a name="csimpleexceptiongeterrormessage"></a><a name="geterrormessage"></a> CSimpleException::GetErrorMessage

调用此成员函数以提供有关已发生的错误的文本。

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```

### <a name="parameters"></a>parameters

*lpszError*<br/>
指向将接收错误消息的缓冲区的指针。

*nMaxError*<br/>
缓冲区可以容纳的最大字符数，包括 NULL 终止符。

*pnHelpContext*<br/>
将接收帮助上下文 ID 的 UINT 的地址。 如果为 NULL，则将不返回任何 ID。

### <a name="return-value"></a>返回值

如果函数成功，则为非零值;如果没有可用的错误消息文本，则为 0; 否则为0。

### <a name="remarks"></a>备注

有关详细信息，请参阅 [CException：： GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage)。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CException 类](../../mfc/reference/cexception-class.md)<br/>
[异常处理](../../mfc/exception-handling-in-mfc.md)
