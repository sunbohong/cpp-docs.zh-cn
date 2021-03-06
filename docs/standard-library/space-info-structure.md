---
description: 了解详细信息： space_info 结构
title: space_info 结构
ms.date: 09/10/2018
f1_keywords:
- filesystem/std::tr2::sys::space_info
ms.assetid: f2b35b42-06ff-45bd-8617-39a0f5358a54
ms.openlocfilehash: 254866a0eb225b4ed7bcfe4e06a734c5c9d0e3ee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97153871"
---
# <a name="space_info-structure"></a>space_info 结构

保存有关卷的信息。

## <a name="syntax"></a>语法

```cpp
struct space_info
{
    uintmax_t capacity;
    uintmax_t free;
    uintmax_t available;
};
```

## <a name="members"></a>成员

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|`unsigned long long capacity`|表示卷可以表示的字节总数。|
|`unsigned long long free`|表示不用于表示卷上数据的字节数。|
|`unsigned long long available`|表示可用于表示卷上数据的字节数。|

## <a name="requirements"></a>要求

**标头：**\<filesystem>

**命名空间：** std::experimental::filesystem

## <a name="see-also"></a>请参阅

[标头文件引用](../standard-library/cpp-standard-library-header-files.md)\
[\<filesystem>](../standard-library/filesystem.md)\
[文件系统导航 (C++)](../standard-library/file-system-navigation.md)
