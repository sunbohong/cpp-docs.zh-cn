---
description: 详细了解：翻译：诊断
title: 翻译：诊断
ms.date: 11/04/2016
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
ms.openlocfilehash: 09fc44dea8d51dbb267d402745c8c2a095b969d8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243050"
---
# <a name="translation-diagnostics"></a>翻译：诊断

**ANSI 2.1.1.3** 如何标识诊断

Microsoft C 生成以下形式的错误消息：

> *filename* **(** *line-number* **) :** *diagnostic* **C**<em>number</em> *message*

其中，filename  是出现错误的源文件的名称；line-number  是编译器在其中检测到错误的行号；diagnostic  是“错误”或“警告”；number  是标识错误或警告的唯一的四位数（前面带有 C  ，如语法中所注明的）；message  是解释性消息。

## <a name="see-also"></a>请参阅

[实现定义的行为](../c-language/implementation-defined-behavior.md)
