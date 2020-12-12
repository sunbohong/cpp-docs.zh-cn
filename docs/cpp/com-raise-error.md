---
description: 了解详细信息： _com_raise_error
title: _com_raise_error
ms.date: 11/04/2016
f1_keywords:
- _com_raise_error
helpviewer_keywords:
- _com_raise_error function
ms.assetid: a98226c2-c3fe-44f1-8ff5-85863de11cd6
ms.openlocfilehash: 81697b565104971d22da04a7b8b0e33a7f9255ac
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97178207"
---
# <a name="_com_raise_error"></a>_com_raise_error

**Microsoft 专用**

引发 [_com_error](../cpp/com-error-class.md) 以响应失败。

## <a name="syntax"></a>语法

```cpp
void __stdcall _com_raise_error(
   HRESULT hr,
   IErrorInfo* perrinfo = 0
);
```

#### <a name="parameters"></a>parameters

*小时*<br/>
HRESULT 信息。

*perrinfo*<br/>
`IErrorInfo` 对象。

## <a name="remarks"></a>备注

**_com_raise_error**（在中定义 \<comdef.h> ）可以替换为具有相同名称和原型的用户编写版本。 若要使用 `#import` 但不使用 C++ 异常处理，则可以执行此操作。 在这种情况下，用户版本的 **_com_raise_error** 可能决定执行 `longjmp` 或显示一个消息框，然后停止。 但不应返回用户版本，因为编译器 COM 支持代码不希望返回它。

你还可以使用 [_set_com_error_handler](../cpp/set-com-error-handler.md) 来替换默认的错误处理函数。

默认情况下，按如下所示定义 **_com_raise_error** ：

```cpp
void __stdcall _com_raise_error(HRESULT hr, IErrorInfo* perrinfo) {
   throw _com_error(hr, perrinfo);
}
```

**结束 Microsoft 专用**

## <a name="requirements"></a>要求

**标头：**\<comdef.h>

**Lib：** 如果 **wchar_t 是本机类型** 编译器选项，请使用 comsuppw.lib 或 comsuppwd.lib。 如果 **wchar_t 为 "本机" 类型** 为 "关"，请使用 comsupp.lib。 有关详细信息，请参阅 [/zc： wchar_t (Wchar_t 是本机类型) ](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)。

## <a name="see-also"></a>请参阅

[编译器 COM 全局函数](../cpp/compiler-com-global-functions.md)<br/>
[_set_com_error_handler](../cpp/set-com-error-handler.md)
