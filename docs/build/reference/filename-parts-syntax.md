---
description: 了解详细信息： Filename-Parts 语法
title: 文件名部分语法
ms.date: 11/04/2016
helpviewer_keywords:
- syntax, filename-parts
- filename-parts syntax in NMAKE
- NMAKE program, syntax
ms.assetid: 48fe38e0-3f3b-40e6-894c-330ee775a656
ms.openlocfilehash: 436481d52324b4c638b5fa0a9840ce0d9ef654f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192130"
---
# <a name="filename-parts-syntax"></a>文件名部分语法

命令中的文件名部分语法表示第一个依赖文件名的组件 (这可能是隐含的依赖) 。 Filename 组件是指定的文件的驱动器、路径、基名称和扩展名，而不是磁盘上存在的。 使用 **% s** 表示完整的文件名。 使用 **% &#124;**[*part*]**F** (在百分号符号后跟一个竖线) ，以表示文件名的各个部分，其中， *部件* 可以按任意顺序以零个或更多的字母表示。

|Letter|描述|
|------------|-----------------|
|无字母|与 **% s**)  (的完整名称|
|**d**|驱动器|
|**h-p**|路径|
|**f**|文件基名称|
|**e**|文件扩展名|

例如，如果文件名为 c:\prog.exe：

- % s 将 c:\prog.exe

- % &#124;F 将 c:\prog.exe

- % &#124;dF 将为 c

- % &#124;pF 将为 c：\

- % &#124;fF 将是进程

- % &#124;eF 将为 exe

## <a name="see-also"></a>请参阅

[生成文件中的命令](commands-in-a-makefile.md)
