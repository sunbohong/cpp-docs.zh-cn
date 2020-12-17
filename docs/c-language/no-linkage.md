---
description: 详细了解：无链接
title: 无链接
ms.date: 11/04/2016
helpviewer_keywords:
- no linkage
- linkage [C++], none
ms.assetid: 5a413082-1034-4e04-b76b-8d14668bf434
ms.openlocfilehash: cf0e1ccbbea3b79bce66335e361f3c23162e6cb6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97243310"
---
# <a name="no-linkage"></a>无链接

如果块内某标识符的声明不包括 `extern` 存储类说明符，则此标识符没有链接，并且对函数是唯一的。

以下标识符没有链接：

- 声明为除对象或函数以外的任何项的标识符

- 声明为函数参数的标识符

- 声明不包含 `extern` 存储类说明符的对象的块范围标识符

如果标识符没有链接，那么在相同的范围级别内再次声明相同的名称（在声明符或类型说明符中）将产生符号重新定义错误。

## <a name="see-also"></a>请参阅

[使用 extern 指定链接](../cpp/extern-cpp.md)
