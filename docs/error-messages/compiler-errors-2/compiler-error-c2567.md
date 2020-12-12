---
description: 了解更多：编译器错误 C2567
title: 编译器错误 C2567
ms.date: 11/04/2016
f1_keywords:
- C2567
helpviewer_keywords:
- C2567
ms.assetid: 9c140ac9-7059-47e6-9ba1-e7939c8c0dc3
ms.openlocfilehash: 113dfebc1ac6bde6857ea55fd6249fff12c9faae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97209108"
---
# <a name="compiler-error-c2567"></a>编译器错误 C2567

无法打开 "file" 中的元数据，文件可能已被删除或移动

编译器后端进程在同一目录中未找到使用) 在源 (中引用的元数据文件，该文件与 `#using` 编译器前端进程的情况相同。 有关详细信息，请参阅 [#using 指令](../../preprocessor/hash-using-directive-cpp.md) 。

如果在一台计算机上使用 **/c** 进行编译，然后在另一台计算机上尝试使用链接时间代码生成，则可能导致 C2567。 有关详细信息，请参阅 [/ltcg () ) 的链接时间代码生成 ](../../build/reference/ltcg-link-time-code-generation.md) 。

它也可能表示您的计算机没有更多的内存。

若要更正此错误，请确保元数据文件在生成过程的所有阶段都处于相同的目录位置。
