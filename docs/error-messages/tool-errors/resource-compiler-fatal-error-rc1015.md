---
description: 了解更多：资源编译器错误 RC1015
title: 资源编译器错误 RC1015
ms.date: 11/04/2016
f1_keywords:
- RC1015
helpviewer_keywords:
- RC1015
ms.assetid: 23f187e1-5538-40b5-9042-edd2888f55c2
ms.openlocfilehash: 41afe385189d35e80e5f624d379b45c0dca17441
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97265657"
---
# <a name="resource-compiler-fatal-error-rc1015"></a>资源编译器错误 RC1015

无法打开包含文件 "filename"

给定的包含文件不存在、无法打开或找不到。

确保环境设置有效，并且已为该文件指定了正确的路径。 确保有足够的文件句柄可用于资源编译器。 如果文件位于网络驱动器上，请确保您有打开该文件的权限。

即使包含文件存在于指定为 "配置属性-> 资源-> 常规" 属性页中的 "附加包含目录" 的目录中，也可能会发生 RC1015;指定包含文件的完整路径。
