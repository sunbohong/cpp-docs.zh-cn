---
description: 了解更多：命令修饰符
title: 命令修饰符
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, command modifiers
- command modifiers
ms.assetid: b661c432-210f-4f05-bc56-744a46e0fc0b
ms.openlocfilehash: d17d5f25719dfe5638ca6688105517d385bdf68e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182367"
---
# <a name="command-modifiers"></a>命令修饰符

可以在命令前面指定一个或多个命令修饰符，还可以选择用空格或制表符分隔。 与命令一样，修饰符必须缩进。

|修饰符|目标|
|--------------|-------------|
|\@*command*|禁止显示命令。 不会禁止显示按命令。 默认情况下，NMAKE 回显所有已执行的命令。 使用/S 禁止显示整个生成文件;使用 **。无提示** ，禁止显示部分生成文件。|
|**-**\[*number*] *命令*|关闭 *命令* 的错误检查。 默认情况下，当命令返回非零退出代码时，NMAKE 将暂停。 如果使用-*number* ，则如果退出代码超出了 *数字*，NMAKE 将停止。 空格或制表符不能出现在短划线和 *数字之间。* 和命令之间必须至少出现一个空格或 `number` 制表符。 使用/I 为整个生成文件禁用错误检查;使用 **。"忽略** " 关闭部分生成文件的错误检查。|
|**!** *command*|如果 *命令* <strong>$\*\*</strong> (使用依赖项) 中的所有依赖文件或 **$？**  (依赖项中的所有依赖文件，其时间戳晚于目标) 。|

## <a name="see-also"></a>请参阅

[生成文件中的命令](commands-in-a-makefile.md)
