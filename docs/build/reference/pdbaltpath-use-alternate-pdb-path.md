---
description: '了解详细信息：/PDBALTPATH (使用备用 PDB 路径) '
title: /PDBALTPATH（使用备用 PDB 路径）
ms.date: 11/04/2016
f1_keywords:
- /pdbaltpath
helpviewer_keywords:
- .pdb files, path
- PDBALTPATH dumpbin option
- -PDBALTPATH dumpbin option
- /PDBALTPATH dumpbin option
- PDB files, path
ms.assetid: 72e200aa-e2c3-4ad8-b687-25528da1aaaf
ms.openlocfilehash: f85a39fb4570773f01a98331e746f6b37b76c161
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226059"
---
# <a name="pdbaltpath-use-alternate-pdb-path"></a>/PDBALTPATH（使用备用 PDB 路径）

```
/PDBALTPATH:pdb_file_name
```

## <a name="arguments"></a>参数

*pdb_file_name*<br/>
.pdb 文件的路径和文件名。

## <a name="remarks"></a>备注

使用此选项可以在已编译二进制文件中为程序数据库 (.pdb) 文件提供一个备用位置。 通常，链接器将 .pdb 文件的位置记录到它所生成的二进制文件中。 使用此选项可以为 .pdb 文件提供另一个路径和文件名。 /PDBALTPATH 提供的信息不会更改实际 .pdb 文件的位置或名称；它更改链接器写入二进制文件中的信息。 这样，你可以提供一个独立于生成计算机的文件结构的路径。 此选项的两个常见用途是提供网络路径或不包含路径信息的文件。

*Pdb_file_name* 的值可以是任意字符串、环境变量或 **% _PDB%**。 链接器会将环境变量（如 **% SystemRoot%**）展开为其值。 链接器定义环境变量 **% _PDB%** 和 **% _EXT%**。 **% _PDB%** 展开为实际 .pdb 文件的文件名，而不包含任何路径信息， **% _EXT%** 是生成的可执行文件的扩展名。

## <a name="see-also"></a>请参阅

[DUMPBIN 选项](dumpbin-options.md)<br/>
[/PDBPATH](pdbpath.md)
