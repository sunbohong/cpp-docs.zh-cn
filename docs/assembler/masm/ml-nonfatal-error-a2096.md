---
description: 了解更多： ML 非严重错误 A2096
title: ML 非致命错误 A2096
ms.date: 12/17/2019
ms.custom: error-reference
f1_keywords:
- A2096
helpviewer_keywords:
- A2096
ms.assetid: bab0b5ee-b39f-4e44-a41a-3f949fab4297
ms.openlocfilehash: cbef33a8147b9f4cbe436860611f643b4f272516
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97128526"
---
# <a name="ml-nonfatal-error-a2096"></a>ML 非致命错误 A2096

**应输入段、组或段寄存器**

需要段或组，但找不到。

出现下列情况之一：

- 使用段替代运算符指定的左操作数 (**：**) 不是段寄存器 (CS、DS、SS、ES、FS 或 GS) 、组名称、段名称或段表达式。

- [假设](assume.md)在给定段寄存器时没有有效的段地址、段寄存器、组或特殊的 **平面** 组。

## <a name="see-also"></a>请参阅

[ML 错误消息](ml-error-messages.md)
