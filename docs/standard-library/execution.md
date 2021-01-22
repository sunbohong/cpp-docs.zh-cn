---
description: 了解详细信息： &lt; 执行&gt;
title: '&lt;操作&gt;'
ms.date: 01/15/2021
f1_keywords:
- <execution>
- execution/std::execution
- std::execution
helpviewer_keywords:
- execution header
ms.openlocfilehash: 2ffba3ad8620092676588c2a67e36cf8956413ba
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98667488"
---
# `<execution>`

介绍并行算法的执行策略。

## <a name="syntax"></a>语法

```cpp
namespace std {
    template<class T> inline constexpr bool is_execution_policy_v = is_execution_policy<T>::value;
}
namespace std::execution {
    inline constexpr sequenced_policy seq { unspecified };
    inline constexpr parallel_policy par { unspecified };
    inline constexpr parallel_unsequenced_policy par_unseq { unspecified };
}
```

### <a name="classes-and-structs"></a>类和结构

|名称|说明|
|-|-|
|[`is_execution_policy` 结构](is-execution-policy-struct.md)|检测执行策略，以排除某些函数签名（其他不明确的重载决策参与）。|
|[`parallel_policy` 班级](parallel-policy-class.md)|用作消除并行算法重载的唯一类型。 指示并行算法的执行可能会并行化。|
|[`parallel_unsequenced_policy` 班级](parallel-unsequenced-policy-class.md)|用作消除并行算法重载的唯一类型。 指示并行算法的执行可能会并行化并向量化。|
|[`sequenced_policy` 班级](sequenced-policy-class.md)|用作消除并行算法重载的唯一类型。 指定并行算法的执行不能并行化。|

## <a name="requirements"></a>要求

**标头：**\<execution>

**命名空间：** stdext

## <a name="see-also"></a>另请参阅

[标头文件引用](cpp-standard-library-header-files.md)\
[C + + 标准库中的线程安全](thread-safety-in-the-cpp-standard-library.md)\
[C++ 标准库参考](cpp-standard-library-reference.md)
