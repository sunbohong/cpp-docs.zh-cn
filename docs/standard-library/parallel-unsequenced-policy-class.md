---
description: 了解详细信息： parallel_unsequenced_policy 类
title: parallel_unsequenced_policy 类
ms.date: 04/18/2019
f1_keywords:
- execution/std::execution::parallel_unsequenced_policy
ms.openlocfilehash: e39edc0979bf1374bc6092dbadb032811180f668
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340783"
---
# <a name="parallel_unsequenced_policy-class"></a>parallel_unsequenced_policy 类

用作消除并行算法重载的唯一类型，并指示并行算法的执行可能会并行化并向量化。

## <a name="syntax"></a>语法

```cpp
class execution::parallel_unsequenced_policy;
```

## <a name="remarks"></a>备注

在并行算法与策略的执行过程中 `execution::parallel_unsequenced_policy` ，如果通过未捕获的异常退出元素访问函数，则 `terminate()` 应调用。
