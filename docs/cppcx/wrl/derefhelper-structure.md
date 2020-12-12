---
description: 了解详细信息： DerefHelper 结构
title: DerefHelper 结构
ms.date: 10/03/2018
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::Details::DerefHelper
helpviewer_keywords:
- DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
ms.openlocfilehash: 8605e3923d8d3099a080be22f9d8e70ee9187ef9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272911"
---
# <a name="derefhelper-structure"></a>DerefHelper 结构

支持 WRL 基础结构，不应在代码中直接使用。

## <a name="syntax"></a>语法

```cpp
template <typename T>
struct DerefHelper;

template <typename T>
struct DerefHelper<T*>;
```

### <a name="parameters"></a>parameters

*T*<br/>
模板参数。

## <a name="remarks"></a>备注

表示指向模板参数的取消引用的指针 `T*` 。

**DerefHelper** 用在表达式中，例如： `ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;` 。

## <a name="members"></a>成员

### <a name="public-typedefs"></a>公共 Typedef

|名称|描述|
|----------|-----------------|
|`DerefType`|取消引用的模板参数的标识符 `T*` 。|

## <a name="inheritance-hierarchy"></a>继承层次结构

`DerefHelper`

## <a name="requirements"></a>要求

**标头：** async。h

**命名空间：** Microsoft：： WRL：:D etails

## <a name="see-also"></a>请参阅

[Microsoft：： WRL：:D etails 命名空间](microsoft-wrl-details-namespace.md)
