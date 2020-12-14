---
description: 了解详细信息：链接器工具错误 LNK1164
title: 链接器工具错误 LNK1164
ms.date: 11/04/2016
f1_keywords:
- LNK1164
helpviewer_keywords:
- LNK1164
ms.assetid: da89765c-affa-4f88-b170-6d6b19a577cf
ms.openlocfilehash: e4b9b1ae5bb7b15f192869fc8f633abf63cc9507
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97281140"
---
# <a name="linker-tools-error-lnk1164"></a>链接器工具错误 LNK1164

节部分对齐 (数字) 大于/ALIGN 值

对象文件中给定部分的对齐大小超过了用 [/align](../../build/reference/align-section-alignment.md) 选项指定的值。 **/Align** 值必须是2的幂，并且必须等于或大于对象文件中给定的节对齐方式。

使用较小的节对齐进行重新编译，或增加 **/align** 值。
