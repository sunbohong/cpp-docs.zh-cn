---
description: 了解详细信息： noreturn
title: noreturn
ms.date: 11/04/2016
f1_keywords:
- noreturn_cpp
helpviewer_keywords:
- __declspec keyword [C++], noreturn
- noreturn __declspec keyword
ms.assetid: 9c6517e5-22d7-4051-9974-3d2200ae4d1d
ms.openlocfilehash: 829f8cc2d81ae1b9f55024442f1a38b495d54896
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97195354"
---
# <a name="noreturn"></a>noreturn

**Microsoft 专用**

此 **`__declspec`** 特性告知编译器函数不返回。 因此，编译器知道调用函数后的代码 **`__declspec(noreturn)`** 是无法访问的。

如果编译器找到带有不返回值的控制路径的函数，则它会生成警告 (C4715) 或错误消息 (C2202)。 如果由于从不返回的函数而无法访问控件路径，则可以使用 **`__declspec(noreturn)`** 来防止此警告或错误。

> [!NOTE]
> 添加 **`__declspec(noreturn)`** 到预期返回的函数可能会导致未定义的行为。

## <a name="example"></a>示例

在下面的示例中， **`else`** 子句不包含 return 语句。  `fatal`将声明为 **`__declspec(noreturn)`** 可避免出现错误或警告消息。

```cpp
// noreturn2.cpp
__declspec(noreturn) extern void fatal () {}

int main() {
   if(1)
     return 1;
   else if(0)
     return 0;
   else
     fatal();
}
```

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[__declspec](../cpp/declspec.md)<br/>
[关键字](../cpp/keywords-cpp.md)
