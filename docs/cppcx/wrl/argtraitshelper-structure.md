---
description: 了解详细信息： ArgTraitsHelper 结构
title: ArgTraitsHelper 结构
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
- event/Microsoft::WRL::Details::ArgTraitsHelper::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraitsHelper structure
- Microsoft::WRL::Details::ArgTraitsHelper::args constant
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
ms.openlocfilehash: a749c48c72c837eb0898d32ddd08410b87918871
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97175854"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper 结构

支持 WRL 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
template<typename TDelegateInterface>
struct ArgTraitsHelper;
```

### <a name="parameters"></a>parameters

*TDelegateInterface*<br/>
委托接口。

## <a name="remarks"></a>备注

有助于定义委托参数的常见特性。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

名称         | 描述
------------ | ------------------------------------------------------
`methodType` | `decltype(&TDelegateInterface::Invoke)` 的同义词。
`Traits`     | `ArgTraits<methodType>` 的同义词。

### <a name="public-constants"></a>公共常量

名称                           | 描述
------------------------------ | ---------------------------------------------------------------------------------------------------------------------
[ArgTraitsHelper：： args](#args) | 帮助 [ArgTraits：： args](#args) 保持委托接口的方法的参数数目 `Invoke` 。

## <a name="inheritance-hierarchy"></a>继承层次结构

`ArgTraitsHelper`

## <a name="requirements"></a>要求

**标头：** 事件。h

**命名空间：** Microsoft：： WRL：:D etails

## <a name="argtraitshelperargs"></a><a name="args"></a> ArgTraitsHelper：： args

支持 WRL 基础结构，不应在代码中直接使用。

```cpp
static const int args = Traits::args;
```

### <a name="remarks"></a>备注

有助于 `ArgTraitsHelper::args` 保持委托接口的方法的参数数量 `Invoke` 。
