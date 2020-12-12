---
description: 了解详细信息： Command-Line 警告 D9043
title: 命令行警告 D9043
ms.date: 11/04/2016
f1_keywords:
- D9043
helpviewer_keywords:
- D9043
ms.assetid: 9263e28d-217b-414c-bfb6-86efd3c27a77
ms.openlocfilehash: ac61626f21465056ea96efe784e19405481f1b0f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97119744"
---
# <a name="command-line-warning-d9043"></a>命令行警告 D9043

"compiler_option" 的值 "warning_level" 无效;假定为 "4999";代码分析警告与警告等级无关

## <a name="example"></a>示例

下面的示例生成 C9043。

```cpp
// D9043.cpp
// compile with: /analyze /w16001
// D9043 warning expected
int main() {}
```
