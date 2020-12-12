---
description: 了解详细信息：多个内联文件
title: 多内联文件
ms.date: 11/04/2016
helpviewer_keywords:
- inline files, multiple NMAKE
- multiple inline files
- NMAKE program, inline files
ms.assetid: 6d381dcf-0ed8-45d1-8df3-b4598d860b99
ms.openlocfilehash: d739591910007f69eca5d4834f6943ae0a0082ed
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190596"
---
# <a name="multiple-inline-files"></a>多内联文件

命令可创建多个内联文件。

## <a name="syntax"></a>语法

```
command << <<
inlinetext
<<[KEEP | NOKEEP]
inlinetext
<<[KEEP | NOKEEP]
```

## <a name="remarks"></a>备注

对于每个文件，指定一个或多个内联文本行，后跟包含分隔符的结束行。 在第一个文件的分隔行后的行上，开始第二个文件的文本。

## <a name="see-also"></a>请参阅

[生成文件中的内联文件](inline-files-in-a-makefile.md)
