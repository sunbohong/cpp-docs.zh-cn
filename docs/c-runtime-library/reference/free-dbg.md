---
description: 了解详细信息： _free_dbg
title: _free_dbg
ms.date: 11/04/2016
api_name:
- _free_dbg
api_location:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _free_dbg
- free_dbg
helpviewer_keywords:
- memory blocks, deallocating
- freeing memory
- _free_dbg function
- free_dbg function
ms.assetid: fc5e8299-616d-48a0-b979-e037117278c6
ms.openlocfilehash: 4baba591349c197b301b0dcd11b1998adfc7a971
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314030"
---
# <a name="_free_dbg"></a>_free_dbg

释放堆中的内存块（仅限调试版本）。

## <a name="syntax"></a>语法

```C
void _free_dbg(
   void *userData,
   int blockType
);
```

### <a name="parameters"></a>parameters

*userData*<br/>
指向要释放的已分配内存块的指针。

*blockType*<br/>
要释放的已分配内存块的类型： **_CLIENT_BLOCK**、 **_NORMAL_BLOCK** 或 **_IGNORE_BLOCK**。

## <a name="remarks"></a>备注

**_Free_dbg** 函数是 [可用](free.md)函数的调试版本。 未定义 [_DEBUG](../../c-runtime-library/debug.md) 时，对 **_free_dbg** 的每个调用都将减少为 **免费** 调用。 **可用** 和 **_free_dbg** 在基本堆中释放内存块，但 **_free_dbg** 提供两个调试功能：能够在堆的链接列表中保留已释放的块，以便模拟内存不足的情况，并使用块类型参数来释放特定分配类型。

**_free_dbg** 在执行免费操作之前在所有指定的文件和块位置上执行有效性检查。 应用程序不应该提供此信息。 当释放内存块时，调试堆管理器自动检查用户部分两侧的缓冲区的完整性，如果发生覆盖，将发出错误报告。 如果设置了 [_crtDbgFlag](../../c-runtime-library/crtdbgflag.md)标志的 **_CRTDBG_DELAY_FREE_MEM_DF** 位字段，则会用值0xDD 填充已释放的块，并为其分配了 **_FREE_BLOCK** 块类型，并将其保留在堆的链接内存块列表中。

如果在释放内存时发生错误，则会在出现故障的情况下，使用操作系统中的信息设置 **errno** 。 有关详细信息，请参阅 [errno、_doserrno、_sys_errlist 和 _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)。

若要了解如何在基堆的调试版本中分配、初始化和管理内存块，请参阅 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)。 有关分配块类型及其使用方式的信息，请参阅[调试堆上的块类型](/visualstudio/debugger/crt-debug-heap-details)。 有关在应用程序的调试版本中调用标准堆函数及其调试版本之间差异的信息，请参阅[堆分配函数的调试版本](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**_free_dbg**|\<crtdbg.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

有关如何使用 **_free_dbg** 的示例，请参阅 [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)。

## <a name="see-also"></a>请参阅

[调试例程](../../c-runtime-library/debug-routines.md)<br/>
[_malloc_dbg](malloc-dbg.md)<br/>
