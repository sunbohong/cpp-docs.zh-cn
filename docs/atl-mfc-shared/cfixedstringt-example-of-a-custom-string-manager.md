---
description: 了解详细信息： CFixedStringT：自定义字符串管理器示例
title: CFixedStringT：自定义字符串管理器的示例
ms.date: 11/04/2016
helpviewer_keywords:
- CFixedStringT class, using a custom string manager
ms.assetid: 1cf11fd7-51b8-4b94-87af-02bc25f47dd6
ms.openlocfilehash: c9af2530500ad5972c01d063116e7ac981109493
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97142501"
---
# <a name="cfixedstringt-example-of-a-custom-string-manager"></a>CFixedStringT：自定义字符串管理器的示例

ATL 库实现类 [CFixedStringT](../atl-mfc-shared/reference/cfixedstringt-class.md)使用的自定义字符串管理器的一个示例，名为 **CFixedStringMgr**。 `CFixedStringT` 派生自 [CStringT](../atl-mfc-shared/reference/cstringt-class.md) ，并实现一个字符串，该字符串将其字符数据作为对象本身的一部分分配， `CFixedStringT` 前提是该字符串小于的模板参数指定的长度 `t_nChars` `CFixedStringT` 。 利用此方法，除非字符串的长度超出固定缓冲区的大小，否则字符串根本不需要堆。 由于不 `CFixedStringT` 会始终使用堆来分配其字符串数据，因此不能将其 `CAtlStringMgr` 用作字符串管理器。 它使用自定义字符串管理器 (`CFixedStringMgr`) ，实现 [IAtlStringMgr](../atl-mfc-shared/reference/iatlstringmgr-class.md) 接口。 此接口在 [ (高级方法) 的自定义字符串管理器的实现 ](../atl-mfc-shared/implementation-of-a-custom-string-manager-advanced-method.md)中进行了讨论。

的构造函数 `CFixedStringMgr` 采用三个参数：

- *pData：* 指向要使用的固定 `CStringData` 结构的指针。

- *nChars：* 结构可容纳的最大字符数 `CStringData` 。

- *pMgr：* 指向 `IAtlStringMgr` "备份字符串管理器" 的接口的指针。

构造函数将 *pData* 和 *pMgr* 的值存储在各自的成员变量中 (`m_pData` 和 `m_pMgr`) 。 然后，它将缓冲区的长度设置为零，可用长度等于固定缓冲区的最大大小，并将引用计数设置为-1。 引用计数值指示缓冲区已锁定，并使用此实例 `CFixedStringMgr` 作为字符串管理器。

将缓冲区标记为锁定会阻止其他 `CStringT` 实例持有对缓冲区的共享引用。 如果 `CStringT` 允许其他实例共享缓冲区，则 `CFixedStringT` 当其他字符串仍在使用缓冲区时，将删除包含的缓冲区。

`CFixedStringMgr` 是接口的完全实现 `IAtlStringMgr` 。 分别讨论了每种方法的实现。

## <a name="implementation-of-cfixedstringmgrallocate"></a>CFixedStringMgr：： Allocate 的实现

`CFixedStringMgr::Allocate`第一次实现将检查是否请求的字符串大小小于或等于) 中存储的固定 (缓冲区的大小 `m_pData` 。 如果固定缓冲区足够大，则 `CFixedStringMgr` 锁定长度为零的固定缓冲区。 只要字符串长度不超过固定缓冲区的大小， `CStringT` 就不需要重新分配缓冲区。

如果请求的字符串大小大于固定缓冲区，则会将 `CFixedStringMgr` 请求转发到备份字符串管理器。 建议将备份字符串管理器分配给堆。 但是，在返回此缓冲区之前，会 `CFixedStringMgr` 锁定缓冲区，并将缓冲区的字符串管理器指针替换为指向对象的指针 `CFixedStringMgr` 。 这可确保通过将调入，尝试重新分配或释放缓冲区 `CStringT` `CFixedStringMgr` 。

## <a name="implementation-of-cfixedstringmgrreallocate"></a>CFixedStringMgr：：重新分配的实现

的实现 `CFixedStringMgr::ReAllocate` 非常类似于的实现 `Allocate` 。

如果要重新分配的缓冲区为固定缓冲区，并且所请求的缓冲区大小小于固定缓冲区，则不会执行任何分配。 但是，如果要重新分配的缓冲区不是固定缓冲区，则它必须是使用备份管理器分配的缓冲区。 在这种情况下，备份管理器用于重新分配缓冲区。

如果要重新分配的缓冲区为固定缓冲区，并且新缓冲区大小太大而无法容纳在固定缓冲区内，则 `CFixedStringMgr` 使用备份管理器分配新的缓冲区。 然后，固定缓冲区的内容将被复制到新的缓冲区中。

## <a name="implementation-of-cfixedstringmgrfree"></a>CFixedStringMgr：： Free 的实现

的实现 `CFixedStringMgr::Free` 遵循与和相同的模式 `Allocate` `ReAllocate` 。 如果要释放的缓冲区为固定缓冲区，则该方法会将其设置为长度为零的锁定缓冲区。 如果要释放的缓冲区是使用备份管理器分配的，则 `CFixedStringMgr` 使用备份管理器释放它。

## <a name="implementation-of-cfixedstringmgrclone"></a>CFixedStringMgr：： Clone 的实现

的实现 `CFixedStringMgr::Clone` 始终返回指向备份管理器而不是自身的指针 `CFixedStringMgr` 。 发生这种情况的原因是，的每个实例 `CFixedStringMgr` 只能与的单个实例相关联 `CStringT` 。 `CStringT`尝试克隆管理器的任何其他实例都应改为获取备份管理器。 这是因为备份管理器支持共享。

## <a name="implementation-of-cfixedstringmgrgetnilstring"></a>CFixedStringMgr：： GetNilString 的实现

的实现 `CFixedStringMgr::GetNilString` 返回固定缓冲区。 由于和的一对一对应关系，因此的一个 `CFixedStringMgr` `CStringT` 指定实例 `CStringT` 绝不会同时使用多个缓冲区。 因此，永远不需要同时使用零字符串和实际字符串缓冲区。

每次未使用固定缓冲区时， `CFixedStringMgr` 都将确保用零长度对其进行初始化。 这允许将其用作 nil 字符串。 作为附加的奖金， `nAllocLength` 固定缓冲区的成员始终设置为固定缓冲区的完整大小。 这意味着， `CStringT` 即使对于 nil 字符串，也可以在不调用 [IAtlStringMgr：：重新分配](../atl-mfc-shared/reference/iatlstringmgr-class.md#reallocate)的情况下增大字符串。

## <a name="requirements"></a>要求

**标头：** cstringt

## <a name="see-also"></a>请参阅

[内存管理与 CStringT](../atl-mfc-shared/memory-management-with-cstringt.md)
