---
description: 了解详细信息：。Res 文件作为链接器输入
title: 用作链接器输入的 .Res 文件
ms.date: 11/04/2016
helpviewer_keywords:
- RES files as linker input
- .res files as linker input
- linking [C++], resource files
- resource files, linking
ms.assetid: 9c37ab00-97df-4d9a-91cd-6bf132970683
ms.openlocfilehash: 9670e922412f68aef78d64572f8241083ebc74b7
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192702"
---
# <a name="res-files-as-linker-input"></a>用作链接器输入的 .Res 文件

在链接程序时可以指定 res 文件。 Res 文件由资源编译器 (RC) 创建。 LINK 自动将 .res 文件转换为 COFF。 CVTRES.exe 工具必须与 LINK.exe 在同一目录中，或者在 PATH 环境变量中指定的目录中。

## <a name="see-also"></a>请参阅

[链接输入文件](link-input-files.md)<br/>
[MSVC 链接器选项](linker-options.md)
