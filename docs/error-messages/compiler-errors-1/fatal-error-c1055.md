---
description: 了解详细信息：严重错误 C1055
title: 错误 C1055
ms.date: 11/04/2016
f1_keywords:
- C1055
helpviewer_keywords:
- C1055
ms.assetid: a9fb9190-d7eb-4d5f-b1a2-a41e584a28c1
ms.openlocfilehash: f85d3bc19b9dcd2ba3f4338e78c55cc7aa549fb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251643"
---
# <a name="fatal-error-c1055"></a>错误 C1055

编译器限制：超出键范围

源文件包含太多符号。 编译器用完了符号表的哈希键。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>使用以下可能的解决方案进行修复

1. 将源文件拆分为较小的文件。

1. 消除不必要的标头文件。

1. 重复使用临时和全局变量，而不是创建新变量。
