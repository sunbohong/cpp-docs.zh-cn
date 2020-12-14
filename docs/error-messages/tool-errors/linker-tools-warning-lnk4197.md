---
description: 了解详细信息：链接器工具警告 LNK4197
title: 链接器工具警告 LNK4197
ms.date: 09/05/2018
f1_keywords:
- LNK4197
helpviewer_keywords:
- LNK4197
ms.assetid: 8a976fd7-a74b-4c83-ab66-a9e7d7073c4a
ms.openlocfilehash: a2054caf5e60cc7333c0da70c6027966536e8406
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294348"
---
# <a name="linker-tools-warning-lnk4197"></a>链接器工具警告 LNK4197

> 多次指定导出 "*exportname*";使用第一个规范

使用多种不同的方式指定导出。 链接器使用第一个规范并忽略其余。

如果要重新生成 C 运行时库，可以忽略此消息。

如果按相同方式多次指定导出，则链接器将不会发出警告。

例如，.def 文件的以下内容将导致此警告：

```
EXPORTS
   functioname      NONAME
   functioname      @10
```

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 在命令行上指定相同的导出 (通过导出： ) 并在 .def 文件中。

2. 同一导出在 .def 文件中列出了两次，具有不同的属性。
