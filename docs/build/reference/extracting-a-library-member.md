---
description: 了解更多：提取库成员
title: 提取库成员
ms.date: 11/04/2016
helpviewer_keywords:
- LIB [C++], extracting library members
- EXTRACT library manager option
- libraries, extracting members
- -EXTRACT library manager option
- extracting library members
- /EXTRACT library manager option
ms.assetid: a2c5c2a1-9b7e-489a-a9a4-1dec694e1fc5
ms.openlocfilehash: 8797db6baa08fc36cf288f5b23d73ff730edd973
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192312"
---
# <a name="extracting-a-library-member"></a>提取库成员

您可以使用 LIB 创建对象 ( .obj) 文件，该对象包含现有库的成员的副本。 若要提取成员的副本，请使用以下语法：

```
LIB library /EXTRACT:member /OUT:objectfile
```

此命令创建名为 *objectfile* 的 .obj 文件，其中包含库的的副本 `member` 。  该 `member` 名称区分大小写。 只能在单个命令中提取一个成员。 /OUT 选项是必需的;没有默认的输出名称。 如果名为 *objectfile* 的文件已存在于指定目录 (或当前目录中，如果未使用 *objectfile*) 指定目录，则提取的 *objectfile* 将替换现有文件。

## <a name="see-also"></a>请参阅

[LIB 引用](lib-reference.md)
