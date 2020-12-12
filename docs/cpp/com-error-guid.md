---
description: 了解详细信息： _com_error：： GUID
title: _com_error::GUID
ms.date: 11/04/2016
f1_keywords:
- _com_error::GUID
helpviewer_keywords:
- GUID method [C++]
ms.assetid: e84c2c23-d02e-48f8-b776-9bd6937296d2
ms.openlocfilehash: 32f88728d5c0f93094413aaeae8fb3c116b415c3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295960"
---
# <a name="_com_errorguid"></a>_com_error::GUID

**Microsoft 专用**

调用 `IErrorInfo::GetGUID` 函数。

## <a name="syntax"></a>语法

```
GUID GUID( ) const throw( );
```

## <a name="return-value"></a>返回值

返回 `IErrorInfo::GetGUID` `IErrorInfo` 对象中记录的对象的结果 `_com_error` 。 如果未 `IErrorInfo` 记录任何对象，则返回 `GUID_NULL` 。

## <a name="remarks"></a>备注

调用 `IErrorInfo::GetGUID` 方法时，将忽略任何错误。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_error 类](../cpp/com-error-class.md)
