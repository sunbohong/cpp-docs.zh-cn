---
description: 了解更多：编译器错误 C2722
title: 编译器错误 C2722
ms.date: 11/04/2016
f1_keywords:
- C2722
helpviewer_keywords:
- C2722
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
ms.openlocfilehash: 10d1af61f0b82621469f2d6e91d97296c59f22cf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97155587"
---
# <a name="compiler-error-c2722"></a>编译器错误 C2722

"：： operator"：非法的运算符命令;使用 "operator operator"

`operator`语句重定义 `::new` 或 `::delete` 。 `new`和 `delete` 运算符是全局的，因此，范围解析运算符 (`::`) 没有意义。 删除 `::` 运算符。
