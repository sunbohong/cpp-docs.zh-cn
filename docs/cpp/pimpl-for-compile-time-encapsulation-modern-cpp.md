---
description: '了解有关以下内容的详细信息：用于 pimpl For Compile-Time 封装 (新式 c + +) '
title: 用于编译时封装的 Pimpl（现代 C++）
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c3e8a90a-b328-4990-82bb-e1b147f76e07
ms.openlocfilehash: 95d1ca4f377cc911e862885e86f846d8536d3b1f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145881"
---
# <a name="pimpl-for-compile-time-encapsulation-modern-c"></a>用于编译时封装的 Pimpl（现代 C++）

*用于 pimpl* 方法是一项现代的 c + + 技术，用于隐藏实现，最小化耦合和分隔接口。 用于 pimpl 是 "指向实现的指针" 的简称。 您可能已熟悉此概念，但通过其他名称（如 Cheshire Cat 或编译器防火墙方法）了解它。

## <a name="why-use-pimpl"></a>为什么使用用于 pimpl？

下面是用于 pimpl 方法如何提高软件开发生命周期：

- 编译依赖项的最小化。

- 接口和实现的分离。

- 可移植性。

## <a name="pimpl-header"></a>用于 pimpl 标头

```cpp
// my_class.h
class my_class {
   //  ... all public and protected stuff goes here ...
private:
   class impl; unique_ptr<impl> pimpl; // opaque type here
};
```

用于 pimpl 用法避免了重新生成级联和脆弱对象布局。 它非常适合 (的) 常用类型。

## <a name="pimpl-implementation"></a>用于 pimpl 实现

`impl`在 .cpp 文件中定义类。

```cpp
// my_class.cpp
class my_class::impl {  // defined privately here
  // ... all private data and functions: all of these
  //     can now change without recompiling callers ...
};
my_class::my_class(): pimpl( new impl )
{
  // ... set impl values ...
}
```

## <a name="best-practices"></a>最佳做法

考虑是否添加对非引发交换专用化的支持。

## <a name="see-also"></a>请参阅

[欢迎回到 C++](../cpp/welcome-back-to-cpp-modern-cpp.md)<br/>
[C++ 语言参考](../cpp/cpp-language-reference.md)<br/>
[C++ 标准库](../standard-library/cpp-standard-library-reference.md)
