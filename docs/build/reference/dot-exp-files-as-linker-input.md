---
description: 了解详细信息：。Exp 文件作为链接器输入
title: 用作链接器输入的 .Exp 文件
ms.date: 11/04/2016
helpviewer_keywords:
- exporting functions
- import libraries, linker files
- linking [C++], exports
- exporting functions, information about exported functions
- exporting data, export (.exp) files
- functions [C++], exporting
- .exp files [C++]
- EXP files
ms.assetid: 399f5636-0a4d-462e-b500-5f5b9ae5ad22
ms.openlocfilehash: 03104d6b4265484e54373484b6c9bbdabf0e1afc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192806"
---
# <a name="exp-files-as-linker-input"></a>用作链接器输入的 .Exp 文件

导出 ( .exp) 文件包含有关导出的函数和数据项的信息。 当 LIB 创建导入库时，它还会创建 .exp 文件。 当你链接两个导出的程序并直接或间接从另一个程序导入时，可以使用 .exp 文件。 如果链接到 .exp 文件，LINK 不会生成导入库，因为它假定 LIB 已创建了一个导入库。 有关 .exp 文件和导入库的详细信息，请参阅使用 [导入库和导出文件](working-with-import-libraries-and-export-files.md)。

## <a name="see-also"></a>请参阅

[链接输入文件](link-input-files.md)<br/>
[MSVC 链接器选项](linker-options.md)
