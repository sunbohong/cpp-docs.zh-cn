---
description: 详细了解 pragma Microsoft c/c + + 中的 auto_inline 指令
title: auto_inline pragma
ms.date: 01/22/2021
f1_keywords:
- auto_inline_CPP
- vc-pragma.auto_inline
helpviewer_keywords:
- pragma, auto_inline
- auto_inline pragma
no-loc:
- pragma
ms.openlocfilehash: 72c6823acf260d48883142f8568483eb78155da1
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713722"
---
# <a name="auto_inline-no-locpragma"></a>`auto_inline` pragma

排除在指定的范围内定义 **`off`** 为自动内联展开候选项的任何函数。

## <a name="syntax"></a>语法

> **`#pragma auto_inline(`** [ { **`on`** | **`off`** } ] **`)`**

## <a name="remarks"></a>注解

若要使用 **`auto_inline`** pragma ，请将它放在函数定义之前和之后（而不是在中）。 一旦出现，就会在 pragma 第一个函数定义之后立即生效 pragma 。

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
