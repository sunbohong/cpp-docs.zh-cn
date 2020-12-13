---
description: 了解更多： end 函数
title: end 函数
ms.date: 01/22/2017
f1_keywords:
- collection/Windows::Foundation::Collections::end
helpviewer_keywords:
- end Function
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
ms.openlocfilehash: e29595e7eb403af85abdbfa18782adf1c33c308e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341966"
---
# <a name="end-function"></a>end 函数

返回指向集合末尾以外的迭代器，该集合由指定的接口参数访问。

## <a name="syntax"></a>语法

```

template <typename T>
    ::Platform::Collections::VectorIterator<T>
    end(
        IVector<T>^ v       );

template <typename T>
    ::Platform::Collections::VectorViewIterator<T>
    end(
        IVectorView<T>^ v
       );
template <typename T>
    ::Platform::Collections::InputIterator<T>
    end(
        IIterable<T>^ i
       );
```

#### <a name="parameters"></a>parameters

*T*<br/>
模板类型参数。

*v*<br/>
\<T> \<T> 由 IVector \<T> 或 IVectorView 接口访问的 Vector 或 VectorView 对象的集合 \<T> 。

*i*<br/>
Iiterable<t> 接口访问的任意 Windows 运行时对象的集合 \<T> 。

### <a name="return-value"></a>返回值

指向集合结尾之外的迭代器。

### <a name="remarks"></a>备注

前两个模板函数返回迭代器，第三个模板函数返回输入迭代器。

[返回的](../cppcx/platform-collections-vectorviewiterator-class.md) Platform::Collections::VectorViewIterator `end` 对象是存储 `VectorProxy<T>`类型的元素的代理迭代器。 不过，代理对象对于用户代码应该不可见。 有关更多信息，请参见 [集合 (C++/CX)](../cppcx/collections-c-cx.md)。

### <a name="requirements"></a>要求

**标头：** 集合。h

**命名空间：** Windows::Foundation::Collections

## <a name="see-also"></a>请参阅

[Windows：： Foundation：：集合命名空间](../cppcx/windows-foundation-collections-namespace-c-cx.md)
