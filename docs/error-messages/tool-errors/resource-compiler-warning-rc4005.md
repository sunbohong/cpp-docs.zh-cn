---
description: 了解更多：资源编译器警告 RC4005
title: 资源编译器警告 RC4005
ms.date: 11/04/2016
f1_keywords:
- RC4005
helpviewer_keywords:
- RC4005
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
ms.openlocfilehash: 138037e48356448550308abee8dc43cd06b9ac06
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97237122"
---
# <a name="resource-compiler-warning-rc4005"></a>资源编译器警告 RC4005

"identifier"：宏重定义

标识符定义了两次。 编译器使用第二个宏定义。

通过使用指令在命令行和代码中定义宏可能导致此警告 `#define` 。 它也可能是从包含文件导入的宏导致的。

若要消除此警告，请删除其中一个定义，或者在 `#undef` 第二个定义之前使用指令。
