---
description: 了解详细信息： Container Class：： swap
title: Container Class::swap
ms.date: 11/04/2016
helpviewer_keywords:
- swap method
ms.assetid: 898c219c-bc8e-4d14-a149-6240426c693f
ms.openlocfilehash: a38dd6d14ada3ad50927060ccec1542ebf2fd4ca
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97233352"
---
# <a name="container-classswap"></a>Container Class::swap

> [!NOTE]
> 本主题在 Microsoft c + + 文档中作为 c + + 标准库中使用的容器的非功能性示例。 有关详细信息，请参阅 [C++ 标准库容器](../standard-library/stl-containers.md)。

交换 **\* 此** 和其参数之间的受控序列。

## <a name="syntax"></a>语法

```cpp
void swap(Container& right);
```

## <a name="remarks"></a>备注

如果为，则为 **\* get \_ 分配器 = =** _right_**.get_allocator**，它将在固定时间进行交换。 否则，它所执行的元素分配和构造函数调用数量会与两个受控序列中的元素数量成正比。

## <a name="see-also"></a>请参阅

[示例容器类](../standard-library/sample-container-class.md)
