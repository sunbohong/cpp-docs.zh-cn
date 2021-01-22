---
description: 了解详细信息：延迟负载调用约定、参数和返回类型
title: 调用约定、参数和返回类型
ms.date: 01/19/2021
helpviewer_keywords:
- calling conventions, helper functions
- helper functions, calling conventions
- helper functions, return types
ms.openlocfilehash: 68817f2746abccf9ad6ae72c4f189fa29aa4c26f
ms.sourcegitcommit: 3d9cfde85df33002e3b3d7f3509ff6a8dc4c0a21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/21/2021
ms.locfileid: "98666922"
---
# <a name="delay-load-helper-calling-conventions-parameters-and-return-type"></a>延迟加载助手调用约定、参数和返回类型

延迟加载 helper 例程的原型是：

```C
FARPROC WINAPI __delayLoadHelper2(
    PCImgDelayDescr pidd,
    FARPROC * ppfnIATEntry
);
```

## <a name="parameters"></a>参数

*`pidd`*<br/>
**`const`** 指向的指针， `ImgDelayDescr` 该指针包含各种导入相关数据的偏移量、绑定信息的时间戳，以及提供有关描述符内容的进一步信息的一组属性。 目前只有一个属性，该属性 `dlattrRva` 指示描述符中的地址是相对虚拟地址。 有关详细信息，请参阅中的声明 *`delayimp.h`* 。

有关结构的定义 `PCImgDelayDescr` ，请参阅 [结构和常量定义](structure-and-constant-definitions.md)。

*`ppfnIATEntry`*<br/>
指向延迟加载导入地址表中的槽的指针 (IAT) 。 这是用导入函数的地址更新的槽。 Helper 例程需要存储返回到此位置的相同值。

## <a name="expected-return-values"></a>预期的返回值

如果函数运行成功，则返回导入函数的地址。

如果函数失败，则会引发结构化异常并返回0。 引发的异常有三种类型：

- 参数无效，如果未正确指定中的属性，则会发生这种情况 *`pidd`* 。

- `LoadLibrary` 在指定的 DLL 上失败。

- `GetProcAddress` 失败。

您负责处理这些异常。

## <a name="remarks"></a>注解

Helper 函数的调用约定是 **`__stdcall`** 。 返回值的类型不相关，因此 `FARPROC` 使用。 此函数具有 C 链接，这意味着它需要 `extern "C"` 在 c + + 代码中声明时进行包装。 `ExternC`此宏会为你处理此包装器。

将 helper 函数的返回值存储在传入的函数指针位置，除非你想要使用 helper 例程作为通知挂钩。 在这种情况下，由你的代码负责查找要返回的适当函数指针。 然后，链接器生成的 thunk 代码可将该返回值用作导入的实际目标并直接跳转到该目标。

## <a name="sample"></a>示例

下面的代码演示如何实现基本挂钩函数。

```C
FARPROC WINAPI delayHook(unsigned dliNotify, PDelayLoadInfo pdli)
{
    switch (dliNotify) {
        case dliStartProcessing :

            // If you want to return control to the helper, return 0.
            // Otherwise, return a pointer to a FARPROC helper function
            // that will be used instead, thereby bypassing the rest
            // of the helper.

            break;

        case dliNotePreLoadLibrary :

            // If you want to return control to the helper, return 0.
            // Otherwise, return your own HMODULE to be used by the
            // helper instead of having it call LoadLibrary itself.

            break;

        case dliNotePreGetProcAddress :

            // If you want to return control to the helper, return 0.
            // If you choose you may supply your own FARPROC function
            // address and bypass the helper's call to GetProcAddress.

            break;

        case dliFailLoadLib :

            // LoadLibrary failed.
            // If you don't want to handle this failure yourself, return 0.
            // In this case the helper will raise an exception
            // (ERROR_MOD_NOT_FOUND) and exit.
            // If you want to handle the failure by loading an alternate
            // DLL (for example), then return the HMODULE for
            // the alternate DLL. The helper will continue execution with
            // this alternate DLL and attempt to find the
            // requested entrypoint via GetProcAddress.

            break;

        case dliFailGetProc :

            // GetProcAddress failed.
            // If you don't want to handle this failure yourself, return 0.
            // In this case the helper will raise an exception
            // (ERROR_PROC_NOT_FOUND) and exit.
            // If you choose you may handle the failure by returning
            // an alternate FARPROC function address.

            break;

        case dliNoteEndProcessing :

            // This notification is called after all processing is done.
            // There is no opportunity for modifying the helper's behavior
            // at this point except by longjmp()/throw()/RaiseException.
            // No return value is processed.

            break;

        default :

            return NULL;
    }

    return NULL;
}

/*
and then at global scope somewhere:

ExternC const PfnDliHook __pfnDliNotifyHook2 = delayHook;
ExternC const PfnDliHook __pfnDliFailureHook2 = delayHook;
*/
```

## <a name="see-also"></a>另请参阅

[了解 Helper 函数](understanding-the-helper-function.md)
