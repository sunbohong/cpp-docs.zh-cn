---
description: 了解详细信息：/LINENUMBERS
title: /LINENUMBERS
ms.date: 11/04/2016
f1_keywords:
- /linenumbers
helpviewer_keywords:
- LINENUMBERS dumpbin option
- line numbers
- -LINENUMBERS dumpbin option
- /LINENUMBERS dumpbin option
ms.assetid: 1681d582-2c2f-484e-9920-109959549055
ms.openlocfilehash: 9df3d88476a82466f86ec23147c9f8f35f9b3f1d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191012"
---
# <a name="linenumbers"></a>/LINENUMBERS

```
/LINENUMBERS
```

## <a name="remarks"></a>备注

此选项显示 COFF 行号。 如果某个对象文件是使用程序数据库编译的，则该对象文件中存在行号 (/Zi) ，与 C7 兼容 (/Z7) 或行号仅 (/Zd) 。 可执行文件或 DLL 包含 COFF 行号（如果它是通过生成调试信息 (/DEBUG) 来链接的。

只有 [/HEADERS](headers.md) DUMPBIN 选项可用于由 [/GL](gl-whole-program-optimization.md) 编译器选项产生的文件。

## <a name="see-also"></a>请参阅

[DUMPBIN 选项](dumpbin-options.md)
