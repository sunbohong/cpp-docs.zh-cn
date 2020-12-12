---
description: 了解详细信息：编译器警告 (等级 1) C4952
title: 编译器警告（等级 1）C4952
ms.date: 08/27/2018
f1_keywords:
- C4952
helpviewer_keywords:
- C4952
ms.assetid: 593324f0-5cfe-42fb-b221-2f71308765dd
ms.openlocfilehash: afbc12f6e4e8219c541acd846a3752a331abe827
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97327956"
---
# <a name="compiler-warning-level-1-c4952"></a>编译器警告（等级 1）C4952

> "*function*"：在程序数据库 "*pgd_file*" 中找不到配置文件数据

当使用 [/LTCG:PGUPDATE](../../build/reference/ltcg-link-time-code-generation.md)时，编译器检测到一个在 `/LTCG:PGINSTRUMENT` 后被重新编译且具有一个新的函数 (*function*) 存在的输入模块。

此警告为信息性。 若要解决此警告，请运行 `/LTCG:PGINSTRUMENT`，重做所有测试，并运行 `/LTCG:PGOPTIMIZE`。

如果已使用 `/LTCG:PGOPTIMIZE` ，此警告将替换为一个错误。
