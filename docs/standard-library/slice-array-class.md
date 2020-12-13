---
description: 了解详细信息： slice_array 类
title: slice_array 类
ms.date: 11/04/2016
f1_keywords:
- valarray/std::slice_array
helpviewer_keywords:
- slice_array class
ms.assetid: a182d5f7-f35c-4e76-86f2-b5ac64ddc846
ms.openlocfilehash: 580a09d99b08bc563c64571247d74a980eb229f9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153975"
---
# <a name="slice_array-class"></a>slice_array 类

一个内部的辅助类模板，它通过提供由 valarray 的切片定义的子集数组之间的操作来支持切片对象。

## <a name="syntax"></a>语法

```cpp
template <class Type>
class slice_array : public slice {
public:
    typedef Type value_type;
    void operator=(const valarray<Type>& x) const;
    void operator=(const Type& x) const;
    void operator*=(const valarray<Type>& x) const;
    void operator/=(const valarray<Type>& x) const;
    void operator%=(const valarray<Type>& x) const;
    void operator+=(const valarray<Type>& x) const;
    void operator-=(const valarray<Type>& x) const;
    void operator^=(const valarray<Type>& x) const;
    void operator&=(const valarray<Type>& x) const;
    void operator|=(const valarray<Type>& x) const;
    void operator<<=(const valarray<Type>& x) const;
    void operator>>=(const valarray<Type>& x) const;
    // The rest is private or implementation defined
}
```

## <a name="remarks"></a>备注

此类描述一个对象，该对象存储对类 [valarray](../standard-library/valarray-class.md)的对象的引用以及 **\<Type>** 类 [切片](../standard-library/slice-class.md)的对象，该对象描述要从 **valarray \<Type>** 对象中选择的元素的序列。

类模板由某些 valarray 操作间接创建，无法在程序中直接使用。 切片下标运算符使用的内部辅助类模板：

`slice_array`\< **Type**>`valarray` <  **Type**：： `operator[]` ( `slice`) 。

`slice_array<Type>`仅通过编写一个形式为[va&#91;sl&#93;](../standard-library/valarray-class.md#op_at)的表达式来构造对象，以获取 valarray 的切片 `sl` `va` 。 类 slice_array 的成员函数的行为类似于为定义的对应函数签名 `valarray<Type>` ，只不过只影响选定元素的序列。 slice_array 控制的序列由构造函数的三个参数切片定义，即切片中第一个元素的索引、元素数以及元素之间的距离。 `va` **Va**[ `slice` (2，5，3) ] 声明的 valarray 中的 slice_array 切口选择索引为2、5、8、11和14的元素 `va` 。 若要过程有效，索引必须有效。

## <a name="example"></a>示例

有关如何声明和使用 slice_array 的示例，请参阅 [slice::slice](../standard-library/slice-class.md#slice) 的示例。

## <a name="requirements"></a>要求

**标头：**\<valarray>

**命名空间:** std

## <a name="see-also"></a>请参阅

[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
