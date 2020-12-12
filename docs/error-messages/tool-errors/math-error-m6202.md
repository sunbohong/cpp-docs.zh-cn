---
description: 了解详细信息：数学错误 M6202
title: 数学错误 M6202
ms.date: 11/04/2016
f1_keywords:
- M6202
helpviewer_keywords:
- M6202
ms.assetid: 4d17045f-c6dc-4705-9512-e9af12c35fb4
ms.openlocfilehash: f6d4c9c8abab59708854eaac6763181018f47473
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97244298"
---
# <a name="math-error-m6202"></a>数学错误 M6202

"function"： _SING 错误

给定函数的参数是此函数的奇点值。 未为该参数定义函数。

此错误将调用函数 `_matherr` ，其函数名称、参数的参数和错误类型。 您可以重写此 `_matherr` 函数，以自定义对某些运行时浮点算术错误的处理。
