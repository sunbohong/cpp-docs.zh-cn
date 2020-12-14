---
description: 了解详细信息：链接器工具警告 LNK4205
title: 链接器工具警告 LNK4205
ms.date: 11/04/2016
f1_keywords:
- LNK4205
helpviewer_keywords:
- LNK4205
ms.assetid: d63b9d18-ef3c-4081-9d8d-93077dad13c2
ms.openlocfilehash: 1c08eb8b5206be5c61fe3806b984d450a987101f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97294166"
---
# <a name="linker-tools-warning-lnk4205"></a>链接器工具警告 LNK4205

"filename" 缺少引用模块的当前调试信息;正在链接对象，如同没有调试信息一样

.Pdb 文件包含过期信息。 链接器将继续链接对象，但不包含调试信息。 您可能想要使用 [/zi](../../build/reference/z7-zi-zi-debug-information-format.md) 选项重新编译对象文件。
