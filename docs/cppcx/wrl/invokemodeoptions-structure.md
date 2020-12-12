---
description: 了解详细信息： InvokeModeOptions 结构
title: InvokeModeOptions 结构
ms.date: 03/22/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::InvokeModeOptions
helpviewer_keywords:
- InvokeModeOptions structure
- InvokeMode enum
ms.openlocfilehash: 1e1382242c95c47355239c220c43c278280dd451
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97298976"
---
# <a name="invokemodeoptions-structure"></a>InvokeModeOptions 结构

指定是激发委托队列中的所有事件，还是在引发错误后停止激发。 允许的值在枚举中指定 `InvokeMode` 。

## <a name="syntax"></a>语法

```cpp
enum InvokeMode
{
   StopOnFirstError = 1,
   FireAll = 2,
};

struct InvokeModeOptions
{
   static const InvokeMode invokeMode = invokeModeValue;
};
```

## <a name="requirements"></a>要求

**标头：** 事件。h

**命名空间：** Microsoft::WRL

## <a name="see-also"></a>请参阅

[Microsoft：： WRL 命名空间](microsoft-wrl-namespace.md)<br/>
[Microsoft：： WRL：： AgileEventSource 类](agileeventsource-class.md)
