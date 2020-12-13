---
description: 了解详细信息：严重错误 C1071
title: 错误 C1071
ms.date: 11/04/2016
f1_keywords:
- C1071
helpviewer_keywords:
- C1071
ms.assetid: 489f1786-370e-4ecd-af67-538fe6e5bd4e
ms.openlocfilehash: c4a6734dcb515b6d495eac720f83ba39be3c3677
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344375"
---
# <a name="fatal-error-c1071"></a>错误 C1071

在注释中遇到意外的文件结束

编译器在扫描注释时到达了文件的结尾。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 缺少注释终止符 ( */) 。

1. 源文件最后一行的注释后缺少换行符。

下面的示例生成 C1071：

```cpp
// C1071.cpp
int main() {
}

/* this comment is fine */
/* forgot the closing tag        // C1071
```
