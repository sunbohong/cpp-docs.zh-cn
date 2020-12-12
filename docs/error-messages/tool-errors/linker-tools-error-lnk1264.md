---
description: 了解详细信息：链接器工具错误 LNK1264
title: 链接器工具错误 LNK1264
ms.date: 11/04/2016
f1_keywords:
- LNK1264
helpviewer_keywords:
- LNK1264
ms.assetid: 23b1aad7-d382-42c1-bae8-db68575c57a8
ms.openlocfilehash: 122186482800597780405ae89e8e01c008794756
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97193781"
---
# <a name="linker-tools-error-lnk1264"></a>链接器工具错误 LNK1264

/LTCG：已指定 PGINSTRUMENT，但不需要生成代码;检测失败

**/Ltcg：** 已指定 PGINSTRUMENT，但找不到用 [/gl](../../build/reference/gl-whole-program-optimization.md)编译的 .obj 文件。 检测无法发生，链接失败。 在用 **/gl** 编译的命令行上必须至少有一个 .obj 文件，以便进行检测。

按配置优化 (PGO) 仅适用于64位编译器。
