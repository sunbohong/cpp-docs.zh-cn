---
description: 了解详细信息： back_inserter 函数
title: back_inserter 函数
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections::back_inserter
helpviewer_keywords:
- back_inserter Function
ms.assetid: 91476338-5548-44b7-bc7e-2150f4fbe31a
ms.openlocfilehash: d2483c9947fbf3a7bc04024221ec6e582e416f84
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223576"
---
# <a name="back_inserter-function"></a>back_inserter 函数

返回用于在指定集合末尾插入元素的迭代器。

## <a name="syntax"></a>语法

```

template <typename T>
Platform::BackInsertIterator<T>
    back_inserter(IVector<T>^ v);

template<typename T>
Platform::BackInsertIterator<T>
   back_inserter(IObservableVector<T>^ v);
```

#### <a name="parameters"></a>parameters

*T*<br/>
模板类型参数。

*v*<br/>
提供对基础集合访问的接口指针。

### <a name="return-value"></a>返回值

迭代器。

### <a name="requirements"></a>要求

**标头：** 集合。h

**命名空间：** Windows::Foundation::Collections

## <a name="see-also"></a>请参阅

[Windows：： Foundation：：集合命名空间](../cppcx/windows-foundation-collections-namespace-c-cx.md)
