---
description: 了解详细信息：链接器工具警告 LNK4014
title: 链接器工具警告 LNK4014
ms.date: 11/04/2016
f1_keywords:
- LNK4014
helpviewer_keywords:
- LNK4014
ms.assetid: 394903e9-3ded-4ea4-b7c0-a3535d4b4da4
ms.openlocfilehash: 50de7bcba93e5df93c5c81b247be788a844b7e15
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331978"
---
# <a name="linker-tools-warning-lnk4014"></a>链接器工具警告 LNK4014

找不到成员对象 "objectname"

库中找不到 LIB `objectname` 。

**/Remove** 和 **/EXTRACT** 选项要求要删除或复制到文件的成员对象的完整名称。 全名包括原始对象文件的路径。 若要查看库中成员对象的完整名称，请使用 DUMPBIN [/ARCHIVEMEMBERS](../../build/reference/archivemembers.md) 或 LIB [/list](../../build/reference/managing-a-library.md)。
