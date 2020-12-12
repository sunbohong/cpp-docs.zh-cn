---
description: 了解详细信息：增强简单的 Read-Only 提供程序
title: 增强简单的只读提供程序
ms.date: 10/26/2018
helpviewer_keywords:
- read-only poviders [C++]
- IRowsetLocate class
- IRowsetLocate class, adding to OLE DB template providers
- simple read-only poviders [C++]
ms.assetid: cba0e09f-44c1-41c1-9456-332aa13dc158
ms.openlocfilehash: 00a0ea4fb9b759447026353ba0d78c7c856b15ae
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97317631"
---
# <a name="enhancing-the-simple-read-only-provider"></a>增强简单的只读提供程序

本部分演示如何增强在上一部分中创建的 [简单只读提供程序](../../data/oledb/implementing-the-simple-read-only-provider.md) 。 `IRowsetLocateImpl` 为接口创建一个实现 `IRowsetLocate` ，并为你添加书签支持。

当你有一个有效的提供程序时，你可能想要对其进行增强，以使提供程序更新、处理事务或提高行提取算法的性能。 大多数提供程序增强都涉及到将接口添加到现有的 COM 对象。

以下主题中的示例通过将接口添加到来增强行提取机制 `IRowsetLocate` `CAgentRowset` 。 本主题介绍如何执行以下操作：

- [使 RCustomRowset 从 IRowsetLocate 继承](../../data/oledb/modifying-the-inheritance-of-rmyproviderrowset.md)。

- [动态确定返回给使用者的列](../../data/oledb/dynamically-determining-columns-returned-to-the-consumer.md)。

## <a name="see-also"></a>请参阅

[创建简单的 Read-Only 提供程序](../../data/oledb/creating-a-simple-read-only-provider.md)<br/>
