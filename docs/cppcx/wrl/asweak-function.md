---
description: 了解详细信息： AsWeak 函数
title: AsWeak 函数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
ms.openlocfilehash: a02776f06aab4d7505b38fbb1120c36a82e97368
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175841"
---
# <a name="asweak-function"></a>AsWeak 函数

检索对指定实例的弱引用。

## <a name="syntax"></a>语法

```cpp
template<typename T>
HRESULT AsWeak(
   _In_ T* p,
   _Out_ WeakRef* pWeak
);
```

### <a name="parameters"></a>parameters

*T*<br/>
指向参数 *p* 的类型的指针。

*h-p*<br/>
类型的实例。

*pWeak*<br/>
此操作完成后，指向参数 *p* 的弱引用的指针。

## <a name="return-value"></a>返回值

S_OK，如果此操作成功，则为;否则，会出现指示失败原因的错误 HRESULT。

## <a name="requirements"></a>要求

**标头：** client.h

**命名空间：** Microsoft::WRL

## <a name="see-also"></a>请参阅

[Microsoft：： WRL 命名空间](microsoft-wrl-namespace.md)
