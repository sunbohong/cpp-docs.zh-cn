---
description: 了解详细信息：编译器警告 (等级 1) C4462
title: 编译器警告（等级 1）C4462
ms.date: 10/25/2017
f1_keywords:
- C4462
helpviewer_keywords:
- C4462
ms.assetid: 4e20aca4-293e-4c75-a83d-961c27ab7840
ms.openlocfilehash: 81696df228b2cbe6278521f602d2a6f986cacb13
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97212527"
---
# <a name="compiler-warning-level-1-c4462"></a>编译器警告（等级 1）C4462

> 无法确定此类型的 GUID。 程序可能在运行时失败。

当作为某个 Windows 运行时应用程序或组件的类型参数之一的公共 `TypedEventHandler` 具有对封闭类的引用时，该应用程序或组件中将出现警告 C4462。

此警告会自动提升为错误。 如果要修改此行为，请使用 [#pragma 警告](../../preprocessor/warning.md)。 例如，若要将 C4462 添加到第4级警告问题，请将以下代码行添加到源代码文件中：

```cpp
#pragma warning(4:4462)
```

## <a name="example"></a>示例

此示例生成警告 C4462：

```cpp
namespace N
{
    public ref struct EventArgs sealed {};
    public ref struct R sealed
    {
        R() {}
        event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
    };
}

[Platform::MTAThread]
int main()
{
    auto x = ref new N::R();
}
```

有两种解决此错误的方法。 一种方法（如下一个示例所示）是为事件提供内部可访问性，使它对同一可执行文件中的代码可用，而不对其他 Windows 运行时组件中的代码可用。

```cpp
internal:
    event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
```

如果事件必须是公共的，则可以使用另一个解决方法，即通过默认接口公开它：

```cpp
ref struct R;
public interface struct IR{ event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;};

public ref struct R sealed : [Windows::Foundation::Metadata::Default] IR
{
    R() {}
    virtual event Windows::Foundation::TypedEventHandler<R ^, EventArgs^>^ e;
};
```

仅当 `Windows::Foundation::TypedEventHandler<R^, EventArgs^>^` 类型是从另一个组件访问时，才使用该类型的 GUID。 在采用第一个解决方法后，该类型只能在自己的组件中进行访问，因而可以解决问题。 否则，编译器不得不假定出现最坏的情况并发出警告。
