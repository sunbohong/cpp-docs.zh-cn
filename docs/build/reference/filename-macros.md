---
description: 了解详细信息：文件名宏
title: 文件名宏
ms.date: 11/04/2016
helpviewer_keywords:
- macros, NMAKE
- filename macros in NMAKE
- NMAKE program, filename macros
ms.assetid: 20afd6b3-5b6c-4e33-9d01-309ce98ef9db
ms.openlocfilehash: 2b10d021d27eedf008a143472715ee8e0cbecde5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200567"
---
# <a name="filename-macros"></a>文件名宏

Filename 宏预定义为依赖项中指定的文件名 (磁盘) 上的文件的完整文件名规范。 调用时，这些宏无需括在括号中;仅指定 $，如下所示。

|宏|含义|
|-----------|-------------|
|**$\@**|当前目标的全名 (路径，基名称，扩展) ，当前指定的名称相同。|
|**$$\@**|当前目标的全名 (路径，基名称，扩展) ，当前指定的名称相同。 仅在依赖项中作为依赖项有效。|
|**$&#42;**|当前目标的路径和基名称减去文件扩展名。|
|**$&#42;&#42;**|当前目标的所有从属项。|
|**$?**|所有依赖项的时间戳晚于当前目标。|
|**$<**|时间戳比当前目标晚的依赖文件。 仅对推理规则中的命令有效。|

若要指定部分预定义文件名宏，请追加宏修饰符，并将修改后的宏括在括号中。

|修饰符|结果文件名部分|
|--------------|-----------------------------|
|**D**|驱动器和目录|
|**B**|基名称|
|**F**|基名称加扩展|
|**R**|驱动器和目录加基名称|

## <a name="see-also"></a>请参阅

[特殊 NMAKE 宏](special-nmake-macros.md)
