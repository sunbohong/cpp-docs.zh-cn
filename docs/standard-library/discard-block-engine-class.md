---
description: 了解详细信息： discard_block_engine 类
title: discard_block_engine 类
ms.date: 11/04/2016
f1_keywords:
- random/std::discard_block_engine
helpviewer_keywords:
- discard_block_engine class
ms.assetid: aa84808e-38fe-4fa0-9f73-d5b9a653345b
ms.openlocfilehash: 0879dacac70afc78a9c77314ce5042580c6cbb39
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97324511"
---
# <a name="discard_block_engine-class"></a>discard_block_engine 类

通过丢弃由其基引擎返回的值，生成随机序列。

## <a name="syntax"></a>语法

```cpp
template <class Engine, size_t P, size_t R>
class discard_block_engine;
```

### <a name="parameters"></a>parameters

*搜索引擎优化*\
基引擎类型。

*H-p*\
**块大小**。 每个块中的值数。

*迅驰*\
**已使用的块**。 已使用的每个块中的值数。 其余部分将被丢弃 (`P`  -  `R`) 。 **前提条件**： `0 < R ≤ P`

## <a name="members"></a>成员

`discard_block_engine::discard_block_engine`\
`discard_block_engine::base`\
`discard_block_engine::base_type`\
`discard_block_engine::discard`\
`discard_block_engine::operator()`\
`discard_block_engine::seed`

有关引擎成员的详细信息，请参阅 [\<random>](../standard-library/random.md) 。

## <a name="remarks"></a>备注

此类模板通过丢弃由其基引擎返回的某些值，来描述生成值的引擎适配器。

## <a name="requirements"></a>要求

**标头：**\<random>

**命名空间:** std

## <a name="see-also"></a>请参阅

[\<random>](../standard-library/random.md)
