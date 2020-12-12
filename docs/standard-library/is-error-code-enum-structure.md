---
description: 了解详细信息： is_error_code_enum 结构
title: is_error_code_enum 结构
ms.date: 11/04/2016
f1_keywords:
- future/std::is_error_code_enum
ms.assetid: 84ae4b99-66d2-41ba-9b50-645fcbe14630
ms.openlocfilehash: 0de1d5562fd59e72e43c5844421f4ce6b30fe7c6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97231116"
---
# <a name="is_error_code_enum-structure"></a>is_error_code_enum 结构

指示 [future_errc](../standard-library/future-enums.md#future_errc) 适合存储 [error_code](../standard-library/error-code-class.md) 的专用化。

## <a name="syntax"></a>语法

```cpp
template <>
struct is_error_code_enum<Future_errc> : public true_type;
```

## <a name="requirements"></a>要求

**标头：**\<future>

**命名空间:** std

## <a name="see-also"></a>请参阅

[标头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[\<future>](../standard-library/future.md)
