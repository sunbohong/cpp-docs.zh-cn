---
description: 了解详细信息：使用一个存储过程中的多个结果集
title: 使用一个存储过程返回的多个结果集
ms.date: 10/24/2018
helpviewer_keywords:
- stored procedures, returning result sets
- multiple result sets
ms.assetid: c450c12c-a76c-4ae4-9675-071a41eeac05
ms.openlocfilehash: 8e6b7a51635caf9ddfd86dddcad0e2a3f94bb7dd
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319113"
---
# <a name="using-multiple-result-sets-from-one-stored-procedure"></a>使用一个存储过程返回的多个结果集

大多数存储过程返回多个结果集。 此类存储过程通常包括一个或多个 select 语句。 使用者需要考虑这个包含来处理所有结果集。

## <a name="to-handle-multiple-result-sets"></a>处理多个结果集

1. 创建一个 `CCommand` 类，将其 `CMultipleResults` 用作模板参数，并使用所选的访问器创建，通常为动态或手动访问器。 如果使用其他类型的访问器，则可能无法确定每个行集的输出列。

1. 照常执行存储过程并绑定列 (参阅 [如何获取数据？](../../data/oledb/fetching-data.md)) 。

1. 使用数据。

1. 对 `GetNextResult` 类调用 `CCommand` 。 如果有另一个结果行集可用，则 `GetNextResult` 返回 S_OK 并且如果使用手动访问器，则应重新绑定列。 如果 `GetNextResult` 返回错误，则没有其他结果集可用。

## <a name="see-also"></a>请参阅

[使用存储过程](../../data/oledb/using-stored-procedures.md)
