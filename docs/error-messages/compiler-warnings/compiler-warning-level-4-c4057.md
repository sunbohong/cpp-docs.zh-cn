---
description: 详细了解：编译器警告 (级别 4) C4057
title: 编译器警告（等级 4）C4057
ms.date: 11/04/2016
f1_keywords:
- C4057
helpviewer_keywords:
- C4057
ms.assetid: e75d0645-84c9-4bef-a812-942ed9879aa3
ms.openlocfilehash: 0b5da5c4768f4101b7b1780b5d0518ed723c5225
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262082"
---
# <a name="compiler-warning-level-4-c4057"></a>编译器警告（等级 4）C4057

“operator”: “identifier1”与“identifier2”在稍微不同的基类型间接寻址上不同

两个指针表达式引用不同的基类型。 使用表达式时无需转换。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. 混合签名和未签名的类型。

1. 混合 **`short`** **`long`** 类型和类型。
