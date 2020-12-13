---
description: 了解详细信息： SimpleActivationFactory 类
title: SimpleActivationFactory 类
ms.date: 09/07/2018
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
- module/Microsoft::WRL::SimpleActivationFactory::ActivateInstance
- module/Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
helpviewer_keywords:
- Microsoft::WRL::SimpleActivationFactory class
- Microsoft::WRL::SimpleActivationFactory::ActivateInstance method
- Microsoft::WRL::SimpleActivationFactory::GetRuntimeClassName method
- Microsoft::WRL::SimpleActivationFactory::GetTrustLevel method
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
ms.openlocfilehash: 83643c69977b887e58e430bbd500fcf7c2e81ca6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97135208"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory 类

提供创建 Windows 运行时或经典 COM 基类的基础机制。

## <a name="syntax"></a>语法

```cpp
template<typename Base>
class SimpleActivationFactory : public ActivationFactory<>;
```

### <a name="parameters"></a>parameters

*基座*<br/>
基类。

## <a name="remarks"></a>备注

基类必须提供默认构造函数。

下面的代码示例演示如何将 SimpleActivationFactory 与 [ActivatableClassWithFactoryEx](activatableclass-macros.md) 宏一起使用。

`ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[SimpleActivationFactory::ActivateInstance 方法](#activateinstance)|创建指定接口的实例。|
|[SimpleActivationFactory::GetRuntimeClassName 方法](#getruntimeclassname)|获取由 *基类* 模板参数指定的类的实例的运行时类名称。|
|[SimpleActivationFactory::GetTrustLevel 方法](#gettrustlevel)|获取由 *基类* 模板参数指定的类的实例的信任级别。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`I0`

`ChainInterfaces`

`I0`

`RuntimeClassBase`

`ImplementsHelper`

`DontUseNewUseMake`

`RuntimeClassFlags`

`RuntimeClassBaseT`

`RuntimeClass`

`ActivationFactory`

`SimpleActivationFactory`

## <a name="requirements"></a>要求

**标头：** 模块。h

**命名空间：** Microsoft::WRL

## <a name="simpleactivationfactoryactivateinstance-method"></a><a name="activateinstance"></a> SimpleActivationFactory：： ActivateInstance 方法

创建指定接口的实例。

```cpp
STDMETHOD( ActivateInstance )(
    _Deref_out_ IInspectable **ppvObject
);
```

#### <a name="parameters"></a>parameters

*ppvObject*<br/>
此操作完成后，指向由类模板参数指定的对象的实例的指针 `Base` 。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为指示错误的 HRESULT。

### <a name="remarks"></a>备注

如果 `__WRL_STRICT__` 定义了，则在类模板参数中指定的基类不是从 [RuntimeClass](runtimeclass-class.md)派生的或未使用 WinRt 或 WinRtClassicComMix [RuntimeClassType](runtimeclasstype-enumeration.md) 枚举值配置的情况下，将发出断言错误。

## <a name="simpleactivationfactorygetruntimeclassname-method"></a><a name="getruntimeclassname"></a> SimpleActivationFactory：： GetRuntimeClassName 方法

获取类模板参数指定的类的实例的运行时类名称 `Base` 。

```cpp
STDMETHOD( GetRuntimeClassName )(
    _Out_ HSTRING* runtimeName
);
```

#### <a name="parameters"></a>parameters

*runtimeName*<br/>
此操作完成后，运行时类名称。

### <a name="return-value"></a>返回值

如果成功，则为 S_OK；否则为指示错误的 HRESULT。

### <a name="remarks"></a>备注

如果 `__WRL_STRICT__` 定义了，则在 `Base` 类模板参数指定的类不是从 [RuntimeClass](runtimeclass-class.md)派生的情况下发出断言错误，也不会使用 WinRt 或 WinRtClassicComMix [RuntimeClassType](runtimeclasstype-enumeration.md) 枚举值进行配置。

## <a name="simpleactivationfactorygettrustlevel-method"></a><a name="gettrustlevel"></a> SimpleActivationFactory：： GetTrustLevel 方法

获取由类模板参数指定的类的实例的信任级别 `Base` 。

```cpp
STDMETHOD(
   GetTrustLevel
)(_Out_ TrustLevel* trustLvl);
```

#### <a name="parameters"></a>parameters

*trustLvl*<br/>
此操作完成后，当前类对象的信任级别。

### <a name="return-value"></a>返回值

始终 S_OK。
