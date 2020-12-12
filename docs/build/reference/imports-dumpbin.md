---
description: '了解详细信息：/IMPORTS (DUMPBIN) '
title: /IMPORTS (DUMPBIN)
ms.date: 11/04/2016
f1_keywords:
- /imports
helpviewer_keywords:
- IMPORTS dumpbin option
- /IMPORTS dumpbin option
- -IMPORTS dumpbin option
ms.assetid: 6a296216-2b1b-40f8-8736-cd4553a22456
ms.openlocfilehash: 86c428280bbca3a4957f7d7a0a640482607547de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97199787"
---
# <a name="imports-dumpbin"></a>/IMPORTS (DUMPBIN)

```
/IMPORTS[:file]
```

此选项显示从导入到可执行文件或 DLL 的静态链接和 [延迟加载](linker-support-for-delay-loaded-dlls.md))  (dll 的列表，以及每个 dll 的所有单独导入。

可选 `file` 规范允许指定仅显示该 DLL 的导入。 例如：

```
dumpbin /IMPORTS:msvcrt.dll
```

## <a name="remarks"></a>备注

此选项显示的输出类似于 [/EXPORTS](dash-exports.md) 输出。

只有 [/HEADERS](headers.md) DUMPBIN 选项可用于由 [/GL](gl-whole-program-optimization.md) 编译器选项产生的文件。

## <a name="see-also"></a>请参阅

[DUMPBIN 选项](dumpbin-options.md)
