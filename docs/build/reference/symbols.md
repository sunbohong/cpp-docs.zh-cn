---
description: 了解详细信息：/SYMBOLS
title: /SYMBOLS
ms.date: 09/05/2018
f1_keywords:
- /symbols
helpviewer_keywords:
- symbols, dumping
- public symbols
- symbols, displaying COFF symbol table
- symbol tables
- SYMBOLS dumpbin option
- /SYMBOLS dumpbin option
- -SYMBOLS dumpbin option
ms.assetid: 34bcae90-4561-4c77-a80c-065508dec39a
ms.openlocfilehash: f0cc213a8b37f99e0cb80f6df88967e4eb5204b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230141"
---
# <a name="symbols"></a>/SYMBOLS

```
/SYMBOLS
```

此选项显示 COFF 符号表。 符号表存在于所有对象文件中。 仅当 COFF 符号表与/DEBUG 进行链接时，它才会出现在图像文件中。

下面是/SYMBOLS. 的输出的说明 有关/SYMBOLS 输出含义的其他信息，请参阅 winnt (IMAGE_SYMBOL 和 IMAGE_AUX_SYMBOL) 或 COFF 文档。

假设有以下示例转储：

```
Dump of file main.obj
File Type: COFF OBJECT

COFF SYMBOL TABLE
000 00000000 DEBUG    notype       Filename     | .file
    main.cpp
002 000B1FDB ABS      notype       Static       | @comp.id
003 00000000 SECT1    notype       Static       | .drectve
    Section length     26, #relocs    0, #linenums    0, checksum 722C964F
005 00000000 SECT2    notype       Static       | .text
    Section length     23, #relocs    1, #linenums    0, checksum 459FF65F, selection    1 (pick no duplicates)
007 00000000 SECT2    notype ()    External     | _main
008 00000000 UNDEF    notype ()    External     | ?MyDump@@YAXXZ (void __cdecl MyDump(void))

String Table Size = 0x10 bytes

  Summary

         26 .drectve
         23 .text
```

## <a name="remarks"></a>备注

以下说明对于以符号编号开头的行，描述了包含与用户相关的信息的列：

- 前三位数字是符号索引/数字。

- 如果第三列包含段 *x*，则符号在对象文件的该部分中定义。 但如果显示了 UNDEF，则它不会在该对象中定义，并且必须在其他位置进行解析。

- 第五列 (Static、External) 指示该符号是否仅在该对象内可见，或者该符号是否为公共 (外部) 可见。 静态符号 _sym 不会链接到公共符号 _sym;它们是名为 _sym 的两个不同函数实例。

编号行中的最后一列是符号名称，修饰和未修饰。

只有 [/HEADERS](headers.md) DUMPBIN 选项可用于由 [/GL](gl-whole-program-optimization.md) 编译器选项产生的文件。

## <a name="see-also"></a>请参阅

[DUMPBIN 选项](dumpbin-options.md)
