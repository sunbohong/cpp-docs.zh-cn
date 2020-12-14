---
description: 了解详细信息： RaiseException 函数
title: RaiseException 函数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::RaiseException
helpviewer_keywords:
- RaiseException function
ms.assetid: f9c74f6d-112a-4d2e-900f-622f795d5dbf
ms.openlocfilehash: b5353757ff04ab12c0fc61da6b2e98b2df835ef0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198435"
---
# <a name="raiseexception-function"></a>RaiseException 函数

支持 WRL 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
inline void __declspec(noreturn)   RaiseException(
      HRESULT hr,
      DWORD dwExceptionFlags = EXCEPTION_NONCONTINUABLE);
```

### <a name="parameters"></a>parameters

*小时*<br/>
引发的异常的异常代码;也就是说，失败操作的 HRESULT。

*dwExceptionFlags*<br/>
指示 (标志值为零) 或不可继续操作异常 (标志值为非零) 的持续性异常的标志。 默认情况下，异常为不可继续操作。

## <a name="remarks"></a>备注

引发调用线程中的异常。

有关详细信息，请参阅 Windows `RaiseException` 函数。

## <a name="requirements"></a>要求

**标头：** internal。h

**命名空间：** Microsoft：： WRL：:D etails

## <a name="see-also"></a>请参阅

[Microsoft：： WRL：:D etails 命名空间](microsoft-wrl-details-namespace.md)
