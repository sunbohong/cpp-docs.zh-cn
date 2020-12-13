---
description: 了解详细信息：链接器工具错误 LNK1200
title: 链接器工具错误 LNK1200
ms.date: 11/04/2016
f1_keywords:
- LNK1200
helpviewer_keywords:
- LNK1200
ms.assetid: 55771145-915e-4006-ac6c-ac702041eb2f
ms.openlocfilehash: b8c380b16cef47a4b340e4a48853d58d1ab203e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341641"
---
# <a name="linker-tools-error-lnk1200"></a>链接器工具错误 LNK1200

读取程序数据库 "filename" 时出错

无法读取 (PDB) 的程序数据库。

此错误可能是由文件损坏引起的。

如果 `filename` 是对象文件的 PDB，请使用 [/zi](../../build/reference/z7-zi-zi-debug-information-format.md)重新编译对象文件。

如果 `filename` 是主输出文件的 PDB，而在增量链接期间发生此错误，请删除 PDB 并重新链接。
