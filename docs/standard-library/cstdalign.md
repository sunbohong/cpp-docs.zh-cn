---
description: 了解详细信息： &lt; cstdalign&gt;
title: '&lt;cstdalign&gt;'
ms.date: 07/11/2019
f1_keywords:
- <cstdalign>
- cstdalign
- __alignas_is_defined
- __alignof_is_defined
helpviewer_keywords:
- cstdalign header
- __alignas_is_defined
- __alignof_is_defined
ms.assetid: 9d570924-d299-4225-9a58-8c4c820f5903
ms.openlocfilehash: 149893b33ead3e66223b9124ff7c1b6346929799
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324743"
---
# <a name="ltcstdaligngt"></a>&lt;cstdalign&gt;

在某些 c + + 标准库实现中，此标头包含 C 标准库标头 \<stdalign.h> ，并将关联名称添加到 `std` 命名空间。 由于该标头未在 MSVC 中实现，因此 \<cstdalign> 标头定义兼容性宏 `__alignas_is_defined` 和 `__alignof_is_defined` 。

> [!NOTE]
> 因为 \<stdalign.h> 标头定义了作为 c + + 中的关键字的宏，所以它不起作用。 \<stdalign.h>C + + 中弃用了标头。 \<cstdalign>标头已在 c + + 17 中弃用，并已在草案 c + + 20 标准中删除。

## <a name="requirements"></a>要求

**标头：**\<cstdalign>

**命名空间:** std

## <a name="macros"></a>宏

| 宏 | 描述 |
| - | - |
| `__alignas_is_defined` | 可扩展到整数常数1的 C 兼容性宏。 |
| `__alignof_is_defined` | 可扩展到整数常数1的 C 兼容性宏。 |

## <a name="see-also"></a>请参阅

[标头文件引用](cpp-standard-library-header-files.md)\
[C + + 标准库概述](cpp-standard-library-overview.md)\
[C + + 标准库中的线程安全](thread-safety-in-the-cpp-standard-library.md)
