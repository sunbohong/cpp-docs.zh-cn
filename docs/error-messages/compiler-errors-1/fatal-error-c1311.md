---
description: 了解详细信息：严重错误 C1311
title: 错误 C1311
ms.date: 11/04/2016
f1_keywords:
- C1311
helpviewer_keywords:
- C1311
ms.assetid: 6590a06c-ce9d-4f17-8f62-c809343143b8
ms.openlocfilehash: d6049bfedd01be02e8b3f26163fe062e9023bd78
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97177739"
---
# <a name="fatal-error-c1311"></a>错误 C1311

COFF 格式无法以静态方式初始化使用) 地址的数字字节 (的 "var"

在编译时，值未知的地址不能静态分配给类型的变量，其类型的存储小于四个字节。

如果代码是有效的 c + +，则可能出现此错误。

以下示例显示了可能导致 C1311 的一种情况。

```
char c = (char)"Hello, world";   // C1311
char *d = (char*)"Hello, world";   // OK
```
