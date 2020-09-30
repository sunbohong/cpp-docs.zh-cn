---
title: 编译器警告（等级 1）C4819
ms.date: 04/08/2019
f1_keywords:
- C4819
helpviewer_keywords:
- C4819
ms.assetid: c0316e85-249c-414d-9df0-622d077c6bc2
ms.openlocfilehash: f81a4f44a489e2e4c5bd5c063d922129581819f9
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509361"
---
# <a name="compiler-warning-level-1-c4819"></a>编译器警告（等级 1）C4819

> 文件包含不能在当前代码页中表示的字符 (*号*) 。 以 Unicode 格式保存该文件防止数据丢失。

使用无法表示文件中所有字符的代码页在系统上编译 ANSI 源文件时，会发生 C4819。

可以通过多种方法来解析 C4819。 一种简单的方法是删除有问题的字符（如果不需要），例如，如果它在注释中。 您可以在 "控制面板" 中将 "系统代码页" 设置为支持您的源代码所使用的字符集的 "代码页"。 您可以使用 Unicode [转义序列](../../c-language/escape-sequences.md) 来创建只在源代码中使用基本 ANSI 字符集的字符或字符串。 最后，可以将文件保存为 Unicode 格式，其中包含签名，也称为字节顺序标记 (BOM) 。

若要以 Unicode 格式保存文件，请在 Visual Studio 中选择 "**文件**  >  **另存为**"。 在 "将 **文件另存为** " 对话框中，选择 " **保存** " 按钮上的下拉箭头，然后选择 " **保存并编码**"。 如果保存到相同的文件名，可能需要确认是否要替换该文件。 在 " **高级保存选项** " 对话框中，选择可表示文件中所有字符的编码（例如， **使用签名) -代码页65001的 Unicode (utf-8**），然后选择 **"确定"**。
