---
description: 了解详细信息： sequenced_policy 类
title: sequenced_policy 类
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::sequenced_policy
ms.openlocfilehash: e4d19e3649e3c768e8efc062baaf735e28a8fc22
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250408"
---
# <a name="sequenced_policy-class"></a>sequenced_policy 类

用作消除并行算法重载的唯一类型，并要求并行算法的执行不会并行化。

## <a name="syntax"></a>语法

```cpp
class execution::sequenced_policy;
```

## <a name="remarks"></a>备注

在并行算法与策略的执行过程中 `execution::sequenced_policy` ，如果通过未捕获的异常退出元素访问函数，则 `terminate()` 应调用。
