---
title: 扩展通配符自变量
description: 如何使用链接器选项在程序中处理通配符命令行参数。
ms.date: 11/20/2020
helpviewer_keywords:
- asterisk wildcard
- question mark, wildcard
- expanding wildcard arguments
- wildcards, expanding
ms.openlocfilehash: b847a5dd8af577a4e30edcd9bc7fc34add296c17
ms.sourcegitcommit: b02c61667ff7f38e7add266d0aabd8463f2dbfa1
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/23/2020
ms.locfileid: "95483303"
---
# <a name="expanding-wildcard-arguments"></a>扩展通配符自变量

通配符参数扩展是特定于 Microsoft 的。

在运行 C 程序时，你可以使用两个通配符（问号 (`?`) 和星号 (`*`)）之一，以便在命令行上指定文件名和路径参数。

默认情况下，命令行参数中不展开通配符。 你可以通过链接 `setargv.obj` 或 `wsetargv.obj` 文件将普通参数向量 `argv` 加载例程替换为展开通配符的版本。 如果程序使用 `main` 函数，请与 `setargv.obj` 链接。 如果程序使用 `wmain` 函数，请与 `wsetargv.obj` 链接。 它们具有等效的行为。 

若要与 `setargv.obj` 或 `wsetargv.obj` 链接，请使用 `/link` 选项。 例如：

**`cl example.c /link setargv.obj`**

按照与操作系统命令相同的方式展开通配符。

## <a name="see-also"></a>请参阅

[链接选项](../c-runtime-library/link-options.md)\
[`main` 函数和程序执行](../c-language/main-function-and-program-execution.md)
