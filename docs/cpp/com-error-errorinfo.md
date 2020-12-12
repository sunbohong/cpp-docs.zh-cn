---
description: 了解详细信息： _com_error：： ErrorInfo
title: _com_error::ErrorInfo
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorInfo
helpviewer_keywords:
- ErrorInfo method [C++]
ms.assetid: 071b446c-4395-4fb8-bd3d-300a8b25f5cd
ms.openlocfilehash: 36092ae9287352d421bf502ad24c054cf3b7a907
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97296038"
---
# <a name="_com_errorerrorinfo"></a>_com_error::ErrorInfo

**Microsoft 专用**

检索 `IErrorInfo` 传递给构造函数的对象。

## <a name="syntax"></a>语法

```
IErrorInfo * ErrorInfo( ) const throw( );
```

## <a name="return-value"></a>返回值

已传入构造函数的原始 `IErrorInfo` 项。

## <a name="remarks"></a>备注

检索 `IErrorInfo` 对象中的封装项 `_com_error` ，如果不记录任何项，则为 NULL `IErrorInfo` 。 使用完后，调用方必须对 `Release` 返回的对象调用。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_error 类](../cpp/com-error-class.md)
