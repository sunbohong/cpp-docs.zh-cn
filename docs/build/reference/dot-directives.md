---
description: 了解有关以下方面的详细信息：点指令
title: 点指令
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, dot directives
- dot directives in NMAKE
ms.assetid: ab35da65-30b6-48b7-87d6-61503d7faf9f
ms.openlocfilehash: 41b13d5f0f0f0a04ee47a9958be76c384617fe5f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192858"
---
# <a name="dot-directives"></a>点指令

在描述块外的行首指定点指令。 点指令以句点 ( 开头。 ) 后跟一个冒号 (： ) 。 允许使用空格和制表符。 点指令名称区分大小写，并且为大写字母。

|指令|目标|
|---------------|-------------|
|**.暂且**|忽略由命令返回的非零退出代码，从其指定到生成文件末尾的位置。 默认情况下，如果命令返回非零退出代码，NMAKE 将暂停。 若要还原错误检查，请使用 **！CMDSWITCHES**。 若要忽略单个命令的退出代码，请使用短划线 ( ) 修饰符。 若要忽略整个文件的退出代码，请使用/I|
|**.宝贵：** *目标*|如果要更新的命令已停止，请在磁盘上保留 *目标* ;如果命令通过删除文件来处理中断，则不起作用。 用一个或多个空格或制表符分隔目标名称。 默认情况下，如果生成被 CTRL + C 或 CTRL + BREAK 中断，NMAKE 将删除目标。 的每个使用 **。宝贵** 适用于整个生成文件;多个规范都是累积的。|
|**.自行**|禁止显示已执行命令的显示，从其指定到生成文件末尾的位置。 默认情况下，NMAKE 显示其调用的命令。 若要还原回显，请使用 **！CMDSWITCHES**。 若要取消显示单个命令的回显，请使用 **@** 修饰符。 若要取消整个文件的回显，请使用/S|
|**.后缀：**`list`|列出推理的扩展-规则匹配;预定义为包括以下扩展插件： .cxx. cbl. f. f. f. f. f. f. f90|

更改 **。后缀** 列表顺序或要指定新列表，请清除该列表并指定新设置。 若要清除该列表，请在冒号后面不指定扩展名：

```
.SUFFIXES :
```

若要将其他后缀添加到列表的末尾，请指定

```
.SUFFIXES : suffixlist
```

其中， *suffixlist* 是附加后缀的列表，用一个或多个空格或制表符分隔。 查看的当前设置 **。后缀**，通过/p。运行 NMAKE

## <a name="see-also"></a>请参阅

[NMAKE 参考](nmake-reference.md)
