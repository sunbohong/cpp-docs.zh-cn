---
description: 了解详细信息：表达式计算器错误 CXX0036
title: 表达式计算器错误 CXX0036
ms.date: 11/04/2016
f1_keywords:
- CXX0036
helpviewer_keywords:
- CXX0036
- CAN0036
ms.assetid: 383404be-df5b-4eec-b113-df21bb5d269d
ms.openlocfilehash: fa595c590b6e59b74d693f3b6ff777055b5af2c1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97338533"
---
# <a name="expression-evaluator-error-cxx0036"></a>表达式计算器错误 CXX0036

错误的上下文 {...} specification

使用上下文运算符 () 中的任何一种错误都可生成此消息 **{}** 。

- 未正确给定上下文运算符 () 的语法 **{}** 。

   上下文运算符的语法为：

     {*function*，*module*，*dll*}*表达式*

   这将指定 *表达式* 的上下文。 上下文运算符与类型转换的优先级和用法相同。

   可以省略尾随逗号。 如果任何 *函数*、 *模块* 或 *dll* 包含文字逗号，则必须将整个名称括在括号中。

- 函数名拼写错误，或在指定的模块或动态链接库中不存在。

   因为 C 是一种区分大小写的语言，所以必须在与源中定义的完全相同的情况下提供 *函数* 。

- 未能找到该模块或 DLL。

   检查指定模块或 DLL 的完整路径名称。

此错误与 CAN0036 相同。
