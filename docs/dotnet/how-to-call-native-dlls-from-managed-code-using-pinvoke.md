---
description: 了解详细信息：如何：使用 PInvoke 从托管代码调用本机 Dll
title: 如何：使用 PInvoke 从托管代码调用本机 DLL
ms.custom: get-started-article
ms.date: 11/04/2016
helpviewer_keywords:
- platform invoke [C++], calling native DLLs
- interop [C++], calling native DLLs
- marshaling [C++], calling native DLLs
- data marshaling [C++], calling native DLLs
ms.assetid: 3273eb4b-38d1-4619-92a6-71bda542be72
ms.openlocfilehash: 915601aa813f1c5c14977c1492d6c675125c47be
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97335392"
---
# <a name="how-to-call-native-dlls-from-managed-code-using-pinvoke"></a>如何：使用 PInvoke 从托管代码调用本机 DLL

在非托管 Dll 中实现的函数可以使用平台调用 (P/Invoke) 功能从托管代码调用。 如果 DLL 的源代码不可用，则 P/Invoke 是用于互操作的唯一选项。 但是，与其他 .NET 语言不同，Visual C++ 提供了 P/Invoke 的替代方法。 有关详细信息，请参阅 [使用 c + + 互操作 (隐式 PInvoke) ](../dotnet/using-cpp-interop-implicit-pinvoke.md)。

## <a name="example"></a>示例

下面的代码示例使用 Win32 [GetSystemMetrics](/windows/win32/api/winuser/nf-winuser-getsystemmetrics) 函数来检索屏幕的当前分辨率（以像素为单位）。

对于仅使用内部类型作为参数和返回值的函数，不需要额外的工作。 其他数据类型（如函数指针、数组和结构）需要其他特性来确保正确的数据封送处理。

尽管这不是必需的，但最好使 P/Invoke 声明成为值类的静态成员，使它们不存在于全局命名空间中，如本示例中所示。

```cpp
// pinvoke_basic.cpp
// compile with: /clr
using namespace System;
using namespace System::Runtime::InteropServices;

value class Win32 {
public:
   [DllImport("User32.dll")]
   static int GetSystemMetrics(int);

   enum class SystemMetricIndex {
      // Same values as those defined in winuser.h.
      SM_CXSCREEN = 0,
      SM_CYSCREEN = 1
   };
};

int main() {
   int hRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CXSCREEN) );
   int vRes = Win32::GetSystemMetrics( safe_cast<int>(Win32::SystemMetricIndex::SM_CYSCREEN) );
   Console::WriteLine("screen resolution: {0},{1}", hRes, vRes);
}
```

## <a name="see-also"></a>请参阅

[在 c + + 中使用显式 PInvoke (DllImport 特性) ](../dotnet/using-explicit-pinvoke-in-cpp-dllimport-attribute.md)
