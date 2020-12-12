---
description: 了解详细信息：链接器工具警告 LNK4227
title: 链接器工具警告 LNK4227
ms.date: 11/04/2016
f1_keywords:
- LNK4227
helpviewer_keywords:
- LNK4227
ms.assetid: 941a0414-9964-4e02-8487-f9daa42ef7f9
ms.openlocfilehash: d8fd0f6755b675490f35579a4609c5b2742e4e46
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97180417"
---
# <a name="linker-tools-warning-lnk4227"></a>链接器工具警告 LNK4227

> 元数据操作警告 (*HRESULT*) ： *warning_message*

合并时，链接器检测到元数据差异：

- 具有当前正在生成的程序集的一个或多个引用的程序集。

- 编译中的一个或多个源代码文件。

例如，如果有两个名称相同但参数信息声明不同 (的全局函数，则可能会导致 LNK4227，因为声明在所有 compiland) 中不一致。 对每个 .obj 文件使用 ildasm.exe/TEXT/METADATA *object_file* ，以查看类型的不同之处。

LNK4227 还用于报告与其他工具有关的问题。 搜索警告消息以获取详细信息。

要解决此警告，必须修复元数据问题。

## <a name="examples"></a>示例

当被引用的程序集的签名不同于引用它的程序集时，将生成 LNK4227。

下面的示例生成 LNK4227：

```cpp
// LNK4227.cpp
// compile with: /clr
using namespace System::Reflection;

[assembly:AssemblyDelaySignAttribute(false)];

int main() {}
```

然后

```cpp
// LNK4227b.cpp
// compile with: /clr LNK4227.cpp /FeLNK4227b.exe
using namespace System::Reflection;
using namespace System::Runtime::CompilerServices;

[assembly:AssemblyDelaySignAttribute(true)];
// Try the following line instead
// [assembly:AssemblyDelaySignAttribute(false)];

ref class MyClass
{
};
```

如果将格式不正确的版本传递给程序集特性，也可以生成 LNK4227。  "*" 表示法特定于 `AssemblyVersionAttribute` 。  若要解决此警告，请仅在的版本属性中使用数字 `AssemblyVersionAttribute` 。

下面的示例生成 LNK4227：

```cpp
// LNK4227e.cpp
// compile with: /clr /LD /W1
using namespace System::Reflection;
[assembly:AssemblyVersionAttribute("2.3.*")];   // OK
[assembly:AssemblyFileVersionAttribute("2.3.*")];   // LNK4227
// try the following line instead
// [assembly:AssemblyFileVersionAttribute("2.3")];
```
