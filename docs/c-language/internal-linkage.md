---
description: 详细了解：内部链接
title: 内部链接
ms.date: 11/04/2016
helpviewer_keywords:
- internal linkage
- linkage [C++], internal
ms.assetid: 80be7b51-c930-43db-94d6-4f09a64077bf
ms.openlocfilehash: a22de598f119ec303cb7ea78255c2537c6ed306e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97181860"
---
# <a name="internal-linkage"></a>内部链接

如果对象或函数的文件范围标识符声明包含 storage-class-specifier `static`，则标识符有内部链接。 否则，该标识符具有外部链接。 有关 storage-class-specifier  非终止符的讨论，请参阅[存储类](../c-language/c-storage-classes.md)。

在一个翻译单元内，带内部链接的标识符的每个实例均表示相同的标识符或函数。 内部链接的标识符对于翻译单元是唯一的。

## <a name="see-also"></a>请参阅

[使用 extern 指定链接](../cpp/extern-cpp.md)
