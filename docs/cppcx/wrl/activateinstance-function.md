---
description: 了解详细信息： ActivateInstance 函数
title: ActivateInstance 函数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
ms.openlocfilehash: 03d7b67810ee2ab287072546b098f81f43687233
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287848"
---
# <a name="activateinstance-function"></a>ActivateInstance 函数

注册并检索在指定类 ID 中定义的指定类型的实例。

## <a name="syntax"></a>语法

```cpp
template<typename T>
inline HRESULT ActivateInstance(
   _In_ HSTRING activatableClassId,
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance
);
```

### <a name="parameters"></a>parameters

*T*<br/>
要激活的类型。

*activatableClassId*<br/>
定义参数 *T* 的类 ID 的名称。

*实例*<br/>
此操作完成时，对 *T* 的实例的引用。

## <a name="return-value"></a>返回值

如果成功，则为 S_OK;否则，会出现指示错误原因的错误 HRESULT。

## <a name="requirements"></a>要求

**标头：** client.h

**命名空间：** Windows：： Foundation

## <a name="see-also"></a>请参阅

[Windows：： Foundation 命名空间](windows-foundation-namespace.md)
