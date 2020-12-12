---
description: 了解详细信息：当另一个表包含对该行的引用时更新该列
title: 当另一个表包含对该行的引用时更新列
ms.date: 10/24/2018
helpviewer_keywords:
- rowsets, column updates
ms.assetid: abb5db69-055d-431f-b12d-ad2940a661ba
ms.openlocfilehash: 5c4562aaaa435c9745bedd146c04c98158d50cc5
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97272612"
---
# <a name="updating-a-column-when-another-table-contains-a-reference-to-the-row"></a>当另一个表包含行引用时更新列

某些提供程序可以检测行中哪些列发生更改，但许多提供程序都不能。 因此，当存在对尝试更新的行的引用时，更新列可能导致错误。 若要解决此问题，请创建单独的取值函数，只保存要更改的列。 将该访问器的数量传递给 `SetData` 。

## <a name="see-also"></a>请参阅

[使用访问器](../../data/oledb/using-accessors.md)
