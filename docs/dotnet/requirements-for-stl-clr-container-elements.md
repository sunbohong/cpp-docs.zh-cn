---
description: 了解详细信息： STL/CLR 容器元素的要求
title: STL/CLR 容器元素的需求
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- C++ Standard Library, template class containers
- STL/CLR, containers
- containers, STL/CLR
- containers, C++ Standard Library
ms.assetid: 59ab240c-15bf-4701-a9f9-e7c56e5ab53f
ms.openlocfilehash: 3696d9df40f69b1dd39205a2dc7a3b802e815841
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97305501"
---
# <a name="requirements-for-stlclr-container-elements"></a>STL/CLR 容器元素的需求

插入 STL/CLR 容器的所有引用类型必须至少具有以下元素：

- 公共复制构造函数。

- 公共赋值运算符。

- 公共析构函数。

此外，" [设置](../dotnet/set-stl-clr.md) " 和 " [映射](../dotnet/map-stl-clr.md) " 等关联容器必须定义一个公共比较运算符，这在 `operator<` 默认情况下为。 对容器的某些运算还可能需要定义公共默认构造函数和公共等效运算符。

与引用类型相似，要插入关联容器的引用类型的值类型和句柄必须有一个比较运算符，如 `operator<`。 引用类型的值类型或句柄没有对公共复制构造函数、公共赋值运算符和公共析构函数的要求。

## <a name="see-also"></a>请参阅

[C + + 标准库参考](../standard-library/cpp-standard-library-reference.md)
