---
description: 了解详细信息： RuntimeClassFlags 结构
title: RuntimeClassFlags 结构
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
- implements/Microsoft::WRL::RuntimeClassFlags::value
helpviewer_keywords:
- Microsoft::WRL::RuntimeClassFlags structure
- Microsoft::WRL::RuntimeClassFlags::value constant
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
ms.openlocfilehash: 7874447fbbbe429884c5a79d0c70bb93e617ec61
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209264"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags 结构

包含 [RuntimeClass](runtimeclass-class.md)的实例的类型。

## <a name="syntax"></a>语法

```cpp
template <unsigned int flags>
struct RuntimeClassFlags;
```

### <a name="parameters"></a>参数

*flag*<br/>
[RuntimeClassType 枚举](runtimeclasstype-enumeration.md)值。

## <a name="members"></a>成员

### <a name="public-constants"></a>公共常量

|名称|描述|
|----------|-----------------|
|[RuntimeClassFlags::value 常量](#value-constant)|包含 [RuntimeClassType 枚举](runtimeclasstype-enumeration.md) 值。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`RuntimeClassFlags`

## <a name="requirements"></a>要求

**标头：** 实现。h

**命名空间：** Microsoft::WRL

## <a name="runtimeclassflagsvalue-constant"></a><a name="value-constant"></a> RuntimeClassFlags：： value 常量

包含 [RuntimeClassType 枚举](runtimeclasstype-enumeration.md) 值的字段。

```cpp
static const unsigned int value = flags;
```
