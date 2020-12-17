---
description: 详细了解：外部链接
title: 外部链接
ms.date: 11/04/2016
helpviewer_keywords:
- linkage [C++], external
- external linkage, about external linkage
- external linkage
ms.assetid: a6f8ea69-b405-4cdd-bf12-ad5462b73183
ms.openlocfilehash: 6920183c53067462dbaadb8514bf747300eb6a1c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97196277"
---
# <a name="external-linkage"></a>外部链接

如果标识符在文件范围级别的第一个声明没有使用 `static` 存储类说明符，则对象有外部链接。

如果函数标识符的声明没有 storage-class-specifier，则它的链接确定方式与使用 storage-class-specifier `extern` 声明它时完全一样。 如果对象标识符的声明具有文件范围但没有 storage-class-specifier  ，则其链接为外部的。

具有外部链接的标识符的名称指定相同的函数或数据对象，这与具有外部连接的相同名称的任何其他声明一样。 这两个声明可以在同一个翻译单元中，也可以在不同的翻译单元中。 如果该对象或函数还具有全局生存期，则该对象或函数由整个程序共享。

## <a name="see-also"></a>请参阅

[使用 extern 指定链接](../cpp/extern-cpp.md)
