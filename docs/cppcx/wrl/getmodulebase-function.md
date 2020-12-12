---
description: 了解详细信息： GetModuleBase 函数
title: GetModuleBase 函数
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
ms.openlocfilehash: cdedaf905da194400209840b6bd84fa8e626eb0a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97295193"
---
# <a name="getmodulebase-function"></a>GetModuleBase 函数

检索一个 [ModuleBase](modulebase-class.md) 指针，该指针允许递增和递减 [RuntimeClass](runtimeclass-class.md) 对象的引用计数。

## <a name="syntax"></a>语法

```cpp
inline Details::ModuleBase* GetModuleBase() throw()
```

## <a name="return-value"></a>返回值

一个指向 `ModuleBase` 对象的指针。

## <a name="remarks"></a>备注

此函数在内部用于递增和递减对象引用计数。

可以使用此函数通过调用 [ModuleBase：： IncrementObjectCount](modulebase-class.md#incrementobjectcount) 和 [ModuleBase：:D ecrementobjectcount](modulebase-class.md#decrementobjectcount)来控制引用计数。

## <a name="requirements"></a>要求

**标头：** 实现。h

**命名空间：** Microsoft::WRL

## <a name="see-also"></a>请参阅

[Microsoft：： WRL 命名空间](microsoft-wrl-namespace.md)
