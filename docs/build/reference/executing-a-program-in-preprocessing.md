---
description: 了解详细信息：在预处理中执行程序
title: 在预处理中执行程序
ms.date: 11/04/2016
helpviewer_keywords:
- program execution [C++]
ms.assetid: 5ecf123a-20e5-40cd-b8d8-dd5a9fdd4b24
ms.openlocfilehash: 72743fe1b75e170ce1aa7ea04dd5a0c70440de59
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97192364"
---
# <a name="executing-a-program-in-preprocessing"></a>在预处理中执行程序

若要在预处理期间使用命令的退出代码，请在方括号 ( [] ) 中指定命令，其中包含任何参数。 执行命令前，将展开任何宏。 NMAKE 将命令规范替换为命令的退出代码，该代码可在表达式中用于控制预处理。

## <a name="see-also"></a>请参阅

[生成文件预处理中的表达式](expressions-in-makefile-preprocessing.md)
