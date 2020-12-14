---
description: 了解详细信息：/PDBPATH
title: /PDBPATH
ms.date: 11/04/2016
f1_keywords:
- /pdbpath
helpviewer_keywords:
- .pdb files, path
- -PDBPATH dumpbin option
- /PDBPATH dumpbin option
- PDBPATH dumpbin option
- PDB files, path
ms.assetid: ccf67dcd-0b23-4250-ad47-06c48acbe82b
ms.openlocfilehash: 41207d7cfce3d72ecb9517d9ad3af8bcd3f901d7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226046"
---
# <a name="pdbpath"></a>/PDBPATH

```
/PDBPATH[:VERBOSE] filename
```

### <a name="parameters"></a>parameters

*filename*<br/>
要查找匹配 .pdb 文件的 .dll 或 .exe 文件的名称。

**：详细**<br/>
 (可选) 报告尝试查找 .pdb 文件的所有目录。

## <a name="remarks"></a>备注

/PDBPATH 将搜索你的计算机，使其与调试器搜索 .pdb 文件的路径相同，并报告哪些（如果有） .pdb 文件与 *filename* 中指定的文件相对应。

使用 Visual Studio 调试程序时，可能会遇到问题，因为调试器正在为正在调试的文件的不同版本使用 .pdb 文件。

/PDBPATH 将搜索如下路径中的 .pdb 文件：

- 检查可执行文件所在的位置。

- 检查写入到可执行文件中的 PDB 的位置。 这通常是链接图像时的位置。

- 查看在 Visual Studio IDE 中配置的搜索路径。

- 检查 _NT_SYMBOL_PATH 和 _NT_ALT_SYMBOL_PATH 环境变量中的路径。

- 签入 Windows 目录。

## <a name="see-also"></a>请参阅

[DUMPBIN 选项](dumpbin-options.md)<br/>
[/PDBALTPATH (使用备用 PDB 路径) ](pdbaltpath-use-alternate-pdb-path.md)
