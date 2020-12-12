---
description: 了解详细信息： &lt; 列表 &gt; 函数
title: '&lt;列出 &gt; 函数 |Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- list/std::swap
ms.openlocfilehash: 6a94fcc916db08a510a968b66b0a0dc0cfa9b8e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97284702"
---
# <a name="ltlistgt-functions"></a>&lt;列出 &gt; 函数

## <a name="swap"></a><a name="swap"></a> 购

交换两个列表的元素。

```cpp
template <class T, class Allocator>
    void swap(list<T, Allocator>& left, list<T, Allocator>& right)
```

### <a name="parameters"></a>parameters

*左中*\
一个 `list` 类型的对象。

*然后*\
一个 `list` 类型的对象。

### <a name="remarks"></a>备注

该模板函数执行 `left.swap(right)`。
