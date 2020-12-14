---
description: 了解详细信息： messages_base 类
title: messages_base 类
ms.date: 11/04/2016
f1_keywords:
- xlocmes/std::messages_base
helpviewer_keywords:
- messages_base class
ms.assetid: 9aad38c6-4c13-445d-b096-364bd0836efb
ms.openlocfilehash: 45ea81b02bd15011c9f98b9364ea9918e248692a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97230583"
---
# <a name="messages_base-class"></a>messages_base 类

基类描述 **`int`** 消息目录的类型。

## <a name="syntax"></a>语法

```cpp
struct messages_base : locale::facet {
    typedef int catalog;
    explicit messages_base(size_t _Refs = 0)
};
```

## <a name="remarks"></a>备注

类型目录是类型的同义词，用于 **`int`** 描述消息中可能的返回值：： [do_open](../standard-library/messages-class.md#do_open)。

## <a name="requirements"></a>要求

**标头：**\<locale>

**命名空间:** std

## <a name="see-also"></a>请参阅

[C + + 标准库中的线程安全](../standard-library/thread-safety-in-the-cpp-standard-library.md)
