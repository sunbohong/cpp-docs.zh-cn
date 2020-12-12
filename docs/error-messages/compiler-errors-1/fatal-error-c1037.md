---
description: 了解详细信息：严重错误 C1037
title: 错误 C1037
ms.date: 11/04/2016
f1_keywords:
- C1037
helpviewer_keywords:
- C1037
ms.assetid: 79103bca-ccfb-42e7-aef9-9b90c15b162f
ms.openlocfilehash: 9947843fa99b6b545ffc4120d839d4bae5c2cee0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97123833"
---
# <a name="fatal-error-c1037"></a>错误 C1037

无法打开对象文件的文件名

无法打开由 [/Fo](../../build/reference/fo-object-file-name.md) 指定的对象文件。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 文件名无效。

1. 内存不足，无法打开该文件。

1. 另一个进程正在使用该文件。

1. 一个只读文件具有相同的名称。
