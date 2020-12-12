---
description: 了解有关以下方面的详细信息： operator！ =
title: operator!=
ms.date: 11/04/2016
f1_keywords:
- std::!=
- '!='
- std::operator!=
- std.operator!=
- std.!=
- operator!=
helpviewer_keywords:
- '!= operator'
- operator!=
- operator !=
ms.assetid: ef2be7f0-1c94-4edc-b65c-731fddd519f4
ms.openlocfilehash: 3b5efe9cc1c3157becd9afe4cf5c4e8020ec9e0b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97297052"
---
# <a name="operator"></a>operator!=

> [!NOTE]
> 本主题在 Microsoft c + + 文档中作为 c + + 标准库中使用的容器的非功能性示例。 有关详细信息，请参阅 [C++ 标准库容器](../standard-library/stl-containers.md)。

`operator!=`用于比较类模板[容器](../standard-library/sample-container-class.md)的两个对象的重载。

## <a name="syntax"></a>语法

```cpp
template <class Ty>
bool operator!=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>返回值

返回 `!(left == right)`。

## <a name="see-also"></a>请参阅

[\<sample container>](../standard-library/sample-container.md)
