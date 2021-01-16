---
title: setjmp
description: 适用于 setjmp 的 API 参考;这将保存程序的当前状态。
ms.date: 1/14/2021
api_name:
- setjmp
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
- ntoskrnl.exe
- api-ms-win-crt-private-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- setjmp
helpviewer_keywords:
- programs [C++], saving states
- current state
- setjmp function
ms.assetid: 684a8b27-e8eb-455b-b4a8-733ca1cbd7d2
ms.openlocfilehash: 0830cf253553523747a815efc950d4cf75b36647
ms.sourcegitcommit: 1cd8f8a75fd036ffa57bc70f3ca869042d8019d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/15/2021
ms.locfileid: "98242639"
---
# `setjmp`

保存程序的当前状态。

## <a name="syntax"></a>语法

```C
int setjmp(
   jmp_buf env
);
```

### <a name="parameters"></a>参数

*`env`*\
存储变量的环境。

## <a name="return-value"></a>返回值

保存堆栈环境后，返回 0。 如果 **`setjmp`** 由于 `longjmp` 调用而返回，则返回的 *值* 参数 `longjmp` ; 如果的 *值* 参数 `longjmp` 为0，则返回 **`setjmp`** 1。 无错误返回。

## <a name="remarks"></a>注解

**`setjmp`** 函数保存堆栈环境，你可以随后使用将其还原 `longjmp` 。 一起使用时， **`setjmp`** `longjmp` 提供一种方法来执行非本地 **`goto`** 。 它们通常用于将执行控制传递给之前调用的例程中的错误处理或恢复代码，而无需使用普通的调用或返回约定。

调用将 **`setjmp`** 当前堆栈环境保存在中 *`env`* 。 对的后续调用将 `longjmp` 还原保存的环境并将控件返回到紧靠在相应调用之后的点 **`setjmp`** 。 可供接收控件的例程访问的所有变量（寄存器变量除外）包含在调用 `longjmp` 时它们具有的值。

无法使用 **`setjmp`** 从本机到托管代码进行跳转。

**Microsoft 专用**

在 Windows 上的 Microsoft c + + 代码中， **`longjmp`** 使用与异常处理代码相同的堆栈展开语义。 可以安全地在可引发 c + + 异常的相同位置使用。 但是，这种用法并不是可移植的，并附带一些重要的注意事项。 有关详细信息，请参阅 [`longjmp`](longjmp.md)。

**结束 Microsoft 专用**

> [!NOTE]
> 在可移植的 c + + 代码中，不能假设 `setjmp` 并 `longjmp` 支持 c + + 对象语义。 具体而言， `setjmp` / `longjmp` 如果将和替换并 `setjmp` `longjmp` **`catch`** **`throw`** 将调用任何自动对象的任何非普通析构函数，则调用对的行为未定义。 在 c + + 程序中，建议使用 c + + 异常处理机制。

有关详细信息，请[参阅 `setjmp` 使用 `longjmp` 和](../../cpp/using-setjmp-longjmp.md)。

## <a name="requirements"></a>要求

|例程所返回的值|必需的标头|
|-------------|---------------------|
|**`setjmp`**|\<setjmp.h>|

有关兼容性的详细信息，请参阅[兼容性](../../c-runtime-library/compatibility.md)。

## <a name="example"></a>示例

请参阅的示例 [`_fpreset`](fpreset.md) 。

## <a name="see-also"></a>另请参阅

[进程和环境控制](../../c-runtime-library/process-and-environment-control.md)\
[`longjmp`](longjmp.md)
