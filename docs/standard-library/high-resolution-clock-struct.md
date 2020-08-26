---
title: high_resolution_clock struct |Microsoft Docs
ms.custom: ''
ms.date: 05/22/2018
ms.technology: cpp-standard-libraries
ms.topic: reference
f1_keywords:
- chrono/std::chrono::high_resolution_clock
dev_langs:
- C++
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: a79cb91a6b0e6ca633540fd37f7a0e1ece53b712
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88845778"
---
# <a name="steady_clock-struct"></a>steady_clock 结构

表示一个 *high_resolution* 时钟。

## <a name="syntax"></a>语法

```cpp
class high_resolution_clock
```

## <a name="members"></a>成员

### <a name="typedefs"></a>Typedef

|名称|说明|
|----------|-----------------|
|`duration`|`nanoseconds`在中定义的的同义词 \<chrono> 。|
|`period`|`nano`在中定义的的同义词 \<ratio> 。|
|`rep`|的同义词 **`long long`** ，用于表示的包含实例化中的时钟计时周期数 `duration` 。|
|`time_point`|`chrono::time_point<high_resolution_clock>` 的同义词。|

## <a name="functions"></a>函数

|名称|说明|
|-|-|
|`now`|返回当前时间作为 `time_point` 值。|

## <a name="constants"></a>常量

|名称|说明|
|----------|-----------------|
|`is_steady`|保存 **`true`** 。 `high_resolution_clock` 是*稳定的*。|
