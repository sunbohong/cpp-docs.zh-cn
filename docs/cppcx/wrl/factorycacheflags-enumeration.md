---
description: 了解详细信息： FactoryCacheFlags 枚举
title: FactoryCacheFlags 枚举
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::FactoryCacheFlags
ms.assetid: 6f54258f-0144-4264-9608-414e5905f6fb
ms.openlocfilehash: 68a86049bf1f6287a84ae4df2e27dbe3c63c91c5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97198500"
---
# <a name="factorycacheflags-enumeration"></a>FactoryCacheFlags 枚举

确定是否缓存工厂对象。

## <a name="syntax"></a>语法

```cpp
enum FactoryCacheFlags;
```

## <a name="remarks"></a>备注

默认情况下，创建[Module](module-class.md)对象时，出厂缓存策略指定为[ModuleType](moduletype-enumeration.md)模板参数。 若要重写此策略，请在创建工厂对象时指定 **FactoryCacheFlags** 值。

| 策略 | 描述 |
|-|-|
|`FactoryCacheDefault`|将使用 `Module` 对象的缓存策略。|
|`FactoryCacheEnabled`|启用工厂缓存，无论用于创建 `ModuleType` 对象的 `Module` 模板参数如何都是如此。|
|`FactoryCacheDisabled`|禁用工厂缓存，无论用于创建 `ModuleType` 对象的 `Module` 模板参数如何都是如此。|

## <a name="requirements"></a>要求

**标头：** 实现。h

**命名空间：** Microsoft::WRL

## <a name="see-also"></a>请参阅

[Microsoft：： WRL 命名空间](microsoft-wrl-namespace.md)
