---
description: 了解详细信息：。.Ilk 文件作为链接器输入
title: 用作链接器输入的 .Ilk 文件
ms.date: 11/04/2016
helpviewer_keywords:
- ILK files
- .ilk files
ms.assetid: 7324c104-9e5d-423d-b268-b59f92607bf2
ms.openlocfilehash: 0aaa5fac19cedb8d94fc6dc9ab03a0f23fa0e49b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192728"
---
# <a name="ilk-files-as-linker-input"></a>用作链接器输入的 .Ilk 文件

增量链接时，LINK 将更新在第一个增量链接期间创建的 .ilk 状态文件。 此文件与 .exe 文件或 .dll 文件具有相同的基名称，并且具有扩展名 .ilk。 在后续的增量链接期间，LINK 将更新 .ilk 文件。 如果缺少 .ilk 文件，则 LINK 执行完全链接并创建新的 .ilk 文件。 如果 .ilk 文件不可用，LINK 将执行非增量链接。 有关增量链接的详细信息，请参阅 [/INCREMENTAL) 选项 (增量链接 ](incremental-link-incrementally.md) 。

## <a name="see-also"></a>请参阅

[链接输入文件](link-input-files.md)<br/>
[MSVC 链接器选项](linker-options.md)
