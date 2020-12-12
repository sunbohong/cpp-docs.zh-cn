---
description: 了解详细信息： _com_error：： ErrorMessage
title: _com_error::ErrorMessage
ms.date: 11/04/2016
f1_keywords:
- _com_error::ErrorMessage
helpviewer_keywords:
- ErrorMessage method [C++]
ms.assetid: e47335b6-01af-4975-a841-121597479eb7
ms.openlocfilehash: e7f91882d55e629744df5f26f7dcc64df1dddb22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295999"
---
# <a name="_com_errorerrormessage"></a>_com_error::ErrorMessage

**Microsoft 专用**

检索对象中存储的 HRESULT 的字符串消息 `_com_error` 。

## <a name="syntax"></a>语法

```
const TCHAR * ErrorMessage( ) const throw( );
```

## <a name="return-value"></a>返回值

返回在对象中记录的 HRESULT 的字符串消息 `_com_error` 。 如果 HRESULT 是映射的16位 [wCode](../cpp/com-error-wcode.md)，则返回一般消息 " `IDispatch error #<wCode>` "。 如果未找到消息，则返回一般消息“`Unknown error #<hresult>`”。 返回的字符串是 Unicode 或多字节字符串，具体取决于 _UNICODE 宏的状态。

## <a name="remarks"></a>备注

检索在对象中记录的 HRESULT 的适当系统消息文本 `_com_error` 。 系统消息文本是通过调用 Win32 [FormatMessage](/windows/win32/api/winbase/nf-winbase-formatmessage) 函数获取的。 返回的字符串由 `FormatMessage` API 分配，并在销毁 `_com_error` 对象后释放。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_error 类](../cpp/com-error-class.md)
