---
description: 详细了解：函数声明和定义
title: 函数声明和定义
ms.date: 11/04/2016
helpviewer_keywords:
- local declarations
- function definitions, function declarations
- declaring functions, function definitions
- internal declarations
- external declarations
- function prototypes, basics
- external linkage, function declarations
- declaring functions
ms.assetid: 43fd98eb-7441-4473-a5d9-fc88c75577f7
ms.openlocfilehash: 5fa1e5805b3462e58c04ff73bdbcac337c5a75b6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97221938"
---
# <a name="function-declarations-and-definitions"></a>函数声明和定义

函数原型确定了函数的名称、返回类型以及形参的类型和数量。 函数定义包括函数体。

## <a name="remarks"></a>备注

函数声明和变量声明均可出现在函数定义的内部或外部。 函数定义中的所有声明应在“内部”或“局部”级别显示。 所有函数定义之外的声明应在“外部”、“全局”或“文件范围”级别显示。 变量定义（如声明）可在内部级别（在函数定义中）或在外部级别（在所有函数定义外）显示。 函数定义始终会在外部级别显示。 [函数定义](../c-language/c-function-definitions.md)中进一步讨论了函数定义。 [函数原型](../c-language/function-prototypes.md)中介绍了函数原型。

## <a name="see-also"></a>请参阅

[源文件和源程序](../c-language/source-files-and-source-programs.md)
