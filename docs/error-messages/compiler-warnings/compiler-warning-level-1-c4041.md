---
description: 了解详细信息：编译器警告 (等级 1) C4041
title: 编译器警告（等级 1）C4041
ms.date: 11/04/2016
f1_keywords:
- C4041
helpviewer_keywords:
- C4041
ms.assetid: 107ee9fd-4b88-4f22-a18f-a20726831095
ms.openlocfilehash: d3473be35182f6c99541aa2a0fc79de79dee4a07
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160709"
---
# <a name="compiler-warning-level-1-c4041"></a>编译器警告（等级 1）C4041

编译器限制 : 正在终止浏览器输出

浏览器信息超出了编译器限制。

使用 [/FR](../../build/reference/fr-fr-create-dot-sbr-file.md) （浏览器信息包含局部变量）进行编译可能导致该警告。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>使用以下可能的解决方案进行修复

1. 使用 /Fr（浏览器信息不含局部变量）进行编译。

1. 禁用浏览器输出（不使用 /FR 或 /Fr 进行编译）。
