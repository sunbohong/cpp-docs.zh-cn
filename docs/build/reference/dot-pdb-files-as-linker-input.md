---
description: 了解详细信息：。作为链接器输入的 Pdb 文件
title: 用作链接器输入的 .Pdb 文件
ms.date: 11/04/2016
helpviewer_keywords:
- .pdb files, as linker input
- PDB files, as linker input
ms.assetid: c1071478-2369-4b03-9df8-71761cf82f3b
ms.openlocfilehash: 713d42e7e95b5d1e7e3b1f9be21203b75569cdbe
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97201152"
---
# <a name="pdb-files-as-linker-input"></a>用作链接器输入的 .Pdb 文件

使用/Zi 选项编译的对象 () 文件包含程序数据库 (PDB) 的名称。 不要将对象的 PDB 文件名指定给链接器;如果需要，LINK 使用嵌入名称查找 PDB。 这也适用于库中包含的可调试对象;可调试库的 PDB 必须与库一起提供给链接器。

LINK 还使用 PDB 保存 .exe 文件或 .dll 文件的调试信息。 该程序的 PDB 既是一个输出文件又是一个输入文件，因为在重新生成程序时，LINK 更新了 PDB。

## <a name="see-also"></a>请参阅

[链接输入文件](link-input-files.md)<br/>
[MSVC 链接器选项](linker-options.md)
