---
description: 了解详细信息：表达式计算器错误 CXX0052
title: 表达式计算器错误 CXX0052
ms.date: 11/04/2016
f1_keywords:
- CXX0052
helpviewer_keywords:
- CXX0052
- CAN0052
ms.assetid: 5060d479-d0a4-4682-b858-c8b9a4f324e6
ms.openlocfilehash: a98da6c3d562a3bf95a6e47c97ed803e504a3972
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97208393"
---
# <a name="expression-evaluator-error-cxx0052"></a>表达式计算器错误 CXX0052

成员函数不存在

将成员函数指定为断点，但找不到该函数。 在已内联的函数中设置断点可能导致此错误。

使用内联强行禁用 (/Ob0) 重新编译文件，以便在此函数中设置断点。

表达式调用了未定义的函数。

此错误与 CAN0052 相同。
