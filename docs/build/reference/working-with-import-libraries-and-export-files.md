---
description: 了解更多相关信息：使用导入库和导出文件
title: 使用导入库和导出文件
ms.date: 11/04/2016
helpviewer_keywords:
- LIB [C++], /DEF option
- import libraries
- LIB [C++], import libraries and export files
- export files
- import libraries, creating
ms.assetid: d8175596-9773-4c2f-959d-b05b065a5161
ms.openlocfilehash: b6e1664aedf5fa87d269e0ff250e6c52d9d18259
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258793"
---
# <a name="working-with-import-libraries-and-export-files"></a>使用导入库和导出文件

可以通过/DEF 选项使用 LIB 来创建导入库和导出文件。 LINK 使用导出文件生成一个程序，该程序包含导出 (通常为动态链接库 (DLL) # A3，并使用导入库来解析其他程序中对这些导出的引用。

请注意，如果在初步步骤中创建了导入库，则在创建 .dll 之前，必须在生成 .dll 时传递相同的对象文件集，就像生成导入库时传递的一样。

在大多数情况下，不需要使用 LIB 来创建导入库。 将程序链接 (可执行文件或包含导出的 DLL) 时，LINK 会自动创建一个描述导出的导入库。 稍后，在链接引用这些导出的程序时，可以指定导入库。

但是，当 DLL 导出到它也从其导入的程序时（无论是直接还是间接），都必须使用 LIB 创建一个导入库。 当 LIB 创建导入库时，它还会创建一个导出文件。 在链接其中一个 Dll 时，必须使用导出文件。

## <a name="see-also"></a>请参阅

[LIB 引用](lib-reference.md)
