---
description: 详细了解：检查内存改写
title: 检查内存改写
ms.date: 11/04/2016
helpviewer_keywords:
- memory, overwrites
ms.assetid: da7c5d77-a267-415f-a8ab-ee5ce5bfc286
ms.openlocfilehash: 53361a6aea3de54017be3c966f9500accd21ced1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97163166"
---
# <a name="checking-for-memory-overwrites"></a>检查内存改写

如果在调用堆操作函数时出现访问冲突，则可能是程序损坏了堆。 这种情况的一个常见症状是：

```
Access Violation in _searchseg
```

[_heapchk](../c-runtime-library/reference/heapchk.md) 函数可在调试和发布版本（仅 Windows NT）中用于验证运行时库堆的完整性。 可以按照与 `AfxCheckMemory` 函数大致相同的方式来使用 `_heapchk` 隔离堆覆盖，例如：

```
if(_heapchk()!=_HEAPOK)
   DebugBreak();
```

如果此函数失败，则需要隔离堆损坏的位置。

## <a name="see-also"></a>请参阅

[修复发行版本问题](fixing-release-build-problems.md)
