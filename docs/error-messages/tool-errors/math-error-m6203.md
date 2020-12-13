---
description: 了解详细信息：数学错误 M6203
title: 数学错误 M6203
ms.date: 11/04/2016
f1_keywords:
- M6203
helpviewer_keywords:
- M6203
ms.assetid: bd7fdd1c-83e4-4d6a-901e-10a0308bf5be
ms.openlocfilehash: fcb123af8c79b5ce839e13247f59cbbed42736f4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97143866"
---
# <a name="math-error-m6203"></a>数学错误 M6203

"function"： _OVERFLOW 错误

给定函数的结果太大，无法表示。

此错误将调用函数 `_matherr` ，其函数名称、参数的参数和错误类型。 您可以重写此 `_matherr` 函数，以自定义对某些运行时浮点算术错误的处理。
