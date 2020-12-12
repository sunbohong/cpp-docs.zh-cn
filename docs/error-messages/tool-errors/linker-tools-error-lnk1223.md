---
description: 了解详细信息：链接器工具错误 LNK1223
title: 链接器工具错误 LNK1223
ms.date: 11/04/2016
f1_keywords:
- LNK1223
helpviewer_keywords:
- LNK1223
ms.assetid: c4728c36-daee-462f-a1c7-8733dcdec88e
ms.openlocfilehash: eb1937f253d324781834d0b6f465c79f7009787f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97194054"
---
# <a name="linker-tools-error-lnk1223"></a>链接器工具错误 LNK1223

无效或损坏的文件：文件包含无效的 pdata 基值

对于使用 pdata 的 RISC 平台，如果编译器发出具有无序条目的 .pdata 部分，则将发生此错误。

若要解决此问题，请尝试在没有 [/gl (完全程序优化) ](../../error-messages/tool-errors/linker-tools-error-lnk1223.md) 启用的情况下编译。 在某些情况下，空的函数体也可能导致此错误。
