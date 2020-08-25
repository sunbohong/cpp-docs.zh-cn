---
title: nested_exception 类
ms.date: 11/04/2016
f1_keywords:
- exception/std::nested_exception
helpviewer_keywords:
- nested_exception class
ms.assetid: 5ae2c4ef-c7ad-4469-8a9e-a773e86bb000
ms.openlocfilehash: 4ab48f714e8b4de1a47674f1af8fe25467279f94
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88836434"
---
# <a name="nested_exception-class"></a>nested_exception 类

类描述用于多重继承的异常。 它捕获当前处理的异常，并将其存储起来供以后使用。

## <a name="syntax"></a>语法

```cpp
class nested_exception {
    public:
        nested_exception();
        nested_exception(const nested_exception&) = default;
        virtual ~nested_exception() = default; // access functions
};
```

## <a name="members"></a>成员

### <a name="operators"></a>运算符

|名称|说明|
|-|-|
|[operator =](#op_as)|赋值运算符。|

### <a name="functions"></a>函数

|名称|说明|
|-|-|
|[rethrow_nested](#rethrow_nested)|引发存储的异常。|
|[nested_ptr](#nested_ptr)|返回存储的异常。|

### <a name="operator"></a><a name="op_as"></a> operator =

```cpp
nested_exception& operator=(const nested_exception&) = default;
```

### <a name="nested_ptr"></a><a name="nested_ptr"></a> nested_ptr

```cpp
exception_ptr nested_ptr() const;
```

#### <a name="return-value"></a>返回值

由此对象捕获的存储异常 `nested_exception` 。

### <a name="rethrow_nested"></a><a name="rethrow_nested"></a> rethrow_nested

```cpp
[[noreturn]] void rethrow_nested() const;
```

#### <a name="remarks"></a>注解

如果 `nested_ptr()` 返回一个 null 指针，则该函数将调用 `std::terminate()` 。 否则，它会引发由捕获的存储异常 **`*this`** 。

## <a name="requirements"></a>要求

**标头：**\<exception>

**命名空间:** std

## <a name="see-also"></a>另请参阅

[exception 类](../standard-library/exception-class.md)\
[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
