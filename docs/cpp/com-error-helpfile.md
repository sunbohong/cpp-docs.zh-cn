---
description: 了解详细信息： _com_error：：帮助
title: _com_error::HelpFile
ms.date: 11/04/2016
f1_keywords:
- _com_error::HelpFile
helpviewer_keywords:
- HelpFile method [C++]
ms.assetid: d2d3a0a1-6b62-4d52-a818-3cfae545a4af
ms.openlocfilehash: e45785913a8a5a1909f702bce672727171e0baef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295921"
---
# <a name="_com_errorhelpfile"></a>_com_error::HelpFile

**Microsoft 专用**

调用 `IErrorInfo::GetHelpFile` 函数。

## <a name="syntax"></a>语法

```
_bstr_t HelpFile() const;
```

## <a name="return-value"></a>返回值

返回 `IErrorInfo::GetHelpFile` `IErrorInfo` 对象中记录的对象的结果 `_com_error` 。 生成的 BSTR 封装在 `_bstr_t` 对象中。 如果未 `IErrorInfo` 记录，则返回空 `_bstr_t` 。

## <a name="remarks"></a>备注

调用 `IErrorInfo::GetHelpFile` 方法时，将忽略任何错误。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_error 类](../cpp/com-error-class.md)
