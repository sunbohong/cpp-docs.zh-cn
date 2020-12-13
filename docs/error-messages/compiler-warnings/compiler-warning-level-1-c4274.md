---
description: 了解详细信息：编译器警告 (等级 1) C4274
title: 编译器警告 (等级 1) C4274
ms.date: 11/04/2016
f1_keywords:
- C4274
helpviewer_keywords:
- C4274
ms.assetid: 5a948680-7ed1-469f-978d-ae99d154e161
ms.openlocfilehash: aa1f6d3b07c7d788d9e47955c4bb51930522b7a3
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97340094"
---
# <a name="compiler-warning-level-1-c4274"></a>编译器警告 (等级 1) C4274

\#已忽略 ident;请参阅 #pragma 注释的文档 " (exestr" 的 "string" ) 

`#ident`已弃用在对象或可执行文件中插入用户指定字符串的指令。 因此，编译器将忽略指令。

> [!CAUTION]
> 警告 C4274 建议你使用 [ (exestr，' string ' ) 指令的 #pragma 注释 ](../../preprocessor/comment-c-cpp.md) 。 但是，此建议已弃用，并将在编译器的未来版本中进行修改。 如果使用 `#pragma` 指令，链接器工具 ( # A0) 忽略指令生成的注释记录，并发出警告 [LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)。 `#ident`建议你在应用程序中使用文件版本资源字符串，而不是指令。

## <a name="to-correct-this-error"></a>更正此错误

- 删除 `#ident "` *string* `"` 指令。

## <a name="see-also"></a>请参阅

[注释 (C/C++)](../../preprocessor/comment-c-cpp.md)<br/>
[链接器工具警告 LNK4229](../../error-messages/tool-errors/linker-tools-warning-lnk4229.md)<br/>
[使用资源文件](../../windows/working-with-resource-files.md)
