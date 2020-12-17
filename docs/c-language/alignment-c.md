---
title: 对齐 (C11)
description: 介绍 Microsoft Visual C 类型对齐方式
ms.date: 12/10/2020
helpviewer_keywords:
- _Alignof keyword [C]
- _Alignas keyword [C]
- memory, alignment
ms.openlocfilehash: 051987ae705f84d7d4972398f742143f14b53e2b
ms.sourcegitcommit: be469dd87453255b0e35e333712c8207b09b3dd4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2020
ms.locfileid: "97438889"
---
# <a name="alignment-c11"></a>对齐 (C11)

C 的低级功能之一是能够指定内存中对象的精确对齐方式，以最大限度利用硬件体系结构。

当数据存储在倍数为数据大小的地址中时，CPU 会更有效地读取和写入内存。 例如，如果数据存储在倍数为 4 的地址中，则会更有效地访问 4 字节整数。 如果数据未对齐，则 CPU 需要执行更多工作来访问数据。

默认情况下，编译器会根据数据的大小对齐数据：`char` 在 1 字节的边界上对齐，`short` 在 2 字节的边界上对齐，`int`、`long` 和 `float` 在 4 字节的边界上对齐，`double` 在 8 字节的边界上对齐，依次类推。

另外，通过将常用数据与处理器的缓存行大小对齐，可以提高缓存性能。 例如，如果你定义一个大小小于 32 个字节的结构，你可能希望使用 32 字节方式对齐以确保有效缓存该结构的实例。

通常，无需担心对齐方式。 编译器通常在基于目标处理器和数据大小的自然边界上对齐数据。 在 32 位处理器上，数据最多在 4 字节的边界上对齐，在 64 位处理器上，数据最多在 8 字节的边界对齐。 但是，在某些情况下，你可以通过指定数据结构的自定义对齐方式获得性能提升或节约内存。

使用 C11 关键字 `_Alignof` 来获取类型或变量的首选对齐方式，使用 `_Alignas` 来指定变量或用户定义类型的自定义对齐方式。

`<stdalign.h>` 中定义的便捷宏 `alignof` 和 `alignas` 分别映射到 `_Alignof` 和 `_Alignas`。 这些宏与 C++ 中使用的关键字匹配。 因此，如果你在两种语言之间共享任何代码，则使用宏（而不是 C 关键字）可能会对代码可移植性有所帮助。

## <a name="alignas-and-_alignas-c11"></a>`alignas` 和 `_Alignas` (C11)

使用 `alignas` 或 `_Alignas` 来指定变量或用户定义类型的自定义对齐方式。 它们可以应用于结构、联合、枚举或变量。

### <a name="alignas-syntax"></a>`alignas` 语法

```c
alignas(type)
alignas(constant-expression)
_Alignas(type)
_Alignas(constant-expression)
```

### <a name="remarks"></a>备注

`_Alignas` 不能在 typedef、位域、函数、函数参数或使用 `register` 说明符声明的对象的声明中使用。

指定幂为 2（如 1、2、4、8、16 等）的对齐方式。 不要使用小于类型大小的值。

结构和联合的对齐方式与任何成员的最大对齐方式相等。 在结构中添加填充字节，以确保满足各个成员的对齐要求。

如果声明中有多个 `alignas` 说明符（例如，具有多个成员的结构具有不同的 `alignas` 说明符），则结构的对齐方式将是最大的对齐方式。

### <a name="alignas-example"></a>`alignas` 实例

此示例使用便捷宏 `alignof`，因为它可移植到 C++。 如果使用 `_Alignof`，则行为相同。

```c
// Compile with /std:c11

#include <stdio.h>
#include <stdalign.h>

typedef struct 
{
    int value; // aligns on a 4-byte boundary. There will be 28 bytes of padding between value and alignas
    alignas(32) char alignedMemory[32]; // assuming a 32 byte friendly cache alignment
} cacheFriendly; // this struct will be 32-byte aligned because alignedMemory is 32-byte alligned and is the largest alignment specified in the struct

int main()
{
    printf("sizeof(cacheFriendly): %d\n", sizeof(cacheFriendly)); // 4 bytes for int value + 32 bytes for alignedMemory[] + padding to ensure  alignment
    printf("alignof(cacheFriendly): %d\n", alignof(cacheFriendly)); // 32 because alignedMemory[] is aligned on a 32-byte boundary

    /* output
        sizeof(cacheFriendly): 64
        alignof(cacheFriendly): 32
    */
}
```

## <a name="alignof-and-_alignof-c11"></a>`alignof` 和 `_Alignof` (C11)

`_Alignof` 返回指定类型的对齐方式（以字节为单位）。 它返回类型为 `size_t` 的值。

### <a name="alignof-syntax"></a>`alignof` 语法

```cpp
alignof(type)
_Alignof(type)
```

### <a name="alignof-example"></a>`alignof` 实例

此示例使用便捷宏 `alignof`，因为它可移植到 C++。 如果使用 `_Alignof`，则行为相同。

```c
// Compile with /std:c11

#include <stdalign.h>
#include <stdio.h>

int main()
{
    size_t alignment = alignof(short);
    printf("alignof(short) = %d\n", alignment); // 2
    printf("alignof(int) = %d\n", alignof(int)); // 4
    printf("alignof(long) = %d\n", alignof(long)); // 4
    printf("alignof(float) = %d\n", alignof(float)); // 4
    printf("alignof(double) = %d\n", alignof(double)); // 8

    typedef struct
    {
        int a;
        double b;
    } test;

    printf("alignof(test) = %d\n", alignof(test)); // 8 because that is the alignment of the largest element in the structure

    /* output
        
       alignof(short) = 2
       alignof(int) = 4
       alignof(long) = 4
       alignof(float) = 4
       alignof(double) = 8
       alignof(test) = 8
    */
}
```

## <a name="requirements"></a>要求

需要 [std:c++11](../build/reference/std-specify-language-standard-version.md) 或更高版本。

Windows SDK 版本 10.0.20201.0 或更高版本。 此版本当前是一个预览体验内部版本，你可以从 [Windows 预览体验预览版下载](https://www.microsoft.com/software-download/windowsinsiderpreviewSDK)中下载。 请参阅 [C11 和 C17：入门](https://devblogs.microsoft.com/cppblog/c11-and-c17-standard-support-arriving-in-msvc/#c11-and-c17-getting-started)，以了解有关安装和使用此 SDK 的说明。

## <a name="see-also"></a>另请参阅

[`/std`（指定语言标准版本）](../build/reference/std-specify-language-standard-version.md)\
[C++ `alignof` 和 `alignas`](../cpp/alignment-cpp-declarations.md#alignof-and-alignas)\
[数据对齐的编译器处理](../cpp/alignment-cpp-declarations.md#compiler-handling-of-data-alignment)