---
description: '了解详细信息： operator &lt; = (&lt; 示例容器 &gt;) '
title: operator&lt;= (&lt;sample container&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::<=
- std.operator<=
- operator<=
- std.<=
- std::operator<=
- <=
helpviewer_keywords:
- operator<=
- operator <=
- <= operator, with specific objects
- <= operator
ms.assetid: 338577dd-dc88-4a2b-9e12-0379c54fc8a2
ms.openlocfilehash: 4455efcbd5b3ccca262265f44414b46d3e97f57d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337997"
---
# <a name="operatorlt-ltsample-containergt"></a>operator&lt;= (&lt;sample container&gt;)

> [!NOTE]
> 本主题在 Microsoft c + + 文档中作为 c + + 标准库中使用的容器的非功能性示例。 有关详细信息，请参阅 [C++ 标准库容器](../standard-library/stl-containers.md)。

重载 **运算符<=** 比较类模板 [容器](../standard-library/sample-container-class.md)的两个对象。

## <a name="syntax"></a>语法

```cpp
template <class Ty>
bool operator<=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>返回值

返回 `!(right < left)`。

## <a name="see-also"></a>请参阅

[\<sample container>](../standard-library/sample-container.md)
