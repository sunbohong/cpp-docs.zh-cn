---
description: 了解详细信息： CUserException 类
title: CUserException 类
ms.date: 11/04/2016
f1_keywords:
- CUserException
helpviewer_keywords:
- operations [MFC], stopping
- exceptions [MFC], throwing
- CUserException class [MFC]
- errors [MFC], trapping
- operations [MFC]
- throwing exceptions [MFC], stopping user operations
ms.assetid: 2156ba6d-2cce-415a-9000-6f02c26fcd7d
ms.openlocfilehash: 6104aa2883a80f88aed03634f09ad1947e9c6794
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344960"
---
# <a name="cuserexception-class"></a>CUserException 类

引发后将终止最终用户操作。

## <a name="syntax"></a>语法

```
class CUserException : public CSimpleException
```

## <a name="remarks"></a>备注

`CUserException`若要对应用程序特定的异常使用引发/捕获异常机制，请使用。 类名称中的 "用户" 可以解释为 "我的用户对我的用户进行了一些需要处理的异常。"

`CUserException`通常在调用 global 函数后引发， `AfxMessageBox` 以通知用户操作已失败。 编写异常处理程序时，请专门处理异常，因为用户通常已经收到失败的通知。 在某些情况下，框架会引发此异常。 若要 `CUserException` 自行引发，请向用户发出警报，然后调用 global 函数 `AfxThrowUserException` 。

在下面的示例中，包含可能失败的操作的函数会向用户发出警报，并引发 `CUserException` 。 调用函数将捕获异常并对其进行特殊处理：

[!code-cpp[NVC_MFCExceptions#24](../../mfc/codesnippet/cpp/cuserexception-class_1.cpp)]

有关使用的详细信息 `CUserException` ，请参阅文章 [ (MFC) 的异常处理 ](../../mfc/exception-handling-in-mfc.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

[CSimpleException](../../mfc/reference/csimpleexception-class.md)

`CUserException`

## <a name="requirements"></a>要求

**标头:** afxwin.h

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CException 类](../../mfc/reference/cexception-class.md)
