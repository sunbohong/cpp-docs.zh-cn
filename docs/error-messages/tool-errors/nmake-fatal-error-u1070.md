---
description: 了解详细信息： NMAKE 错误 U1070
title: NMAKE 错误 U1070
ms.date: 11/04/2016
f1_keywords:
- U1070
helpviewer_keywords:
- U1070
ms.assetid: 8639fc39-b4b1-48f5-ac91-0e9fb61680fd
ms.openlocfilehash: a3d0ee448062fec8a024501b0c08d5f0466d974b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97283519"
---
# <a name="nmake-fatal-error-u1070"></a>NMAKE 错误 U1070

宏定义 "macroname" 中的循环

给定宏定义包含一个宏，其定义中包含了给定的宏。 循环宏定义无效。

## <a name="example"></a>示例

以下宏定义

```
ONE=$(TWO)
TWO=$(ONE)
```

导致以下错误：

```
cycle in macro definition 'TWO'
```
