---
description: 了解更多：资源编译器警告 RW4004
title: 资源编译器警告 RW4004
ms.date: 11/04/2016
f1_keywords:
- RW4004
helpviewer_keywords:
- RW4004
ms.assetid: 596b6a89-9ce7-4ba7-bdcb-e8054c7efafa
ms.openlocfilehash: 5609d49e242ba7d74025622c53c279ae1b0da854
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236992"
---
# <a name="resource-compiler-warning-rw4004"></a>资源编译器警告 RW4004

ASCII 字符不等价于虚拟键代码

字符串文本已用于 VIRTKEY 类型快捷键中的虚拟键代码。

此警告允许你继续操作，但请注意，生成的快捷键可能与你指示的字符串不匹配。 （VIRTKEYs 与 ASCII 快捷键使用不同的键代码。）

虽然字符串文本在语法上是有效的，但只能使用 WINDOWS 中的 **VK_ \* #define** 值来确保获取所需的快捷键。
