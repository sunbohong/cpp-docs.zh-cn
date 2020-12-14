---
description: 了解详细信息：严重错误 C1004
title: 错误 C1004
ms.date: 11/04/2016
f1_keywords:
- C1004
helpviewer_keywords:
- C1004
ms.assetid: dbe034b0-6eb0-41b4-a50c-2fccf9e78ad4
ms.openlocfilehash: f21978f5ff314a8273dde60428dc89ca0c5767b0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262680"
---
# <a name="fatal-error-c1004"></a>错误 C1004

找到意外的文件结尾

编译器在未解析构造的情况下到达了源文件的结尾。 代码可能缺少以下元素之一：

- 右大括号

- 右括号

- 结束注释标记 ( */) 

- 分号

若要解决此错误，请检查以下各项：

- 默认磁盘驱动器的临时文件空间不足，需要大约两倍于源文件空间。

- `#if`计算结果为 false 的指令缺少结束 `#endif` 指令。

- 源文件不以回车符和换行符结尾。

下面的示例生成 C1004：

```cpp
// C1004.cpp
#if TEST
int main() {}
// C1004
```

可能的解决方法：

```cpp
// C1004b.cpp
#if TEST
#endif

int main() {}
```
