---
description: 详细了解 pragma Microsoft c/c + + 中的 push_macro 指令
title: push_macro pragma
ms.date: 01/22/2021
f1_keywords:
- vc-pragma.push_macro
- push_macro_CPP
helpviewer_keywords:
- pragma, push_macro
- push_macro pragma
no-loc:
- pragma
ms.openlocfilehash: cb97adcb5ce9c0e46a31a9f4926770d4edd658a1
ms.sourcegitcommit: a26a66a3cf479e0e827d549a9b850fad99b108d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "98713293"
---
# <a name="push_macro-no-locpragma"></a>`push_macro` pragma

将 *宏名称* 宏的值保存在此宏的堆栈顶部。

## <a name="syntax"></a>语法

> **`#pragma push_macro("`**_宏名_**`")`**

## <a name="remarks"></a>注解

可以通过检索的 *宏名* 的值 `pop_macro` 。

有关[ `pop_macro` pragma ](../preprocessor/pop-macro.md)示例，请参阅。

## <a name="see-also"></a>另请参阅

[杂注指令和 `__pragma` 和 `_Pragma` 关键字](./pragma-directives-and-the-pragma-keyword.md)
