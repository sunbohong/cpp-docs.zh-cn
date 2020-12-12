---
description: 了解详细信息： CResourceException 类
title: CResourceException 类
ms.date: 11/04/2016
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
helpviewer_keywords:
- CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
ms.openlocfilehash: c76635ae2cfa6c55bf54da7e73f6afbb44506fee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264864"
---
# <a name="cresourceexception-class"></a>CResourceException 类

当 Windows 无法找到或分配请求的资源时生成。

## <a name="syntax"></a>语法

```
class CResourceException : public CSimpleException
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CResourceException::CResourceException](#cresourceexception)|构造 `CResourceException` 对象。|

## <a name="remarks"></a>备注

无需进行进一步的限制。

有关使用的详细信息 `CResourceException` ，请参阅文章 [ (MFC) 的异常处理 ](../../mfc/exception-handling-in-mfc.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CResourceException`

## <a name="requirements"></a>要求

**标头:** afxwin.h

## <a name="cresourceexceptioncresourceexception"></a><a name="cresourceexception"></a> CResourceException::CResourceException

构造 `CResourceException` 对象。

```
CResourceException();
```

### <a name="remarks"></a>备注

不要直接使用此构造函数，而应调用 global 函数 [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception)。 有关异常的详细信息，请参阅文章 [MFC 中的异常处理](../exception-handling-in-mfc.md)。

## <a name="see-also"></a>请参阅

[CException 类](cexception-class.md)<br/>
[层次结构图](../hierarchy-chart.md)
