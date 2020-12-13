---
description: '了解详细信息： _com_error：:D e) '
title: _com_error::Description
ms.date: 11/04/2016
f1_keywords:
- _com_error::Description
helpviewer_keywords:
- Description method [C++]
ms.assetid: 88191e24-4ee8-44a6-8c4c-3758e22e0548
ms.openlocfilehash: 6404d16361abe81d9e234a6b63039a7476d91ef1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332557"
---
# <a name="_com_errordescription"></a>_com_error::Description

**Microsoft 专用**

调用 `IErrorInfo::GetDescription` 函数。

## <a name="syntax"></a>语法

```
_bstr_t Description( ) const;
```

## <a name="return-value"></a>返回值

返回 `IErrorInfo::GetDescription` `IErrorInfo` 对象中记录的对象的结果 `_com_error` 。 生成的 `BSTR` 封装在 `_bstr_t` 对象中。 如果未 `IErrorInfo` 记录，则返回空 `_bstr_t` 。

## <a name="remarks"></a>备注

调用 `IErrorInfo::GetDescription` 函数并检索 `IErrorInfo` 在对象中记录的 `_com_error` 。 调用 `IErrorInfo::GetDescription` 方法时，将忽略任何错误。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_error 类](../cpp/com-error-class.md)
