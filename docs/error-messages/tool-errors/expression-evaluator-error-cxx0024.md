---
description: 了解详细信息：表达式计算器错误 CXX0024
title: 表达式计算器错误 CXX0024
ms.date: 11/04/2016
f1_keywords:
- CXX0024
helpviewer_keywords:
- CXX0024
- CAN0024
ms.assetid: eca6adbd-8ff2-4f51-a1cc-a2e9d5d0a47d
ms.openlocfilehash: cb40199c217180b08e62d89dee551130eefefc35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97228074"
---
# <a name="expression-evaluator-error-cxx0024"></a>表达式计算器错误 CXX0024

操作需要左值

为需要左值的操作指定的表达式的计算结果不是左值。

左值 (因此调用，因为它显示在赋值语句的左侧) 是引用内存位置的表达式。

例如， `buffer[count]` 是一个有效的左值，因为它指向特定的内存位置。 逻辑比较 `zed != 0` 不是有效的左值，因为它的计算结果为 TRUE 或 FALSE，而不是内存地址。

此错误与 CAN0024 相同。
