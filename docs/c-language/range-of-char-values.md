---
description: 详细了解：字符值的范围
title: 字符值的范围
ms.date: 11/04/2016
ms.assetid: 15ae9781-ec21-4333-bba8-6d2383bbf7f1
ms.openlocfilehash: 4897dd2b6433b148ea0c739118dea14f81f1e2bc
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97309155"
---
# <a name="range-of-char-values"></a>字符值的范围

ANSI 3.2.1.1“普通”`char` 的值范围是否与 `signed char` 或 `unsigned char` 相同

所有带符号的字符值的范围都介于 -128 和 127 之间。 所有无符号的字符值的范围介于 0 和 255 之间。

[`/J`](../build/reference/j-default-char-type-is-unsigned.md) 编译器选项将 `char` 的默认类型从 `signed char` 更改为 `unsigned char`。

## <a name="see-also"></a>请参阅

[字符](../c-language/characters.md)
