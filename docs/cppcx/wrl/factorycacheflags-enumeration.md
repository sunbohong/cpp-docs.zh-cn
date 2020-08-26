---
title: FactoryCacheFlags 枚举
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 3381b2bcfcbf298270b547199ae614291855a2f7
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88843269"
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags 枚举

确定是否缓存工厂对象。

## <a name="syntax"></a>语法

```cpp
enum FactoryCacheFlags;
```

## <a name="remarks"></a>备注

默认情况下，创建[Module](module-class.md)对象时，出厂缓存策略指定为[ModuleType](moduletype-enumeration.md)模板参数。 若要重写此策略，请在创建工厂对象时指定 **FactoryCacheFlags** 值。

| 策略 | 说明 |
|-|-|
|`FactoryCacheDefault`|将使用 `Module` 对象的缓存策略。|
|`FactoryCacheEnabled`|启用工厂缓存，无论用于创建 `ModuleType` 对象的 `Module` 模板参数如何都是如此。|
|`FactoryCacheDisabled`|禁用工厂缓存，无论用于创建 `ModuleType` 对象的 `Module` 模板参数如何都是如此。|

## <a name="requirements"></a>要求

**标头：** 实现。h

**命名空间：** Microsoft::WRL

## <a name="see-also"></a>另请参阅

[Microsoft：： WRL 命名空间](microsoft-wrl-namespace.md)
