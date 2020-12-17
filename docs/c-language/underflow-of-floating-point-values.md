---
description: 详细了解：浮点值的下溢
title: 浮点值的下溢
ms.date: 11/04/2016
ms.assetid: 78af8016-643c-47db-b4f1-7f06cb4b243e
ms.openlocfilehash: 3d8ddd665aa33e1c47f9f187f759058501bc5484
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97321292"
---
# <a name="underflow-of-floating-point-values"></a>浮点值的下溢

**ANSI 4.5.1** 对于下溢范围错误，数学函数是否将整数表达式 `errno` 设置为宏 `ERANGE` 的值

浮点下溢不会将表达式 `errno` 设置为 `ERANGE`。 当值接近零且最终下溢时，该值将设置为零。

## <a name="see-also"></a>请参阅

[库函数](../c-language/library-functions.md)
