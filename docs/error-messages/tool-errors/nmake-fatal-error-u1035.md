---
description: 了解详细信息： NMAKE 错误 U1035
title: NMAKE 错误 U1035
ms.date: 11/04/2016
f1_keywords:
- U1035
helpviewer_keywords:
- U1035
ms.assetid: 68f0cc59-007e-4109-ac30-7ac4ac447e6d
ms.openlocfilehash: e41b65cbec43a0b19e06767c555df9cfede9b69c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97197746"
---
# <a name="nmake-fatal-error-u1035"></a>NMAKE 错误 U1035

语法错误：应输入 "：" 或 "=" 分隔符

应为冒号 (**：**) 或 () 的等号 **=** 。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 冒号不在目标之后。

1. 冒号和无空格 (例如： ) 后跟单字母目标。 NMAKE 将它解释为驱动器规格。

1. 冒号不遵循推理规则。

1. 宏定义后面没有等号。

1. 字符后跟反斜杠 (**\\** 用于将命令继续到新行的) 。

1. 出现的字符串不遵循任何 NMAKE 语法规则。

1. 生成文件由字处理器进行了格式设置。
