---
description: 了解详细信息： NMAKE 警告 U4004
title: NMAKE 警告 U4004
ms.date: 11/04/2016
f1_keywords:
- U4004
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
ms.openlocfilehash: 44326bfb6a69b583967163054b4510bf5c50d6bf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97345285"
---
# <a name="nmake-warning-u4004"></a>NMAKE 警告 U4004

目标 "targetname" 的规则太多

使用单个冒号为给定目标指定了多个描述块 (**：**) 作为分隔符。 NMAKE 在第一个 description 块中执行了命令，并忽略了以后的块。

若要在多个依赖项中指定同一目标，请使用两个冒号 (`::`) 作为每个依赖项行中的分隔符。
