---
description: 了解详细信息： reference_wrapper 类
title: reference_wrapper 类
ms.date: 11/04/2016
f1_keywords:
- functional/std::reference_wrapper
- type_traits/std::reference_wrapper
- xrefwrap/std::reference_wrapper
- type_traits/std::reference_wrapper::get
- type_traits/std::reference_wrapper::operator()
- functional/std::reference_wrapper::result_type
- functional/std::reference_wrapper::type
- functional/std::reference_wrapper::get
- functional/std::reference_wrapper::operator()
helpviewer_keywords:
- std::reference_wrapper [C++]
- std::reference_wrapper [C++]
- std::reference_wrapper [C++], result_type
- std::reference_wrapper [C++], type
- std::reference_wrapper [C++], get
ms.assetid: 90b8ed62-e6f1-44ed-acc7-9619bd58865a
ms.openlocfilehash: 5d3550a6ff579ea1e4174459d3ab1eab07b8a5d4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97337857"
---
# <a name="reference_wrapper-class"></a>reference_wrapper 类

包装引用。

## <a name="syntax"></a>语法

```cpp
template <class Ty>
class reference_wrapper
{
    typedef Ty type;

    reference_wrapper(Ty&) noexcept;
    operator Ty&() const noexcept;
    Ty& get() const noexcept;

    template <class... Types>
    auto operator()(Types&&... args) const ->
        decltype(std::invoke(get(), std::forward<Types>(args)...));
};
```

## <a name="remarks"></a>备注

`reference_wrapper<Ty>` 是可构造副本和可指定副本的包装器，它包装对某个 `Ty` 类型对象或函数的引用，并具有指向该类型对象的指针。 `reference_wrapper` 可用于将引用存储在标准容器内，并根据对 `std::bind` 的引用传递对象。

类型 `Ty` 必须是一种对象类型或函数类型，或会在编译时失败的静态断言。

帮助程序函数 [std::ref](functional-functions.md#ref) 和 [std::cref](functional-functions.md#cref) 可以用于创建 `reference_wrapper` 对象。

## <a name="members"></a>成员

### <a name="constructors"></a>构造函数

|名称|描述|
|-|-|
|[reference_wrapper](#reference_wrapper)|构造一个 `reference_wrapper`。|

### <a name="typedefs"></a>Typedef

|名称|描述|
|-|-|
|[result_type](#result_type)|已包装引用的弱结果类型。|
|type|已包装引用的类型。|

### <a name="functions"></a>函数

|名称|描述|
|-|-|
|[get](#get)|获取已包装的引用。|

### <a name="operators"></a>运算符

|名称|描述|
|-|-|
|[运算符 Ty&amp;](#op_ty_amp)|获取指向已包装引用的指针。|
|[运算符 ( # B1 ](#op_call)|调用已包装的引用。|

## <a name="get"></a><a name="get"></a> 获取

获取已包装的引用。

```cpp
Ty& get() const noexcept;
```

### <a name="remarks"></a>备注

成员函数返回已包装的引用。

### <a name="example"></a>示例

```cpp
// std__functional__reference_wrapper_get.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int main() {
    int i = 1;
    std::reference_wrapper<int> rwi(i);

    std::cout << "i = " << i << std::endl;
    std::cout << "rwi = " << rwi << std::endl;
    rwi.get() = -1;
    std::cout << "i = " << i << std::endl;

    return (0);
}
```

```Output
i = 1
rwi = 1
i = -1
```

## <a name="operator-tyamp"></a><a name="op_ty_amp"></a> 运算符 Ty&amp;

获取已包装的引用。

```cpp
operator Ty&() const noexcept;
```

### <a name="remarks"></a>备注

该成员运算符将返回 `*ptr`。

### <a name="example"></a>示例

```cpp
// std__functional__reference_wrapper_operator_cast.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int main() {
    int i = 1;
    std::reference_wrapper<int> rwi(i);

    std::cout << "i = " << i << std::endl;
    std::cout << "(int)rwi = " << (int)rwi << std::endl;

    return (0);
}
```

```Output
i = 1
(int)rwi = 1
```

## <a name="operator"></a><a name="op_call"></a> 运算符 ( # A1

调用已包装的引用。

```cpp
template <class... Types>
auto operator()(Types&&... args);
```

### <a name="parameters"></a>parameters

*各种*\
参数列表类型。

*args*\
参数列表。

### <a name="remarks"></a>备注

模板成员 `operator()` 返回 `std::invoke(get(), std::forward<Types>(args)...)`。

### <a name="example"></a>示例

```cpp
// std__functional__reference_wrapper_operator_call.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val) {
    return (-val);
}

int main() {
    std::reference_wrapper<int (int)> rwi(neg);

    std::cout << "rwi(3) = " << rwi(3) << std::endl;

    return (0);
}
```

```Output
rwi(3) = -3
```

## <a name="reference_wrapper"></a><a name="reference_wrapper"></a> reference_wrapper

构造一个 `reference_wrapper`。

```cpp
reference_wrapper(Ty& val) noexcept;
```

### <a name="parameters"></a>parameters

*Ty*\
要包装的类型。

*初始值*\
要包装的值。

### <a name="remarks"></a>备注

该构造函数将存储的值 `ptr` 设置为 `&val`。

### <a name="example"></a>示例

```cpp
// std__functional__reference_wrapper_reference_wrapper.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val) {
    return (-val);
}

int main() {
    int i = 1;
    std::reference_wrapper<int> rwi(i);

    std::cout << "i = " << i << std::endl;
    std::cout << "rwi = " << rwi << std::endl;
    rwi.get() = -1;
    std::cout << "i = " << i << std::endl;

    return (0);
}
```

```Output
i = 1
rwi = 1
i = -1
```

## <a name="result_type"></a><a name="result_type"></a> result_type

已包装引用的弱结果类型。

```cpp
typedef R result_type;
```

### <a name="remarks"></a>备注

`result_type` typedef 是已包装函数的弱结果类型的同义词。 typedef 仅对函数类型有意义。

### <a name="example"></a>示例

```cpp
// std__functional__reference_wrapper_result_type.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val) {
    return (-val);
}

int main() {
    typedef std::reference_wrapper<int (int)> Mywrapper;
    Mywrapper rwi(neg);
    Mywrapper::result_type val = rwi(3);

    std::cout << "val = " << val << std::endl;

    return (0);
}
```

```Output
val = -3
```

## <a name="type"></a><a name="type"></a> 类型

已包装引用的类型。

```cpp
typedef Ty type;
```

### <a name="remarks"></a>备注

Typedef 是模板参数 `Ty`的同义词。

### <a name="example"></a>示例

```cpp
// std__functional__reference_wrapper_type.cpp
// compile with: /EHsc
#include <functional>
#include <iostream>

int neg(int val) {
    return (-val);
}

int main() {
    int i = 1;
    typedef std::reference_wrapper<int> Mywrapper;
    Mywrapper rwi(i);
    Mywrapper::type val = rwi.get();

    std::cout << "i = " << i << std::endl;
    std::cout << "rwi = " << val << std::endl;

    return (0);
}
```

```Output
i = 1
rwi = 1
```
