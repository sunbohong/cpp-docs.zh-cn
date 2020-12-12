---
description: 了解详细信息： _com_error：： HelpContext
title: _com_error::HelpContext
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpContext
helpviewer_keywords:
- HelpContext method [C++]
ms.assetid: 160d6443-9b68-4cf5-a540-50da951a5b2b
ms.openlocfilehash: 757fb572d9e41486af419712eb7f70cd7cfa7b14
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295934"
---
# <a name="_com_errorhelpcontext"></a>_com_error::HelpContext

**Microsoft 专用**

调用 `IErrorInfo::GetHelpContext` 函数。

## <a name="syntax"></a>语法

```
DWORD HelpContext( ) const throw( );
```

## <a name="return-value"></a>返回值

返回 `IErrorInfo::GetHelpContext` `IErrorInfo` 对象中记录的对象的结果 `_com_error` 。 如果未 `IErrorInfo` 记录任何对象，则返回零。

## <a name="remarks"></a>备注

调用 `IErrorInfo::GetHelpContext` 方法时，将忽略任何错误。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_error 类](../cpp/com-error-class.md)
