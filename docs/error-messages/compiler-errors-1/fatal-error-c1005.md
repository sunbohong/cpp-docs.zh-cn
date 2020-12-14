---
description: 了解详细信息：严重错误 C1005
title: 错误 C1005
ms.date: 11/04/2016
f1_keywords:
- C1005
helpviewer_keywords:
- C1005
ms.assetid: 150daf8e-a38a-4669-9c1a-a05b5a1f65ef
ms.openlocfilehash: c57856a09aa3473c7f5ba3049a2962fb4553e4e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97262667"
---
# <a name="fatal-error-c1005"></a>错误 C1005

字符串对于缓冲区太大

编译器中间文件内的字符串溢出了缓冲区。

当你传递到 [/Fd](../../build/reference/fd-program-database-file-name.md) 或 [/Yl](../../build/reference/yl-inject-pch-reference-for-debug-library.md) 编译器选项的参数大于 256 个字节时，可能会遇到此错误。
