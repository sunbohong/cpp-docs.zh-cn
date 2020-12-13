---
description: 了解详细信息： _fullpath_dbg、_wfullpath_dbg
title: _fullpath_dbg、_wfullpath_dbg
ms.date: 11/04/2016
api_name:
- _wfullpath_dbg
- _fullpath_dbg
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
- wfullpath_dbg
- _wfullpath_dbg
- _fullpath_dbg
- fullpath_dbg
helpviewer_keywords:
- _fullpath_dbg function
- relative file paths
- absolute paths
- fullpath_dbg function
- _wfullpath_dbg function
- wfullpath_dbg function
ms.assetid: 81f72f85-07da-4f5c-866a-598e0fb03f6b
ms.openlocfilehash: a006533a6641110f1f94ca442743533c18c2aebb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97334164"
---
# <a name="_fullpath_dbg-_wfullpath_dbg"></a>_fullpath_dbg、_wfullpath_dbg

版本的 [_fullpath，_wfullpath](fullpath-wfullpath.md) 使用 **malloc** 的调试版本来分配内存。

## <a name="syntax"></a>语法

```C
char *_fullpath_dbg(
   char *absPath,
   const char *relPath,
   size_t maxLength,
   int blockType,
   const char *filename,
   int linenumber
);
wchar_t *_wfullpath_dbg(
   wchar_t *absPath,
   const wchar_t *relPath,
   size_t maxLength,
   int blockType,
   const char *filename,
   int linenumber
);
```

### <a name="parameters"></a>parameters

*absPath*<br/>
指向包含绝对或完整路径名称的缓冲区的指针或 **NULL**。

*relPath*<br/>
相对路径名称。

*maxLength*<br/>
绝对路径名称缓冲区 (*absPath*) 的最大长度。 对于 **_fullpath** ，此长度以字节为单位，但是以宽字符表示 **`wchar_t`** **_wfullpath** 的 () 。

*blockType*<br/>
内存块的请求类型： **_CLIENT_BLOCK** 或 **_NORMAL_BLOCK**。

*filename*<br/>
指向已请求分配操作的源文件名的指针或 **NULL**。

*linenumber*<br/>
请求分配操作所在的源文件中的行号或 **NULL**。

## <a name="return-value"></a>返回值

每个函数都返回指向包含绝对路径名 (*absPath*) 的缓冲区的指针。 例如，如果在 *relPath* 中传递的值包含一个无效或无法找到的驱动器号，或者创建的绝对路径名 (*AbsPath*) 大于 *maxLength* 的长度) 该函数返回 **NULL**，则为。 (

## <a name="remarks"></a>备注

**_Fullpath_dbg** 和 **_wfullpath_dbg** 函数与 **_fullpath** 和 **_wfullpath** 相同，不同之处在于，定义 **_DEBUG** 时，如果将 **NULL** 作为第一个参数传递，则这些函数将使用 **malloc** **_malloc_dbg** 的调试版本来分配内存。 有关 **_malloc_dbg** 的调试功能的信息，请参阅 [_malloc_dbg](malloc-dbg.md)。

在大多数情况下，无需显式调用这些函数。 您可以改为定义 **_CRTDBG_MAP_ALLOC** 标志。 定义 **_CRTDBG_MAP_ALLOC** 时，对 **_fullpath** 和 **_wfullpath** 的调用将分别重新映射到 **_fullpath_dbg** 和 **_wfullpath_dbg**，并将 *blockType* 设置为 **_NORMAL_BLOCK**。 因此，无需显式调用这些函数，除非你希望将堆块标记为 **_CLIENT_BLOCK**。 有关详细信息，请参阅 [调试堆上的块类型](/visualstudio/debugger/crt-debug-heap-details)。

### <a name="generic-text-routine-mappings"></a>一般文本例程映射

|Tchar.h 例程|未定义 _UNICODE 和 _MBCS|已定义 _MBCS|已定义 _UNICODE|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tfullpath_dbg**|**_fullpath_dbg**|**_fullpath_dbg**|**_wfullpath_dbg**|

## <a name="requirements"></a>要求

|函数|必需的标头|
|--------------|---------------------|
|**_fullpath_dbg**|\<crtdbg.h>|
|**_wfullpath_dbg**|\<crtdbg.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="see-also"></a>请参阅

[文件处理](../../c-runtime-library/file-handling.md)<br/>
[_fullpath、_wfullpath](fullpath-wfullpath.md)<br/>
[堆分配函数的调试版本](/visualstudio/debugger/debug-versions-of-heap-allocation-functions)<br/>
