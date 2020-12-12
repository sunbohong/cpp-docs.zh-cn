---
description: 了解详细信息： _com_error：： Source
title: _com_error::Source
ms.date: 11/04/2016
f1_keywords:
- _com_error::Source
helpviewer_keywords:
- Source method [C++]
ms.assetid: 55353741-fabc-4b0c-9787-b5a69bb189f2
ms.openlocfilehash: 3b6cf35420454e8285d3d8b4deee3df8fe8771e4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295765"
---
# <a name="_com_errorsource"></a>_com_error::Source

**Microsoft 专用**

调用 `IErrorInfo::GetSource` 函数。

## <a name="syntax"></a>语法

```
_bstr_t Source() const;
```

## <a name="return-value"></a>返回值

返回 `IErrorInfo::GetSource` `IErrorInfo` 对象中记录的对象的结果 `_com_error` 。 生成的 `BSTR` 封装在 `_bstr_t` 对象中。 如果未 `IErrorInfo` 记录，则返回空 `_bstr_t` 。

## <a name="remarks"></a>备注

调用 `IErrorInfo::GetSource` 方法时，将忽略任何错误。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_error 类](../cpp/com-error-class.md)
