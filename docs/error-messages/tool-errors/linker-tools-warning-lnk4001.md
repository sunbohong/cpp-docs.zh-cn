---
description: 了解详细信息：链接器工具警告 LNK4001
title: 链接器工具警告 LNK4001
ms.date: 11/04/2016
f1_keywords:
- LNK4001
helpviewer_keywords:
- LNK4001
ms.assetid: 0a8b1c3a-64ce-4311-b7c0-065995059246
ms.openlocfilehash: ceae4b205a7d591eff6de6c745fc379d5422a0e0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97332036"
---
# <a name="linker-tools-warning-lnk4001"></a>链接器工具警告 LNK4001

未指定对象文件;使用的库

链接器传递了一个或多个 .lib 文件，但没有 .obj 文件。

由于链接器无法访问其能够在 .obj 文件中访问的 .lib 文件中的信息，因此此警告表明您必须显式指定其他链接器选项。 例如，你可能需要指定 [/MACHINE](../../build/reference/machine-specify-target-platform.md)、 [/out](../../build/reference/out-output-file-name.md)或 [/ENTRY](../../build/reference/entry-entry-point-symbol.md) 选项。
