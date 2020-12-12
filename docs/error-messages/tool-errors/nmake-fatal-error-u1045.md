---
description: 了解详细信息： NMAKE 错误 U1045
title: NMAKE 错误 U1045
ms.date: 08/11/2019
f1_keywords:
- U1045
helpviewer_keywords:
- U1045
ms.assetid: dc70d162-14b9-4107-9237-7514044d72e3
ms.openlocfilehash: 722525d917b7511dfe2294adf2e796efd3078913
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97322890"
---
# <a name="nmake-fatal-error-u1045"></a>NMAKE 错误 U1045

> 生成失败： *消息*

由于 *消息* 原因，NMAKE 调用的程序或命令失败。 当 NMAKE 调用另一个程序（例如编译器或链接器）时，调用可能会失败。 或者，被调用的程序可能会返回错误。 此消息用于报告错误。

若要解决此问题，请首先确定错误原因。 可以使用 NMAKE [/n](../../build/reference/running-nmake.md#nmake-options) 选项报告的命令来验证环境设置，并重复 NMAKE 在命令行上执行的操作。
