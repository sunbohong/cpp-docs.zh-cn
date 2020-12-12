---
description: 了解详细信息： steady_clock 结构
title: steady_clock 结构
ms.date: 05/22/2018
f1_keywords:
- chrono/std::chrono::steady_clock
ms.assetid: 970d12ec-fc80-4391-a2f7-b57b2aec668d
ms.openlocfilehash: 066a98f4eba6670e640e9fcc9b79eb017859a3d2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97169068"
---
# <a name="steady_clock-struct"></a>steady_clock 结构

表示 *稳定* 时钟。

## <a name="syntax"></a>语法

```cpp
struct steady_clock;
```

## <a name="remarks"></a>备注

在 Windows 上， `steady_clock` 包装 `QueryPerformanceCounter` 函数。

如果首次调用 `now` 返回的值始终小于或等于后续调用 `now` 返回的值，则为单调时钟。 如果它是单调时钟并且时钟计时周期之间的时间是常量，则为稳定时钟。

`high_resolution_clock` 是的 typedef `steady_clock` 。

### <a name="public-typedefs"></a>公共 typedef

|名称|描述|
|----------|-----------------|
|`steady_clock::duration`|`nanoseconds`在中定义的的同义词 \<chrono> 。|
|`steady_clock::period`|`nano`在中定义的的同义词 \<ratio> 。|
|`steady_clock::rep`|的同义词 **`long long`** ，用于表示的包含实例化中的时钟计时周期数 `duration` 。|
|`steady_clock::time_point`|`chrono::time_point<steady_clock>` 的同义词。|

## <a name="public-functions"></a>公共函数

|函数|描述|
|--------------|-----------------|
|`now`|返回当前时间作为 `time_point` 值。|

## <a name="public-constants"></a>公共常量

|名称|描述|
|----------|-----------------|
|`steady_clock::is_steady`|保存 **`true`** 。 `steady_clock` 是 *稳定的*。|

## <a name="requirements"></a>要求

**标头：**\<chrono>

**命名空间：** std::chrono

## <a name="see-also"></a>请参阅

- [头文件引用](../standard-library/cpp-standard-library-header-files.md)
- [\<chrono>](../standard-library/chrono.md)
- [system_clock 结构](../standard-library/system-clock-structure.md)
