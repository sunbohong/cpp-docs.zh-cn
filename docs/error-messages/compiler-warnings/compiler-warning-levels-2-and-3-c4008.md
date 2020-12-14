---
description: 了解详细信息：编译器警告 (级别2和 3) C4008
title: 编译器警告（等级 2 和等级 3）C4008
ms.date: 11/04/2016
f1_keywords:
- C4008
helpviewer_keywords:
- C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
ms.openlocfilehash: 6f13ef60efabeaffe549189431aa04c65a12cbe5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97234418"
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>编译器警告（等级 2 和等级 3）C4008

“identifier”：“attribute”属性被忽略

编译器忽略了 **`__fastcall`** **`static`** **`inline`** 函数 (等级3警告的、或属性) 或数据 (等级2警告) 。

### <a name="to-fix-by-checking-the-following-possible-causes"></a>通过检查以下可能的原因进行修复

1. **`__fastcall`** 具有数据的属性。

1. **`static`** 或 **`inline`** 具有 **main** 函数的属性。
