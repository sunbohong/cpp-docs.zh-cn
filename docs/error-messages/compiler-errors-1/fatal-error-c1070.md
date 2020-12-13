---
description: 了解详细信息：严重错误 C1070
title: 错误 C1070
ms.date: 11/04/2016
f1_keywords:
- C1070
helpviewer_keywords:
- C1070
ms.assetid: 1058269a-5db6-4c23-a97f-b5269eb9188b
ms.openlocfilehash: 2668bfa6c24c602606cbd9ee41b5322272eec093
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344388"
---
# <a name="fatal-error-c1070"></a>错误 C1070

文件“filename”中的 #if/#endif 对不匹配

`#if`、 `#ifdef`或 `#ifndef` 指令没有对应的 `#endif`。

下面的示例生成 C1070：

```cpp
// C1070.cpp
#define TEST

#ifdef TEST

#ifdef TEST
#endif
// C1070
```

可能的解决方法：

```cpp
// C1070b.cpp
// compile with: /c
#define TEST

#ifdef TEST
#endif

#ifdef TEST
#endif
```
