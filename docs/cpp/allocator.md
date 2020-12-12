---
description: 了解详细信息： `allocator`
title: 分配器
ms.date: 03/21/2019
f1_keywords:
- allocator_cpp
helpviewer_keywords:
- __declspec keyword [C++], allocator
- allocator __declspec keyword
ms.openlocfilehash: 20ca879259c49f01f5283a867b4e562cfddcc058
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97288264"
---
# `allocator`

**Microsoft 专用**

**`allocator`** 可以将声明说明符应用于自定义内存分配函数，以便通过 Windows (ETW) 的事件跟踪使分配可见。

## <a name="syntax"></a>语法

> **`__declspec(allocator)`**

## <a name="remarks"></a>备注

Visual Studio 中的本机内存探查器的工作原理是在运行时收集发送的分配 ETW 事件数据。 CRT 和 Windows SDK 中的分配器在源级别上注释，因此可以捕获其分配数据。 如果你正在编写自己的分配器，则可使用修饰返回指向新分配的堆内存的指针的所有函数 `__declspec(allocator)` ，如以下如此 mymalloc 示例所示：

```cpp
__declspec(allocator) void* myMalloc(size_t size)
```

有关详细信息，请参阅 [在 Visual Studio 中度量内存使用情况](/visualstudio/profiling/memory-usage) 和 [自定义本机 ETW 堆事件](/visualstudio/profiling/custom-native-etw-heap-events)。

**结束 Microsoft 专用**
