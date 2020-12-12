---
description: 了解详细信息：链接器工具警告 LNK4049
title: 链接器工具警告 LNK4049
ms.date: 04/15/2019
f1_keywords:
- LNK4049
helpviewer_keywords:
- LNK4049
ms.assetid: 5fd5fb24-c860-4149-a557-0ac26a65d97c
ms.openlocfilehash: 2451c5533b22eacb0b640ed301203f6332b6681d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97210317"
---
# <a name="linker-tools-warning-lnk4049"></a>链接器工具警告 LNK4049

> 导入 "*filename .obj*" 中定义的符号 "*symbol*"

已为 *符号* 指定了 [__declspec (dllimport)](../../cpp/dllexport-dllimport.md) ，即使该符号是在同一映像的对象文件 *文件名 .obj* 中定义的。 删除 `__declspec(dllimport)` 修饰符以解决此警告。

## <a name="remarks"></a>备注

当你在一个对象文件中定义符号，并使用 `__declspec(dllimport)` 另一个对象中的声明修饰符引用该符号时，链接器将生成此警告。

警告 LNK4049 是更通用的 [链接器工具警告 LNK4217](linker-tools-warning-lnk4217.md)版本。 链接器无法确定引用导入的符号的函数或对象文件时，会生成警告 LNK4049。

生成 LNK4049 而不是 LNK4217 的常见情况是：

- 使用 [/INCREMENTAL](../../build/reference/incremental-link-incrementally.md) 选项时。

- 当使用 [/ltcg](../../build/reference/ltcg-link-time-code-generation.md) 选项时。

若要解析 LNK4049，请尝试执行以下过程之一：

- `__declspec(dllimport)`从触发 LNK4049 的符号的前向声明中删除修饰符。 可以使用 **DUMPBIN** 实用工具在二进制映像中搜索符号。 **DUMPBIN/SYMBOLS** 开关显示映像的 COFF 符号表。 有关 **DUMPBIN** 实用工具的详细信息，请参阅 [DUMPBIN 参考](../../build/reference/dumpbin-reference.md)。

- 暂时禁用增量链接和全程序优化。 重新编译时，应用程序将生成警告 LNK4217，其中包括引用导入的符号的函数的名称。 `__declspec(dllimport)`从导入的符号中删除声明修饰符，并根据需要重新启用增量链接或完全程序优化。

尽管最终生成的代码的行为正确，但生成的用于调用导入函数的代码不如直接调用函数有效。 使用 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 选项编译时不会出现此警告。

有关导入和导出数据声明的详细信息，请参阅 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)。

## <a name="example"></a>示例

链接以下两个模块将生成 LNK4049。 第一个模块生成包含单个导出函数的对象文件。

```cpp
// LNK4049a.cpp
// compile with: /c

__declspec(dllexport) int func()
{
   return 3;
}
```

第二个模块生成一个对象文件，其中包含对第一个模块中导出的函数的前向声明，并在函数内调用此函数 `main` 。 将此模块与第一个模块链接将生成 LNK4049。 `__declspec(dllimport)`从声明中删除修饰符以解决此警告。

```cpp
// LNK4049b.cpp
// compile with: /link /WX /LTCG LNK4049a.obj
// LNK4049 expected

__declspec(dllimport) int func();
// try the following line instead
// int func();

int main()
{
   return func();
}
```

## <a name="see-also"></a>请参阅

[链接器工具警告 LNK4217](linker-tools-warning-lnk4217.md) \
[链接器工具警告 LNK4286](linker-tools-warning-lnk4286.md) \
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)
