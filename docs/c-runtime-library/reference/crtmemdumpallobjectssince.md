---
description: 了解详细信息： _CrtMemDumpAllObjectsSince
title: _CrtMemDumpAllObjectsSince
ms.date: 11/04/2016
api_name:
- _CrtMemDumpAllObjectsSince
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
- CrtMemDumpAllObjectsSince
- _CrtMemDumpAllObjectsSince
helpviewer_keywords:
- _CrtMemDumpAllObjectsSince function
- CrtMemDumpAllObjectsSince function
ms.assetid: c48a447a-e6bb-475c-9271-a3021182a0dc
ms.openlocfilehash: e833543d3119b39a21b596af412a97f6991e4ef0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319633"
---
# <a name="_crtmemdumpallobjectssince"></a>_CrtMemDumpAllObjectsSince

从程序开始执行或从指定的堆状态转储堆中对象的信息（仅限调试版本）。

## <a name="syntax"></a>语法

```C
void _CrtMemDumpAllObjectsSince(
   const _CrtMemState *state
);
```

### <a name="parameters"></a>parameters

*state*<br/>
指向开始从其转储的堆状态的指针，或 **NULL**。

## <a name="remarks"></a>备注

**_CrtMemDumpAllObjectsSince** 函数以用户可读的形式转储在堆中分配的对象的调试标头信息。 应用程序可以使用转储信息来跟踪分配并检测内存问题。 未定义 [_DEBUG](../../c-runtime-library/debug.md) 时，将在预处理过程中删除对 **_CrtMemDumpAllObjectsSince** 的调用。

**_CrtMemDumpAllObjectsSince** 使用 *state* 参数的值来确定在何处启动转储操作。 若要开始从指定的堆状态转储， *state* 参数必须是指向 **_CrtMemState** 结构的指针，该结构已在调用 **_CrtMemDumpAllObjectsSince** 之前 [_CrtMemCheckpoint](crtmemcheckpoint.md)填充。 当 *state* 为 **NULL** 时，函数将从程序执行开始开始转储。

如果应用程序通过调用 [_CrtSetDumpClient](crtsetdumpclient.md)安装了转储挂钩函数，则每次 **_CrtMemDumpAllObjectsSince** 转储有关 **_CLIENT_BLOCK** 类型的块的信息时，它也会调用应用程序提供的转储函数。 默认情况下，内存转储操作中不包含内部 C 运行时块 (**_CRT_BLOCK**) 。 [_CrtSetDbgFlag](crtsetdbgflag.md)函数可用于打开 **_crtDbgFlag** 的 **_CRTDBG_CHECK_CRT_DF** 位以包含这些块。 此外，标记为已释放或已忽略的块（**_FREE_BLOCK**、**_IGNORE_BLOCK**）不包括在内存转储中。

有关堆状态函数和 **_CrtMemState** 结构的详细信息，请参阅 [堆状态报告函数](/visualstudio/debugger/crt-debug-heap-details)。 有关如何在基堆的调试版本中分配、初始化和管理内存块的详细信息，请参阅 [CRT Debug Heap Details](/visualstudio/debugger/crt-debug-heap-details)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**_CrtMemDumpAll-ObjectsSince**|\<crtdbg.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="libraries"></a>库

仅限 [C 运行时库](../../c-runtime-library/crt-library-features.md)的调试版本。

## <a name="example"></a>示例

有关如何使用 **_CrtMemDumpAllObjectsSince** 的示例，请参阅 [crt_dbg2](https://github.com/Microsoft/VCSamples/tree/master/VC2010Samples/crt/crt_dbg2)。

## <a name="see-also"></a>请参阅

[调试例程](../../c-runtime-library/debug-routines.md)<br/>
[_CRTDBG_CHECK_CRT_DF](../../c-runtime-library/crtdbgflag.md)<br/>
