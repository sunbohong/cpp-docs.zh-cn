---
description: 了解详细信息：编译器警告 (等级 1) C4124
title: 编译器警告 (等级 1) C4124
ms.date: 11/04/2016
f1_keywords:
- C4124
helpviewer_keywords:
- C4124
ms.assetid: c08c3a65-9584-47a1-a147-44f00c4b230e
ms.openlocfilehash: 97fe65f8513f656d85059714ae598ffad9f7a49c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97267386"
---
# <a name="compiler-warning-level-1-c4124"></a>编译器警告 (等级 1) C4124

具有堆栈检查的 __fastcall 效率低下

**`__fastcall`** 关键字用于启用堆栈检查。

该 **`__fastcall`** 约定生成更快的代码，但堆栈检查会导致代码较慢。 使用时 **`__fastcall`** ，请使用 **check_stack** 杂注或/Gs. 关闭堆栈检查

仅为在这些条件下声明的第一个函数发出此警告。
