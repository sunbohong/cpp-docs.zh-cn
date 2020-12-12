---
description: 了解更多：资源编译器错误 RC2001
title: 资源编译器错误 RC2001
ms.date: 11/04/2016
f1_keywords:
- RC2001
helpviewer_keywords:
- RC2001
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
ms.openlocfilehash: 101ebb260bcfd24fb74368ca66e1e9d318418367
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97206339"
---
# <a name="resource-compiler-error-rc2001"></a>资源编译器错误 RC2001

常量中有换行符

字符串常量在第二行继续进行，但没有反斜杠 (**\\**) 或右双引号 (**"**) 。

若要中断源文件中两行的字符串常数，请执行下列操作之一：

- 使用行继续符（反斜杠）结束第一行。

- 用双引号结束第一行的字符串，并在下一行中用另一个引号打开字符串。

在字符串常量中嵌入换行符的转义序列不能用 \n 结束第一行。
