---
description: 了解更多：文件特性常量
title: 文件特性常量
ms.date: 11/04/2016
f1_keywords:
- A_HIDDEN
- _A_NORMAL
- _A_SUBDIR
- _A_RDONLY
- A_NORMAL
- A_SUBDIR
- _A_SYSTEM
- c.constants.file
- _A_HIDDEN
- A_RDONLY
- _A_ARCH
- A_ARCH
helpviewer_keywords:
- constants [C++], file attributes
- file attribute constants [C++]
- _A_SYSTEM constant
- files [C++], file attribute constants
- _A_SUBDIR constant
- _A_ARCH constant
- _A_NORMAL constant
- _A_HIDDEN constant
- _A_RDONLY constant
ms.assetid: 8dc8ccb9-99f5-446b-876c-7ebecc2f764f
ms.openlocfilehash: 8b57549b4a21cc5d699f933009c575b3f3fca81d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97306360"
---
# <a name="file-attribute-constants"></a>文件特性常量

## <a name="syntax"></a>语法

```
#include <io.h>
```

## <a name="remarks"></a>备注

这些常量指定由函数指定的文件或目录的当前特性。

特性可以通过以下清单常量表示：

|返回的常量|描述|
|-|-|
|`_A_ARCH`| 存档。 每当通过 BACKUP 命令更改或清除文件时进行设置。 值：0x20|
|`_A_HIDDEN`| 隐藏文件。 使用 DIR 命令时通常不可见，除非使用 /AH 选项。 返回常规文件和具有此特性的文件的相关信息。 值：0x02|
|`_A_NORMAL`| 正常。 可以不受限制地读取或写入的文件。 值：0x00|
|`_A_RDONLY`| 只读。 无法打开文件进行写入且无法创建具有相同名称的文件。 值：0x01|
|`_A_SUBDIR`| 子目录。 值：0x10|
|`_A_SYSTEM`| 系统文件。 使用 DIR 命令时通常不可见，除非使用 /AS 选项。 值：0x04|

可以使用 OR 运算符 (&#124;) 组合多个常量。

## <a name="see-also"></a>请参阅

[文件名搜索函数](../c-runtime-library/filename-search-functions.md)<br/>
[全局常量](../c-runtime-library/global-constants.md)
