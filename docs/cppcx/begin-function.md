---
description: 了解有关： begin 函数的详细信息
title: begin 函数
ms.date: 01/22/2017
f1_keywords:
- collection/Windows::Foundation::Collections::begin
helpviewer_keywords:
- begin Function
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
ms.openlocfilehash: ae59a4b4344da520d86c216f4c9979953e16753c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97302759"
---
# <a name="begin-function"></a>begin 函数

返回指向指定接口参数所访问的集合开头的迭代器。

## <a name="syntax"></a>语法

```

template <typename T>
    ::Platform::Collections::VectorIterator<T>
    begin(
          IVector<T>^ v         );

template <typename T>
    ::Platform::Collections::VectorViewIterator<T>
    begin(
          IVectorView<T>^ v
         );

template <typename T>
    ::Platform::Collections::InputIterator<T>
    begin(
          IIterable<T>^ i         );
```

#### <a name="parameters"></a>parameters

*T*<br/>
模板类型参数。

*v*<br/>
\<T> \<T> 由 IVector \<T> 或 IVectorView 接口访问的 Vector 或 VectorView 对象的集合 \<T> 。

*i*<br/>
Iiterable<t> 接口访问的任意 Windows 运行时对象的集合 \<T> 。

### <a name="return-value"></a>返回值

指向集合开头的迭代器。

### <a name="remarks"></a>备注

前两个模板函数返回迭代器，第三个模板函数返回输入迭代器。

Begin 返回的 VectorIterator 对象是存储 VectorProxy 类型的元素的代理迭代器 \<T> 。 不过，代理对象对于用户代码应该不可见。 有关更多信息，请参见 [集合 (C++/CX)](../cppcx/collections-c-cx.md)。

### <a name="requirements"></a>要求

**标头：** 集合。h

**命名空间：** Windows::Foundation::Collections

## <a name="see-also"></a>请参阅

[Windows：： Foundation：：集合命名空间](../cppcx/windows-foundation-collections-namespace-c-cx.md)
