---
description: '了解更多相关信息：自定义字符串管理器的实现 (高级方法) '
title: '自定义字符串管理器的实现 (高级方法) '
ms.date: 11/04/2016
helpviewer_keywords:
- IAtlStringMgr class, using
ms.assetid: 64ab7da9-47c1-4c4a-9cd7-4cc37e7f3f57
ms.openlocfilehash: 042c0759076d14e2fd0cf8dd91e34c4f1d8bb534
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97166962"
---
# <a name="implementation-of-a-custom-string-manager-advanced-method"></a>自定义字符串管理器的实现 (高级方法) 

在特殊情况下，您可能需要实现自定义字符串管理器，而不仅仅更改用于分配内存的堆。 在这种情况下，你必须手动实现 [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) 接口作为自定义字符串管理器。

为此，必须首先了解 [CStringT](../atl-mfc-shared/reference/cstringt-class.md) 如何使用该接口管理其字符串数据。 每个实例 `CStringT` 都有一个指向 [CStringData](../atl-mfc-shared/reference/cstringdata-class.md) 结构的指针。 此长度可变的结构包含有关字符串 (的重要信息，例如长度) ，以及字符串的实际字符数据。 每个自定义字符串管理器都负责在请求时分配和释放这些结构 `CStringT` 。

`CStringData`结构由四个字段组成：

- [pStringMgr](../atl-mfc-shared/reference/cstringdata-class.md#pstringmgr) 此字段指向 `IAtlStringMgr` 用于管理此字符串数据的接口。 当 `CStringT` 需要重新分配或释放字符串缓冲区时，它将调用此接口的重新分配或释放方法，并将该 `CStringData` 结构作为参数传递。 `CStringData`在字符串管理器中分配结构时，必须将此字段设置为指向您的自定义字符串管理器。

- [nDataLength](../atl-mfc-shared/reference/cstringdata-class.md#ndatalength) 此字段包含存储在缓冲区中的字符串的当前逻辑长度，不包括终止 null。 `CStringT` 当字符串的长度更改时，更新此字段。 在分配 `CStringData` 结构时，您的字符串管理器必须将此字段设置为零。 重新分配 `CStringData` 结构时，自定义字符串管理器必须将此字段保持不变。

- [nAllocLength](../atl-mfc-shared/reference/cstringdata-class.md#nalloclength) 此字段包含可在不重新分配它的情况下存储在此字符串缓冲区中的终止 null)  (的最大字符数。 只要 `CStringT` 需要增加字符串的逻辑长度，它将首先检查此字段，以确保缓冲区中有足够的空间。 如果检查失败，则 `CStringT` 调入自定义字符串管理器以重新分配缓冲区。 在分配或重新分配 `CStringData` 结构时，必须将此字段至少设置为 [IAtlStringMgr：： Allocate](../atl-mfc-shared/reference/iatlstringmgr-class.md#allocate)或 [IAtlStringMgr：：](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate)Allocate 的 *nChars* 参数中所请求的字符数。 如果缓冲区中的空间超出了所请求的数量，则可以设置此值以反映可用空间的实际数量。 这允许 `CStringT` 增加字符串以填充整个已分配空间，然后必须回调字符串管理器以重新分配缓冲区。

- [nRefs](../atl-mfc-shared/reference/cstringdata-class.md#nrefs) 此字段包含字符串缓冲区的当前引用计数。 如果值为1，则的单个实例 `CStringT` 将使用缓冲区。 此外，允许实例读取和修改缓冲区的内容。 如果值大于1，则多个实例 `CStringT` 可以使用缓冲区。 由于字符缓冲区是共享的，因此 `CStringT` 实例只能读取缓冲区的内容。 若要修改内容， `CStringT` 首先会生成缓冲区的副本。 如果该值为负数，则仅有一个实例 `CStringT` 使用缓冲区。 在这种情况下，缓冲区被视为已锁定。 当 `CStringT` 实例使用锁定缓冲区时，任何其他实例都不 `CStringT` 能共享该缓冲区。 相反，这些实例在操作内容之前会创建缓冲区的副本。 此外， `CStringT` 使用锁定缓冲区的实例不会尝试共享任何其他分配给它的实例的缓冲区 `CStringT` 。 在这种情况下， `CStringT` 实例会将其他字符串复制到锁定的缓冲区中。

   在分配 `CStringData` 结构时，必须设置此字段，以反映允许用于缓冲区的共享类型。 对于大多数实现，请将此值设置为1。 这允许常见的写入时复制共享行为。 但是，如果字符串管理器不支持共享字符串缓冲区，请将此字段设置为锁定状态。 这将强制 `CStringT` 只将此缓冲区用于 `CStringT` 分配它的实例。

## <a name="see-also"></a>请参阅

[内存管理与 CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)
