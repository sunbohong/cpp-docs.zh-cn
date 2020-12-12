---
description: 了解详细信息： Microsoft：： WRL：：包装命名空间
title: Microsoft::WRL::Wrappers 命名空间
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers
helpviewer_keywords:
- Wrappers namespace
ms.assetid: 36ac38c7-1fc3-42da-a879-5c68661dc9e1
ms.openlocfilehash: 603fa14b0e43f481b1afe56d98e355d328f284fe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209394"
---
# <a name="microsoftwrlwrappers-namespace"></a>Microsoft::WRL::Wrappers 命名空间

定义简化对象、字符串和句柄的生存期管理的“获取资源即初始化”(RAII) 包装器类型。

## <a name="syntax"></a>语法

```cpp
namespace Microsoft::WRL::Wrappers;
```

## <a name="members"></a>成员

### <a name="typedefs"></a>Typedef

|名称|描述|
|----------|-----------------|
|`FileHandle`|`HandleT<HandleTraits::FileHandleTraits>`|

### <a name="classes"></a>类

|“属性”|描述|
|----------|-----------------|
|[CriticalSection 类](criticalsection-class.md)|表示关键部分对象。|
|[事件类 (WRL) ](event-class-wrl.md)|表示一个事件。|
|[HandleT 类](handlet-class.md)|表示对象的句柄。|
|[HString 类](hstring-class.md)|提供对操作 HSTRING 句柄的支持。|
|[HStringReference 类](hstringreference-class.md)|表示从现有字符串创建的 HSTRING。|
|[Mutex 类](mutex-class.md)|表示完全控制共享资源的同步对象。|
|[RoInitializeWrapper 类](roinitializewrapper-class.md)|初始化 Windows 运行时。|
|[信号灯类](semaphore-class.md)|表示控制可支持有限数量用户的共享资源的同步对象。|
|[SRWLock 类](srwlock-class.md)|表示精简读取器/编写器锁定。|

## <a name="requirements"></a>要求

**标头：** corewrappers。h

**命名空间：** Microsoft：： WRL：：包装

## <a name="see-also"></a>请参阅

[Microsoft：： WRL 命名空间](microsoft-wrl-namespace.md)
