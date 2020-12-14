---
description: 了解详细信息：测试提取错误
title: 测试提取错误
ms.date: 11/04/2016
helpviewer_keywords:
- extraction errors
ms.assetid: 6a681028-adba-4557-8f7b-f137932905f8
ms.openlocfilehash: c4a9b5c1ffe4f78718563b33e39012272cfb8042
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97259352"
---
# <a name="testing-for-extraction-errors"></a>测试提取错误

处理函数时出现的输出错误适用于输入流，请参阅[处理函数时出错](../standard-library/output-file-stream-member-functions.md)。 在提取过程测试是否有错误非常重要。 请看下面的语句：

```cpp
cin>> n;
```

如果 `n` 是一个带符号整数且使用大于 32,767 的值（最大允许值或 MAX_INT）设置流的 `fail` 位，则 `cin` 对象将不可用。 所有后续提取都会立即返回，不会存储任何值。

## <a name="see-also"></a>请参阅

[输入流](../standard-library/input-streams.md)
