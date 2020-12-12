---
description: '了解详细信息： Context-Sensitive 关键字 (c + +/CLI 和 c + +/CX) '
title: 上下文相关关键字（C++/CLI 和 C++/CX）
ms.date: 10/12/2018
ms.topic: reference
f1_keywords:
- internal_CPP
helpviewer_keywords:
- context-sensitive keywords
ms.assetid: e33da089-f434-44e9-8cce-4668d05a8939
ms.openlocfilehash: 7c005b1a6149f010b9729db5459fa3951bc50521
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97176855"
---
# <a name="context-sensitive-keywords--ccli-and-ccx"></a>上下文相关关键字（C++/CLI 和 C++/CX）

上下文相关关键字是仅在特定上下文中才能识别出来的语言元素。 在特定的上下文以外，区分上下文关键字可以是用户定义的符号。

## <a name="all-runtimes"></a>所有运行时

### <a name="remarks"></a>备注

下面是区上下文关键字的列表：

- [abstract](abstract-cpp-component-extensions.md)

- [delegate](delegate-cpp-component-extensions.md)

- [event](event-cpp-component-extensions.md)

- [finally](../dotnet/finally.md)

- [for each, in](../dotnet/for-each-in.md)

- [initonly](../dotnet/initonly-cpp-cli.md)

- `internal`

- literal

- [override](override-cpp-component-extensions.md)

- [property](property-cpp-component-extensions.md)

- [sealed](sealed-cpp-component-extensions.md)

- `where`（属于[泛型](generics-cpp-component-extensions.md)）

出于可读性目的，建议限制为仅将上下文相关关键字用作用户定义符号。

## <a name="windows-runtime"></a>Windows 运行时

### <a name="remarks"></a>备注

（此功能没有特定于平台的备注。）

### <a name="requirements"></a>要求

编译器选项：`/ZW`

## <a name="common-language-runtime"></a>公共语言运行时

### <a name="remarks"></a>备注

（此功能没有特定于平台的备注。）

### <a name="requirements"></a>要求

编译器选项：`/clr`

### <a name="examples"></a>示例

下面的代码示例显示，在相应的上下文中， **`property`** 可以使用区分上下文的关键字来定义属性和变量。

```cpp
// context_sensitive_keywords.cpp
// compile with: /clr
public ref class C {
   int MyInt;
public:
   C() : MyInt(99) {}

   property int Property_Block {   // context-sensitive keyword
      int get() { return MyInt; }
   }
};

int main() {
   int property = 0;               // variable name
   C ^ MyC = gcnew C();
   property = MyC->Property_Block;
   System::Console::WriteLine(++property);
}
```

```Output
100
```

## <a name="see-also"></a>请参阅

[适用于 .NET 和 UWP 的组件扩展](component-extensions-for-runtime-platforms.md)
