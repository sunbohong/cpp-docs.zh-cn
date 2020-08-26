---
title: STL/CLR 库参考
ms.date: 09/18/2018
ms.topic: reference
helpviewer_keywords:
- STL/CLR Library
- STL/CLR, redistribution
- cliext directory
ms.assetid: a9d9ca00-7bf2-48c1-b205-3ae6f8c25f82
ms.openlocfilehash: e6804dab814eca4ecc5fd23c74cbbb21eac3be77
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839694"
---
# <a name="stlclr-library-reference"></a>STL/CLR 库参考

STL/CLR 库提供类似于 c + + 标准库容器的接口，与 c + + 和 .NET Framework 公共语言运行时 (CLR) 相同。 STL/CLR 与 c + + 标准库的 Microsoft 实现完全分离。 STL/CLR 是为实现旧支持而维护的，但它不是用 c + + 标准保持最新的。 强烈建议尽可能使用本机 [c + + 标准库](../standard-library/cpp-standard-library-reference.md) 容器，而不是 STL/CLR。

使用 STL/CLR：

- 包含 **cliext** 中的标头包括子目录，而不是常用的 c + + 标准库。

- 用代替来限定库名称 `cliext::` `std::` 。

STL/CLR 库提供了类似于 STL 的接口，可与 c + + 和 .NET Framework 公共语言运行时 (CLR) 一起使用。 此库是为传统支持维护的，但它不是用 c + + 标准保持最新的。 强烈建议使用本机 [c + + 标准库](../standard-library/cpp-standard-library-reference.md) 容器，而不是 STL/CLR。

## <a name="in-this-section"></a>本节内容

[cliext 命名空间](../dotnet/cliext-namespace.md)<br/>
讨论包含 STL/CLR 库的所有类型的命名空间。

[STL/CLR 容器](../dotnet/stl-clr-containers.md)<br/>
提供 c + + 标准库中的容器的概述，包括容器元素的要求、可以插入的元素类型和所有权问题。

[STL/CLR 容器元素的要求](../dotnet/requirements-for-stl-clr-container-elements.md)<br/>
描述插入 c + + 标准库容器中的所有引用类型的最低要求。

[如何：从 .NET 集合转换为 STL/CLR 容器](../dotnet/how-to-convert-from-a-dotnet-collection-to-a-stl-clr-container.md)<br/>
介绍如何将 .NET 集合转换为 STL/CLR 容器。

[如何：从 STL/CLR 容器转换为 .NET 集合](../dotnet/how-to-convert-from-a-stl-clr-container-to-a-dotnet-collection.md)<br/>
介绍如何将 STL/CLR 容器转换为 .NET 集合。

[如何：公开程序集中的 STL/CLR 容器](../dotnet/how-to-expose-an-stl-clr-container-from-an-assembly.md)<br/>
演示如何显示用 c + + 程序集编写的多个 STL/CLR 容器的元素。

此外，本节还介绍了 STL/CLR 的以下组件：

:::row:::
   :::column span="":::
      [`adapter` (STL/CLR) ](../dotnet/adapter-stl-clr.md)\
      [`algorithm` (STL/CLR) ](../dotnet/algorithm-stl-clr.md)\
      [`deque` (STL/CLR) ](../dotnet/deque-stl-clr.md)\
      [`for each`, `in`](../dotnet/for-each-in.md)\
      [`functional` (STL/CLR) ](../dotnet/functional-stl-clr.md)\
      [`hash_map` (STL/CLR) ](../dotnet/hash-map-stl-clr.md)\
      [`hash_multimap` (STL/CLR) ](../dotnet/hash-multimap-stl-clr.md)\
      [`hash_multiset` (STL/CLR) ](../dotnet/hash-multiset-stl-clr.md)\
      [`hash_set` (STL/CLR) ](../dotnet/hash-set-stl-clr.md)\
      [`list` (STL/CLR) ](../dotnet/list-stl-clr.md)\
   :::column-end:::
   :::column span="":::
      [`map` (STL/CLR) ](../dotnet/map-stl-clr.md)\
      [`multimap` (STL/CLR) ](../dotnet/multimap-stl-clr.md)\
      [`multiset` (STL/CLR) ](../dotnet/multiset-stl-clr.md)\
      [`numeric` (STL/CLR) ](../dotnet/numeric-stl-clr.md)\
      [`priority_queue` (STL/CLR) ](../dotnet/priority-queue-stl-clr.md)\
      [`queue` (STL/CLR) ](../dotnet/queue-stl-clr.md)\
      [`set` (STL/CLR) ](../dotnet/set-stl-clr.md)\
      [`stack` (STL/CLR) ](../dotnet/stack-stl-clr.md)\
      [`utility` (STL/CLR) ](../dotnet/utility-stl-clr.md)\
      [`vector` (STL/CLR) ](../dotnet/vector-stl-clr.md)\
   :::column-end:::
:::row-end:::

## <a name="see-also"></a>另请参阅

[C + + 标准库](../standard-library/cpp-standard-library-reference.md)
