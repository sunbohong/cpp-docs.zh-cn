---
description: '详细了解： @ (指定编译器响应文件) '
title: '@（指定编译器响应文件）'
ms.date: 11/04/2016
f1_keywords:
- '@'
helpviewer_keywords:
- response files, C/C++ compiler
- '@ compiler option'
- cl.exe compiler, specifying response files
ms.assetid: 400fffee-909d-4f60-bf76-45833e822685
ms.openlocfilehash: bd2859f7973723d93594693902e92ac3530d73ff
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182887"
---
# <a name="-specify-a-compiler-response-file"></a>@（指定编译器响应文件）

指定编译器响应文件。

## <a name="syntax"></a>语法

> **\@**<em>response_file</em>

## <a name="arguments"></a>参数

*response_file*<br/>
包含编译器命令的文本文件。

## <a name="remarks"></a>备注

响应文件可以包含你将在命令行上指定的任何命令。 如果命令行自变量超过 127 个字符，这可能很有用。

不能 **\@** 从响应文件中指定选项。 也就是说，响应文件不能嵌入其他响应文件。

在命令行中，可以指定任意多个响应文件选项 (例如， `@respfile.1 @respfile.2` 按所需) 。

### <a name="to-set-this-compiler-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此编译器选项

- 无法从开发环境中指定响应文件，必须在命令行中指定响应文件。

### <a name="to-set-this-compiler-option-programmatically"></a>以编程方式设置此编译器选项

- 不能以编程方式更改此编译器选项。

## <a name="see-also"></a>请参阅

[MSVC 编译器选项](compiler-options.md)<br/>
[MSVC 编译器 Command-Line 语法](compiler-command-line-syntax.md)
