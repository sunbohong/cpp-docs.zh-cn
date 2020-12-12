---
description: 了解详细信息： Batch-Mode 规则
title: 批模式规则
ms.date: 11/04/2016
helpviewer_keywords:
- inference rules in NMAKE
- NMAKE program, inference rules
- batch-mode inference rules in NMAKE
ms.assetid: 0650b547-ef19-4455-9bba-fa567dcf88f2
ms.openlocfilehash: 73439082b4e2ad8e33b104329d861ddd1919ec63
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182731"
---
# <a name="batch-mode-rules"></a>批模式规则

```
{frompath}.fromext{topath}.toext::
   commands
```

当 N 个命令通过此推理规则时，批处理模式推理规则仅提供一次推理规则调用。 如果没有批处理模式推理规则，则需要调用 N 个命令。 N 是触发推理规则的依赖项的数目。

包含批处理模式推理规则的生成程序必须使用 NMAKE 版本1.62 或更高版本。 若要检查 NMAKE 版本，请运行适用于 NMAKE 版本1.62 或更高版本的 _NMAKE_VER 宏。 此宏返回一个字符串，该字符串表示 Visual C++ 产品版本。

与标准推理规则唯一的语法差别在于，批处理模式推理规则以双冒号 (：： ) 终止。

> [!NOTE]
> 正在调用的工具必须能够处理多个文件。 批处理模式推理规则必须使用 `$<` 作为宏来访问依赖文件。

批处理模式推理规则可以加速生成过程。 由于编译器驱动程序只调用一次，因此可以更快地将文件提供给编译器。 例如，C 和 c + + 编译器在处理一组文件时的性能更好，因为它可以在进程中保留内存。

下面的示例演示如何使用批处理模式推理规则：

```
#
# sample makefile to illustrate batch-mode inference rules
#
O = .
S = .
Objs = $O/foo1.obj $O/foo2.obj $O/foo2.obj $O/foo3.obj $O/foo4.obj
CFLAGS = -nologo

all : $(Objs)

!ifdef NOBatch
{$S}.cpp{$O}.obj:
!else
{$S}.cpp{$O}.obj::
!endif
   $(CC) $(CFLAGS) -Fd$O\ -c $<

$(Objs) :

#end of makefile
```

NMAKE 生成以下输出，而不包含批处理模式推理规则：

```
E:\tmp> nmake -f test.mak -a NOBatch=1

Microsoft (R) Program Maintenance Utility   Version 7.00.0000
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.
        cl -nologo -Fd.\ -c .\foo1.cpp
foo1.cpp
        cl -nologo -Fd.\ -c .\foo2.cpp
foo2.cpp
        cl -nologo -Fd.\ -c .\foo3.cpp
foo3.cpp
        cl -nologo -Fd.\ -c .\foo4.cpp
foo4.cpp
```

NMAKE 生成带有批处理模式推理规则的以下结果：

```
E:\tmp> nmake -f test.mak -a

Microsoft (R) Program Maintenance Utility   Version 7.00.0000
Copyright (C) Microsoft Corp 1988-2001. All rights reserved.

        cl -nologo -Fd.\ -c .\foo1.cpp .\foo2.cpp .\foo3.cpp .\foo4.cpp
foo1.cpp
foo2.cpp
foo3.cpp
foo4.cpp
Generating Code...
```

## <a name="see-also"></a>请参阅

[推理规则](inference-rules.md)
