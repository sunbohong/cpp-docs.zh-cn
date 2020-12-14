---
description: 了解详细信息：严重错误 C1054
title: 错误 C1054
ms.date: 11/04/2016
f1_keywords:
- C1054
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
ms.openlocfilehash: 1bfe8718fcb0d3edb172f0f5a89bb2f479e56137
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97251656"
---
# <a name="fatal-error-c1054"></a>错误 C1054

编译器限制：初始值设定项嵌套太深

此代码超出了对初始值设定项的嵌套限制 (10-15 级别，具体取决于) 初始化的类型的组合。

### <a name="to-fix-by-using-the-following-possible-solutions"></a>使用以下可能的解决方案进行修复

1. 简化要初始化的数据类型，以减少嵌套。

1. 在声明后，在单独的语句中初始化变量。
