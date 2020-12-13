---
description: '了解详细信息： operator = = (&lt; 示例容器 &gt;) '
title: operator== (&lt;sample container&gt;)
ms.date: 11/04/2016
f1_keywords:
- std.==
- std::==
- operator==
- std.operator==
- std::operator==
- ==
helpviewer_keywords:
- operator ==, containers
- operator==, containers
- == operator, with specific standard C++ objects
ms.assetid: d3d8754e-5157-4b8b-bf9c-da41856f5eed
ms.openlocfilehash: b2fb296feb76536c28dd45e631af8071efa16939
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337979"
---
# <a name="operator-ltsample-containergt"></a>operator== (&lt;sample container&gt;)

> [!NOTE]
> 本主题在 Microsoft c + + 文档中作为 c + + 标准库中使用的容器的非功能性示例。 有关详细信息，请参阅 [C++ 标准库容器](../standard-library/stl-containers.md)。

`operator==`用于比较类模板[容器](../standard-library/sample-container-class.md)的两个对象的重载。

## <a name="syntax"></a>语法

```cpp
template <class Ty>
bool operator==(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>返回值

返回 `left.` [大小](../standard-library/container-class-size.md) `== right.size && equal(left.` [开始](../standard-library/container-class-begin.md) `, left.` [端](../standard-library/container-class-end.md) `, right.begin)` 。

## <a name="see-also"></a>请参阅

[\<sample container>](../standard-library/sample-container.md)
