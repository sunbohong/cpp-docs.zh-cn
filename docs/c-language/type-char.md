---
description: 详细了解：char 类型
title: char 类型
ms.date: 11/04/2016
helpviewer_keywords:
- type char
- unsigned char keyword [C]
- char keyword [C]
ms.assetid: a5da0866-e780-4793-be87-15a8426e7ea0
ms.openlocfilehash: 187f0ca5f70f6743f52ae62dc2c14d04b78ca63e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97242894"
---
# <a name="type-char"></a>char 类型

`char` 类型用于存储可表示的字符集的成员的整数值。 该整数值是与指定字符对应的 ASCII 代码。

**Microsoft 专用**

类型 `unsigned char` 的字符值介于 0 和 0xFF（十六进制）范围之间。 `signed char` 介于 0x80 和 0x7F 范围之间。 这些范围分别转换为 0 到 255（十进制）以及 -128 到 +127（十进制）。 /J 编译器选项将默认值从 `signed` 更改为 `unsigned`。

**结束 Microsoft 专用**

## <a name="see-also"></a>请参阅

[基本类型的存储](../c-language/storage-of-basic-types.md)
