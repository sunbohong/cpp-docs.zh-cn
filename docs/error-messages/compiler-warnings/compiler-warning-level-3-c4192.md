---
description: 详细了解：编译器警告 (等级 3) C4192
title: 编译器警告 (等级 3) C4192
ms.date: 11/04/2016
f1_keywords:
- C4192
helpviewer_keywords:
- C4192
ms.assetid: ea5f91fa-8c96-4f3f-ac42-0c8a86d4e5df
ms.openlocfilehash: 8cfebf1845c578723bab5622e18699c0282d4c4b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344219"
---
# <a name="compiler-warning-level-3-c4192"></a>编译器警告 (等级 3) C4192

导入类型库 "库" 时自动排除 "name"

`#import`库包含在 Win32 系统标头中也定义的项 *名称*。 由于类型库的限制，通常在类型库中定义 **IUnknown** 或 GUID 等名称，从系统标头复制定义。 `#import` 将检测这些项，并拒绝将它们合并到 .tlh 和 .tli 标头文件中。

若要重写此行为，请使用 `#import` [no_auto_exclude](../../preprocessor/no-auto-exclude.md) 特性，并 [包括 ( # B1 ](../../preprocessor/include-parens.md)。
