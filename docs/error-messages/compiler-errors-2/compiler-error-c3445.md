---
description: 了解更多：编译器错误 C3445
title: 编译器错误 C3445
ms.date: 04/10/2017
f1_keywords:
- C3445
helpviewer_keywords:
- C3445
ms.assetid: 0d272bfc-136b-4025-a9ba-5e4eea5f8215
ms.openlocfilehash: 992c0e4f6e8b068bf6c038a6a5f58b45dd80a3c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97316025"
---
# <a name="compiler-error-c3445"></a>编译器错误 C3445

> "*type*" 的复制列表初始化不能使用显式构造函数

根据 ISO c + + 17 标准，编译器需要在复制列表初始化中考虑使用显式构造函数进行重载解析，但如果实际选择了该重载，则必须引发错误。

从 Visual Studio 2017 开始，编译器将使用 Visual Studio 2015 找不到的初始值设定项列表查找与对象创建相关的错误。 这些错误可能导致运行时出现故障或未定义的行为。

## <a name="example"></a>示例

下面的示例生成 C3445。

```cpp
// C3445.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1 = { 1 };     // error C3445: copy-list-initialization of
                      //     'A' cannot use an explicit constructor
}
```

若要更正此错误，请改为使用直接初始化：

```cpp
// C3445b.cpp
struct A
{
    explicit A(int) {}
    A(double) {}
};

int main()
{
    A a1{ 1 };
}
```
