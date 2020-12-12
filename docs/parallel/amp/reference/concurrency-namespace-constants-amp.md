---
description: '了解详细信息：并发命名空间常量 (AMP) '
title: 并发命名空间常量 (AMP)
ms.date: 11/04/2016
f1_keywords:
- amp/Concurrency::HLSL_MAX_NUM_BUFFERS
- amp/Concurrency::MODULENAME_MAX_LENGTH
ms.assetid: 13a8e8cd-2eec-4e60-a91d-5d271072747b
ms.openlocfilehash: f8a2cd10aa2701bda24f7017704dce59c5609835
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122221"
---
# <a name="concurrency-namespace-constants-amp"></a>并发命名空间常量 (AMP)

[HLSL_MAX_NUM_BUFFERS](#hlsl_max_num_buffers)\
[MODULENAME_MAX_LENGTH](#modulename_max_length)

## <a name="hlsl_max_num_buffers-constant"></a><a name="hlsl_max_num_buffers"></a> HLSL_MAX_NUM_BUFFERS 常量

DirectX 允许的最大缓冲区数。

```cpp
static const UINT HLSL_MAX_NUM_BUFFERS = 64 + 128;
```

## <a name="modulename_max_length-constant"></a><a name="modulename_max_length"></a> MODULENAME_MAX_LENGTH 常量

存储模块名称的最大长度。 此值必须在编译器和运行时上相同。

```cpp
static const UINT MODULENAME_MAX_LENGTH = 1024;
```

## <a name="see-also"></a>请参阅

[并发命名空间 (C++ AMP) ](concurrency-namespace-cpp-amp.md)
