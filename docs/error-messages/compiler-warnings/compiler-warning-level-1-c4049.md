---
description: 了解详细信息：编译器警告 (等级 1) C4049
title: 编译器警告 (等级 1) C4049
ms.date: 11/04/2016
f1_keywords:
- C4049
helpviewer_keywords:
- C4049
ms.assetid: d11c1870-bcfc-4d71-8945-b87ec6ec3514
ms.openlocfilehash: b6de6fd816be8925dab553ff4dc5a062300b42e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97160566"
---
# <a name="compiler-warning-level-1-c4049"></a>编译器警告 (等级 1) C4049

编译器限制：发射的终止行号

文件包含 16777215 (2<sup>24</sup>-1) 源行。 编译器停止编号为16777215。

对于第16777215行后面的代码：

- 该映像不包含行号的调试信息。

- 某些诊断可能报告了错误的行号。

- .asm 节目表 (/FAs) 可能具有错误的行号。
