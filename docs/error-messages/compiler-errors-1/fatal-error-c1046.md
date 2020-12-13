---
description: 了解详细信息：严重错误 C1046
title: 错误 C1046
ms.date: 11/04/2016
f1_keywords:
- C1046
helpviewer_keywords:
- C1046
ms.assetid: 822ec5f5-b0b0-4711-99e1-fc237b619af6
ms.openlocfilehash: 0251d717ba86405a90ed34b170af39e0b9eacea1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97341199"
---
# <a name="fatal-error-c1046"></a>错误 C1046

编译器限制：结构嵌套太深

结构、联合或类超出了15个级别的嵌套限制。 重写定义以降低嵌套级别。 使用 **`typedef`** 定义一个或多个嵌套结构，将结构、联合或类拆分为两个或多个部分。
