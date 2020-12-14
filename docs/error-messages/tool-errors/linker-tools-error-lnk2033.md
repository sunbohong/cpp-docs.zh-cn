---
description: 了解详细信息：链接器工具错误 LNK2033
title: 链接器工具错误 LNK2033
ms.date: 11/04/2016
f1_keywords:
- LNK2033
helpviewer_keywords:
- LNK2033
ms.assetid: d61db467-9328-4788-bf54-e2a20537f13f
ms.openlocfilehash: 46ee94e0aff4379a6d28a508ed1394e90ef9a96d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97275641"
---
# <a name="linker-tools-error-lnk2033"></a>链接器工具错误 LNK2033

"type" (标记) 的 typeref 标记无法解析

类型在 MSIL 元数据中没有定义。

使用 **/clr： safe** 进行编译时，LNK2033 可能会发生，而 msil 模块中只有一个类型的前向声明，其中类型在 msil 模块中引用。

该类型需要在 **/clr： safe** 下定义。

有关详细信息，请参阅 [/clr (公共语言运行时编译) ](../../build/reference/clr-common-language-runtime-compilation.md)。

## <a name="example"></a>示例

下面的示例生成 LNK2033。

```cpp
// LNK2033.cpp
// compile with: /clr:safe
// LNK2033 expected
ref class A;
ref class B {};

int main() {
   A ^ aa = nullptr;
   B ^ bb = nullptr;   // OK
};
```
