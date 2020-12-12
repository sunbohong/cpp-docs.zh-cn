---
description: 了解详细信息：链接器工具警告 LNK4286
title: 链接器工具警告 LNK4286
ms.date: 04/15/2019
f1_keywords:
- LNK4286
helpviewer_keywords:
- LNK4286
ms.openlocfilehash: 6a1e397967857ae3f982bf8f5e55f4bf74c9abe4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244441"
---
# <a name="linker-tools-warning-lnk4286"></a>链接器工具警告 LNK4286

> "*filename_1*" 中定义的符号 "*symbol*" 由 "*filename_2 .obj*" 导入

为 *符号* 指定了 [__declspec (dllimport)](../../cpp/dllexport-dllimport.md) ，即使该符号是在同一映像的对象文件 *filename_1 .obj* 中定义的。 删除 `__declspec(dllimport)` 修饰符以解决此警告。

## <a name="remarks"></a>备注

警告 LNK4286 是更通用的 [链接器工具警告 LNK4217](linker-tools-warning-lnk4217.md)版本。 当链接器可以判断哪个对象文件引用了符号而不是哪个函数时，链接器会生成警告 LNK4286。

若要解析 LNK4286，请 `__declspec(dllimport)` 从 *filename_2 .obj* 中引用的 *符号* 的前向声明中删除声明修饰符。

尽管最终生成的代码的行为正确，但生成的用于调用导入函数的代码不如直接调用函数。 使用 [/clr](../../build/reference/clr-common-language-runtime-compilation.md) 选项编译时不会出现此警告。

有关导入和导出数据声明的详细信息，请参阅 [dllexport、dllimport](../../cpp/dllexport-dllimport.md)。

## <a name="see-also"></a>请参阅

[链接器工具警告 LNK4049](linker-tools-warning-lnk4049.md) \
[链接器工具警告 LNK4217](linker-tools-warning-lnk4217.md) \
[dllexport、dllimport](../../cpp/dllexport-dllimport.md)
