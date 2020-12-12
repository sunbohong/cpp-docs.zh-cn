---
description: 了解详细信息：生成文件中的注释
title: 生成文件中的注释
ms.date: 11/04/2016
helpviewer_keywords:
- makefiles, comments
ms.assetid: 76fd9e3d-5966-47f4-a091-c9e80b232b49
ms.openlocfilehash: 9edee594c0299d8e93928c1284b7244af71f61e1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182289"
---
# <a name="comments-in-a-makefile"></a>生成文件中的注释

在注释前面加上数字符号 ( # ) 。 NMAKE 忽略数字符号中的文本到下一个换行符。 示例：

```
# Comment on line by itself
OPTIONS = /MAP  # Comment on macro definition line

all.exe : one.obj two.obj  # Comment on dependency line
    link one.obj two.obj
# Comment in commands block
#   copy *.obj \objects  # Command turned into comment
    copy one.exe \release

.obj.exe:  # Comment on inference rule line
    link $<

my.exe : my.obj ; link my.obj  # Err: cannot comment this
# Error: # must be the first character
.obj.exe: ; link $<  # Error: cannot comment this
```

若要指定文本数字符号，请在其前面加上一个插入符号 (**^**) ，如下所示：

```
DEF = ^#define  #Macro for a C preprocessing directive
```

## <a name="see-also"></a>请参阅

[生成文件的内容](contents-of-a-makefile.md)
