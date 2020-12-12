---
description: 了解详细信息：/STACK
title: /STACK
ms.date: 11/04/2016
f1_keywords:
- /stack_editbin
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
ms.openlocfilehash: 253aec1d760a85f1ebe5dbf7596353b46744cd57
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224447"
---
# <a name="stack"></a>/STACK

```
/STACK:reserve[,commit]
```

## <a name="remarks"></a>备注

此选项设置堆栈的大小（以字节为单位），并以十进制或 C 语言表示法取参数。 /STACK 选项仅适用于可执行文件。

*Reserve* 参数指定虚拟内存中的总堆栈分配。 EDITBIN 将指定的值舍入为最接近的4个字节。

可选 `commit` 参数受操作系统的解释。 在 Windows NT、Windows 95 和 Windows 98 中， `commit` 指定一次分配的物理内存量。 已提交的虚拟内存会导致在页面文件中保留空间。 `commit`当应用程序需要更多堆栈空间时，较高的值可节省时间，但会增加内存需求和可能的启动时间。

## <a name="see-also"></a>请参阅

[EDITBIN 选项](editbin-options.md)
