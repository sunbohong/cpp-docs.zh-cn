---
description: 了解详细信息： CreateActivationFactory 函数
title: CreateActivationFactory 函数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::CreateActivationFactory
helpviewer_keywords:
- CreateActivationFactory function
ms.assetid: a1a53e04-6757-4faf-a4c8-ecf06e43b959
ms.openlocfilehash: 25f2181a00bb018361b05ea6570ebbadc6f7a975
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97273099"
---
# <a name="createactivationfactory-function"></a>CreateActivationFactory 函数

创建为可由 Windows 运行时激活的指定类生成实例的工厂。

## <a name="syntax"></a>语法

```cpp
template<typename Factory>
   inline HRESULT STDMETHODCALLTYPE CreateActivationFactory(
      _In_ unsigned int *flags,        _In_ const CreatorMap* entry,
      REFIID riid,
   _Outptr_ IUnknown **ppFactory) throw();
```

### <a name="parameters"></a>参数

*flag*<br/>
一个或多个 [RuntimeClassType](runtimeclasstype-enumeration.md) 枚举值的组合。

*条目*<br/>
指向包含参数 *riid* 的初始化和注册信息的 [CreatorMap](creatormap-structure.md)的指针。

*riid*<br/>
对接口 ID 的引用。

*ppFactory*<br/>
如果此操作成功完成，则为指向激活工厂的指针。

## <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为指示错误的 HRESULT。

## <a name="remarks"></a>备注

如果模板参数 *工厂* 不是从接口派生的，将发出断言错误 `IActivationFactory` 。

## <a name="requirements"></a>要求

**标头：** 模块。h

**命名空间：** Microsoft::WRL

## <a name="see-also"></a>请参阅

[Microsoft：： WRL：：包装：:D etails 命名空间](microsoft-wrl-wrappers-details-namespace.md)
