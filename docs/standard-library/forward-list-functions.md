---
description: 了解详细信息： &lt; forward_list &gt; 函数
title: '&lt;forward_list&gt; 函数'
ms.date: 11/04/2016
f1_keywords:
- forward_list/std::swap
ms.assetid: 0d6bc656-7049-4651-a4bd-c9a805e47756
ms.openlocfilehash: 3f827b777f2e6fa62dd78c7d737d5da84b50610c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324344"
---
# <a name="ltforward_listgt-functions"></a>&lt;forward_list&gt; 函数

## <a name="swap"></a><a name="swap"></a> 购

交换两个转发列表的元素。

```cpp
void swap(forward_list <Type, Allocator>& left, forward_list <Type, Allocator>& right);
```

### <a name="parameters"></a>parameters

*左中*\
一个 `forward_list` 类型的对象。

*然后*\
一个 `forward_list` 类型的对象。

### <a name="remarks"></a>备注

该模板函数执行 `left.swap(right)`。
