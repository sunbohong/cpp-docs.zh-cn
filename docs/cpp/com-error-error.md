---
description: 了解详细信息： _com_error：： Error
title: _com_error::Error
ms.date: 11/04/2016
f1_keywords:
- _com_error::Error
- Error
helpviewer_keywords:
- Error method [C++]
ms.assetid: b53a15fd-198e-4276-afcd-13439c4807f7
ms.openlocfilehash: 25dd78caeada9e7606bc26f241126b0d0f510f4c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318190"
---
# <a name="_com_errorerror"></a>_com_error::Error

**Microsoft 专用**

检索传递给构造函数的 HRESULT。

## <a name="syntax"></a>语法

```
HRESULT Error( ) const throw( );
```

## <a name="return-value"></a>返回值

传入构造函数的原始 HRESULT 项。

## <a name="remarks"></a>备注

检索对象中封装的 HRESULT 项 `_com_error` 。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[_com_error 类](../cpp/com-error-class.md)
