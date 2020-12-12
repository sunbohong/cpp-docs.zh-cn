---
description: 了解详细信息： BSCMAKE 如何生成。.Bsc 文件
title: BSCMAKE 如何生成 .Bsc 文件
ms.date: 11/04/2016
helpviewer_keywords:
- browse information files (.bsc), building
ms.assetid: 8512b33e-c856-44a2-87bd-01ab10b52a95
ms.openlocfilehash: 6d468f365f7f42be2eb393e53d72053b682ec65a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97191376"
---
# <a name="how-bscmake-builds-a-bsc-file"></a>BSCMAKE 如何生成 .Bsc 文件

BSCMAKE 以最有效的方式生成或重新生成 .bsc 文件。 若要避免潜在的问题，请务必了解构建过程。

当 BSCMAKE 生成浏览信息文件时，它会将 .sbr 文件截断为零长度。 在同一文件的后续生成过程中，零长度 (或空) .sbr 文件会告知 BSCMAKE 文件没有要生成的新内容。 它使 BSCMAKE 知道，不需要更新该文件的该部分，而增量生成就足够了。 在每个生成 (，除非) 指定/n 选项，否则 BSCMAKE 首先尝试仅使用已更改的 .sbr 文件来增量更新文件。

BSCMAKE 查找 .bsc 文件，该文件具有使用/o 选项指定的名称。 如果未指定/o，则 BSCMAKE 将查找一个文件，其中包含第一个 .sbr 文件的基名称和一个 .bsc 扩展名。 如果该文件存在，则 BSCMAKE 只使用生成的 .sbr 文件来执行浏览信息文件的增量生成。 如果该文件不存在，则 BSCMAKE 使用所有 .sbr 文件执行完整生成。 生成的规则如下所示：

- 若要使完整生成成功，所有指定的 .sbr 文件必须存在，并且不能被截断。 如果 .sbr 文件被截断，则必须在运行 BSCMAKE 之前重新编译或汇编)  (重新生成它。

- 若要使增量生成成功，.bsc 文件必须存在。 所有构成 .sbr 文件（甚至是空文件）都必须存在，并且必须在 BSCMAKE 命令行上指定。 如果省略命令行中的 .sbr 文件，则 BSCMAKE 会将其内容从文件中删除。

## <a name="see-also"></a>请参阅

[生成。.Bsc 文件](building-a-dot-bsc-file.md)
