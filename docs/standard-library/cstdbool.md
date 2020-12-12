---
description: 了解详细信息： &lt; cstdbool&gt;
title: '&lt;cstdbool&gt;'
ms.date: 07/11/2019
f1_keywords:
- <cstdbool>
- cstdbool
helpviewer_keywords:
- cstdbool header
ms.assetid: 44ccb8b2-d808-4715-8097-58ba09ab33ed
ms.openlocfilehash: 0711c05ff136f90a701ff707976a172d2bcb1315
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324730"
---
# <a name="ltcstdboolgt"></a>&lt;cstdbool&gt;

包括 C 标准库标头 \<stdbool.h> 并将关联名称添加到 `std` 命名空间。

> [!NOTE]
> 因为 \<stdbool.h> 标头定义了作为 c + + 中的关键字的宏，所以它不起作用。 \<stdbool.h>C + + 中弃用了标头。 \<cstdbool>标头已在 c + + 17 中弃用，并已在草案 c + + 20 标准中删除。

## <a name="requirements"></a>要求

**标头：**\<cstdbool>

**命名空间:** std

## <a name="remarks"></a>备注

包括此标头可确保在命名空间中声明使用 C 标准库标头中的外部链接声明的名称 `std` 。

## <a name="see-also"></a>请参阅

[标头文件引用](cpp-standard-library-header-files.md)\
[C + + 标准库概述](cpp-standard-library-overview.md)\
[C + + 标准库中的线程安全](thread-safety-in-the-cpp-standard-library.md)
