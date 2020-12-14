---
description: 了解详细信息：指定内联文件
title: 指定内联文件
ms.date: 11/04/2016
helpviewer_keywords:
- NMAKE program, inline files
- inline files [C++], specifying NMAKE
- files [C++], inline
ms.assetid: 393eccfb-3fc9-4bac-a30c-8ac8d221cca3
ms.openlocfilehash: 461bf507f707512aa690e81dc5752a97d0c1c4ce
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224603"
---
# <a name="specifying-an-inline-file"></a>指定内联文件

在命令中指定要在其中显示 *文件名* ( # A2) 的两个尖括号。 尖括号不能是宏扩展。

## <a name="syntax"></a>语法

```
<<[filename]
```

## <a name="remarks"></a>备注

运行该命令时，尖括号由 *filename*（如果指定）替换，或由 NMAKE 生成的唯一名称替换。 如果已指定， *filename* 必须跟在尖括号中，而不带空格或制表符。允许路径。 不需要或采用扩展名。 如果指定 *文件名* ，则将在当前或指定目录中创建文件，并按该名称覆盖任何现有文件;否则，如果未) 定义 TMP 环境变量，则在 TMP 目录 (或当前目录中创建它。 如果重复使用以前的 *文件名* ，NMAKE 将替换上一个文件。

## <a name="see-also"></a>请参阅

[生成文件中的内联文件](inline-files-in-a-makefile.md)
