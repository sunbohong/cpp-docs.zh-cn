---
description: 了解详细信息： CancelTransitionPolicy 枚举
title: CancelTransitionPolicy 枚举
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::CancelTransitionPolicy::TransitionFromCanceled
- module/Microsoft::WRL::CancelTransitionPolicy::RemainCanceled
- module/Microsoft::WRL::CancelTransitionPolicy
helpviewer_keywords:
- CancelTransitionPolicy Enumeration
ms.assetid: 5de49f7d-e5e3-43e9-bbca-666caf226cef
ms.openlocfilehash: 8de995ed492f8f1260534b08b818b77d889d95fd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344531"
---
# <a name="canceltransitionpolicy-enumeration"></a>CancelTransitionPolicy 枚举

指示异步操作尝试转换为已完成或错误的终端状态的方式应与客户端请求的已取消状态的行为有关。

## <a name="syntax"></a>语法

```cpp
enum CancelTransitionPolicy;
```

## <a name="members"></a>成员

### <a name="values"></a>值

|“属性”|描述|
|----------|-----------------|
|`RemainCanceled`|如果异步操作当前处于客户端请求的已取消状态，这表示它将保持为 "已取消" 状态，而不是转换为 "已完成" 或 "错误" 状态。|
|`TransitionFromCanceled`|如果异步操作当前处于客户端请求的已取消状态，则指示状态应从该取消状态转换为已完成或错误的结束状态，这取决于利用此标志的调用。|

## <a name="requirements"></a>要求

**标头：** async。h

**命名空间：** Microsoft::WRL

## <a name="see-also"></a>请参阅

[Microsoft：： WRL 命名空间](microsoft-wrl-namespace.md)
