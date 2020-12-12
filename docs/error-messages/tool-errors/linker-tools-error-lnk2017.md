---
description: 了解详细信息：链接器工具错误 LNK2017
title: 链接器工具错误 LNK2017
ms.date: 11/04/2016
f1_keywords:
- LNK2017
helpviewer_keywords:
- LNK2017
ms.assetid: f7c21733-b0fb-4888-a295-9b453ba6ee77
ms.openlocfilehash: e4215d7c1730f85f43c2440163fa03ad97c741e5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338442"
---
# <a name="linker-tools-error-lnk2017"></a>链接器工具错误 LNK2017

"symbol" 重定位到 "段" 无效，没有/LARGEADDRESSAWARE： NO

你正在尝试使用32位地址生成64位映像。 要这样做，必须：

- 使用固定的加载地址。

- 将图像限制为 3 GB。

- 指定 [/largeaddressaware： no](../../build/reference/largeaddressaware-handle-large-addresses.md)。
