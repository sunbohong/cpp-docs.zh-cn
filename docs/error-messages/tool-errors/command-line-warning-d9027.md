---
description: 了解详细信息： Command-Line 警告 D9027
title: 命令行警告 D9027
ms.date: 11/04/2016
f1_keywords:
- D9027
helpviewer_keywords:
- D9027
ms.assetid: 2a29edc5-5649-48f2-9058-2057c747284c
ms.openlocfilehash: 8c17750f3310072f8f69c77587a1c17fc9377e79
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97136105"
---
# <a name="command-line-warning-d9027"></a>命令行警告 D9027

已忽略源文件 " \<filename> "

CL.exe 忽略输入源文件。

此警告可能由使用/c 选项的命令行上的/Fo 选项和输出文件名之间的空格引起。 例如：

```
cl /c /Fo output.obj input.c
```

由于/Fo 与之间有一个空格 `output.obj` ，因此 CL.exe 将 `output.obj` 作为输入文件的名称。 若要解决此问题，请删除以下空间：

```
cl /c /Fooutput.obj input.c
```
