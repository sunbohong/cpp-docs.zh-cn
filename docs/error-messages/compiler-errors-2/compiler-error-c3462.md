---
title: 编译器错误 C3462
ms.date: 11/04/2016
f1_keywords:
- C3462
helpviewer_keywords:
- C3462
ms.assetid: 56b75f35-9fad-42d9-a969-eeca5d709bec
ms.openlocfilehash: f267d195ba851a9d585961848062fa271168aeb8
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743329"
---
# <a name="compiler-error-c3462"></a>编译器错误 C3462

“type”：只有导入的类型才能被转发

TypeForwardedTo 特性必须应用于引用的元数据中的类型。

有关详细信息，请参阅 [类型转发 (c + +/cli) ](../../extensions/type-forwarding-cpp-cli.md)。

## <a name="examples"></a>示例

下面的示例创建一个组件。

```cpp
// C3462.cpp
// compile with: /clr /LD
public ref class R {};
```

下面的示例生成 C3462。

```cpp
// C3462b.cpp
// compile with: /clr /c
#using "C3462.dll"
ref class N {};
[assembly:TypeForwardedTo(N::typeid)];   // C3462
[assembly:TypeForwardedTo(R::typeid)];
```
