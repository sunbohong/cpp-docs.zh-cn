---
description: 了解详细信息：输入/输出替代项
title: Input-Output 替代项
ms.date: 05/07/2019
helpviewer_keywords:
- I/O [C++], alternatives
ms.assetid: 9f8401c7-d90d-4285-8918-63573df74a80
ms.openlocfilehash: a6df022dd38bc23eaaaad49620067aca408b2df2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97323997"
---
# <a name="inputoutput-alternatives"></a>输入/输出替换选项

Microsoft c + + 编译器为 i/o 编程提供了几种替代方法：

- C 运行时库直接无缓冲 I/O。

- ANSI C 运行时库流 I/O。

- 控制台和端口直接 I/O。

- Microsoft 基础类库。

- Microsoft C++ 标准库。

iostream 类适用于缓冲的格式化文本 I/O。 如果需要 C++ 编程接口且决定不使用 Microsoft 基础类 (MFC) 库，此类也适用于无缓冲或二进制 I/O。 iostream 类是 C 运行时函数的一种面向对象的 I/O 替代方法。

可将 iostream 类用于 Microsoft Windows 操作系统。 字符串和文件流无使用限制条件，但字符模型流对象 `cin`、`cout`、`cerr` 和 `clog` 与 Windows 图形用户界面不一致。 也可派生与 Windows 环境直接交互的自定义流类。

## <a name="see-also"></a>请参阅

[流的定义](../standard-library/what-a-stream-is.md)
