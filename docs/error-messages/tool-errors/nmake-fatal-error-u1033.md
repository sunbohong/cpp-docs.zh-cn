---
description: 了解详细信息： NMAKE 错误 U1033
title: NMAKE 错误 U1033
ms.date: 11/04/2016
f1_keywords:
- U1033
helpviewer_keywords:
- U1033
ms.assetid: c146f7b5-7d5c-4329-a522-28a648546016
ms.openlocfilehash: e616e98a21c92137fab4b167318a9305a2175bb2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272131"
---
# <a name="nmake-fatal-error-u1033"></a>NMAKE 错误 U1033

语法错误：意外的 "string"

该字符串不是生成文件的有效语法的一部分。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 如果 **<<** 内联文件 () 的右尖括号集不在行首，则会发生以下错误：

    ```
    syntax error : 'EOF' unexpected
    ```

1. 如果生成文件中的宏定义包含等号 (**=**) 没有前面的名称，或者如果要定义的名称是扩展到 nothing 的宏，则会发生以下错误：

    ```
    syntax error : '=' unexpected
    ```

1. 如果分号 (**;** 在 TOOLS.INI 中的注释行) 不在行首，则会发生以下错误：

    ```
    syntax error : ';' unexpected
    ```

1. 如果生成文件已由字处理程序设置格式，则可能会发生以下错误：

    ```
    syntax error : ':' unexpected
    ```
