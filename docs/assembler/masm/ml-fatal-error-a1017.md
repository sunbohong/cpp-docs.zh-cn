---
description: 了解更多： ML 错误 A1017
title: ML 错误 A1017
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A1017
helpviewer_keywords:
- A1017
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
ms.openlocfilehash: f15896e18721ef149cabd178bca433844a6edef5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97129436"
---
# <a name="ml-fatal-error-a1017"></a>ML 错误 A1017

**缺少源文件名**

ML 找不到要汇编或传递到链接器的文件。

如果不指定要操作的文件名，则会生成 ML 命令行选项。 若要组合不具有 .asm 扩展名的文件，请使用 **/Ta** 命令行选项。

如果 ML 环境变量包含命令行选项，则还可以通过调用不带参数的 ML 来生成此错误。

## <a name="see-also"></a>请参阅

[ML 错误消息](ml-error-messages.md)
