---
description: 了解详细信息：使用导入库和导出文件
title: 使用导入库和导出文件
ms.date: 11/04/2016
helpviewer_keywords:
- circular exports
- import libraries, using
- export files
ms.assetid: 2634256a-8aa5-4495-8c9e-6cde10e4ed76
ms.openlocfilehash: f42a98ebe19cb32fb77964f26c37928776b5b30c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97247015"
---
# <a name="using-an-import-library-and-export-file"></a>使用导入库和导出文件

当程序 (可执行文件或 DLL) 导出到它也从其导入的另一个程序时，或者如果两个以上的程序都导出到另一个程序并从中导入，则用于链接这些程序的命令必须适应循环导出。

在没有循环导出的情况下，当链接使用其他程序的导出的程序时，必须指定导出程序的导入库。 当你链接该导出程序时，将创建导出程序的导入库。 因此，您必须在导入程序之前链接导出程序。 例如，如果从 ONE.dll TWO.dll 导入，则必须首先链接 ONE.dll 并将导入库导入。 然后，在链接 TWO.dll 时指定一个 .lib。 当链接器创建 TWO.dll 时，它还会创建它的导入库。 在链接从 TWO.dll 导入的程序时，请使用两个 .lib。

但是，在循环导出情况下，不能使用其他程序中的 "导入库" 链接所有相互依赖的程序。 在前面所述的示例中，如果 TWO.dll 也导出到 ONE.dll，则在 ONE.dll 链接时，TWO.dll 的导入库仍不存在。 存在循环导出时，必须使用 LIB 为某个程序创建导入库和导出文件。

若要开始，请选择要在其中运行 LIB 的程序之一。 在 LIB 命令中，列出程序的所有对象和库，并指定/DEF。 如果程序使用 .def 文件或/EXPORT 规范，还应指定这些规范。

创建 ( .lib) 和该程序的导出文件 ( .exp) 后，在链接其他程序或程序时使用导入库。 LINK 为生成的每个导出程序创建导入库。 例如，如果在 ONE.dll 的对象和导出上运行 LIB，则创建一个 .lib 和一个 .exp。你现在可以在链接时使用一个 .lib TWO.dll;此步骤还创建了两个导入库。

最后，链接开始的程序。 在 "链接" 命令中，指定程序的对象和库、LIB 为程序创建的 .exp 文件以及该程序使用的导出的导入库。 若要继续此示例，ONE.dll 的链接命令包含一个 .exp 和两个 .lib 以及进入 ONE.dll 的对象和库。 请勿在 LINK 命令中指定 .def 文件或/EXPORT 规范;这不是必需的，因为导出定义包含在 .exp 文件中。 使用 .exp 文件进行链接时，LINK 不会创建导入库，因为它假定创建 .exp 文件时创建了一个导入库。

## <a name="see-also"></a>请参阅

[使用导入库和导出文件](working-with-import-libraries-and-export-files.md)
