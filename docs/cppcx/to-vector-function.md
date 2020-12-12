---
description: 了解详细信息： to_vector 函数
title: to_vector 函数
ms.date: 12/30/2016
f1_keywords:
- collection/Windows::Foundation::Collections::to_vector
helpviewer_keywords:
- to_vector Function
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
ms.openlocfilehash: 77d6bee58a793946f91bc03ba4afed35aa7252cd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97307582"
---
# <a name="to_vector-function"></a>to_vector 函数

返回 `std::vector` ，其值与指定 IVector 或 IVectorView 参数所代表的集合相同。

## <a name="syntax"></a>语法

```
template <typename T>
inline ::std::vector<T> to_vector(IVector<T>^ v);

template <typename T>
inline ::std::vector<T> to_vector(IVectorView<T>^ v);
```

#### <a name="parameters"></a>parameters

*T*<br/>
模板类型参数。

*v*<br/>
提供对基础 Vector 或 VectorView 对象访问的 IVector 或 IVectorView 接口。

### <a name="return-value"></a>返回值

### <a name="requirements"></a>要求

**标头：** 集合。h

**命名空间：** Windows::Foundation::Collections

## <a name="see-also"></a>请参阅

[Windows：： Foundation：：集合命名空间](../cppcx/windows-foundation-collections-namespace-c-cx.md)
