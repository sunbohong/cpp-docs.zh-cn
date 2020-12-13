---
description: 了解详细信息：严重错误 C1081
title: 错误 C1081
ms.date: 11/04/2016
f1_keywords:
- C1081
helpviewer_keywords:
- C1081
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
ms.openlocfilehash: 97e1070cb24a70750e9c7d9f78a3860b26a7831a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97330702"
---
# <a name="fatal-error-c1081"></a>错误 C1081

"symbol"：文件名太长

文件路径名的长度超过 `_MAX_PATH` stdlib.h 定义的 (为260个字符) 。 缩短文件的名称。

如果使用短文件名调用 CL.exe，编译器可能需要生成完整的路径名。 例如， `cl -c myfile.cpp` 可能导致编译器生成：

```
D:\<very-long-directory-path>\myfile.cpp
```
