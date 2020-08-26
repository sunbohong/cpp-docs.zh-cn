---
title: /CLRSUPPORTLASTERROR（为 PInvoke 调用保留上次的错误代码）
ms.date: 11/04/2016
f1_keywords:
- /CLRSUPPORTLASTERROR
helpviewer_keywords:
- /CLRSUPPORTLASTERROR linker option
- -CLRSUPPORTLASTERROR linker option
ms.assetid: b7057990-4154-4b1d-9fc9-6236f7be7575
ms.openlocfilehash: 071846e18dfef6cad0b7c5fb983dac3f6c85a689
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88839161"
---
# <a name="clrsupportlasterror-preserve-last-error-code-for-pinvoke-calls"></a>/CLRSUPPORTLASTERROR（为 PInvoke 调用保留上次的错误代码）

默认情况下， **/CLRSUPPORTLASTERROR**将保留通过 P/Invoke 机制调用的函数的最后一个错误代码，该机制允许您通过使用 **/clr**编译的代码调用 dll 中的本机函数。

## <a name="syntax"></a>语法

```
/CLRSUPPORTLASTERROR{:NO | SYSTEMDLL}
```

## <a name="remarks"></a>备注

保留上一个错误代码表示性能下降。  如果你不希望对保留上一个错误代码产生性能影响，请与  **/CLRSUPPORTLASTERROR： NO**关联。

你可以通过链接 **/CLRSUPPORTLASTERROR： SYSTEMDLL**来最大程度地降低性能影响，后者仅保留系统 dll 中函数的最后一个错误代码。

> [!NOTE]
> 对于 CLR 代码在同一模块中使用的非托管函数，不支持保留上一个错误。

- 有关详细信息，请参阅 [/clr (公共语言运行时编译) ](clr-common-language-runtime-compilation.md)。

### <a name="to-set-this-linker-option-in-the-visual-studio-development-environment"></a>在 Visual Studio 开发环境中设置此链接器选项

1. 打开项目的“属性页”  对话框。 有关详细信息，请参阅[在 Visual Studio 中设置 C++ 编译器和生成属性](../working-with-project-properties.md)。

1. 单击“链接器”文件夹****。

1. 点击“命令行” **** 属性页。

1. 在 " **附加选项** " 框中键入选项。

### <a name="to-set-this-linker-option-programmatically"></a>以编程方式设置此链接器选项

- 请参阅 <xref:Microsoft.VisualStudio.VCProjectEngine.VCLinkerTool.AdditionalOptions%2A>。

## <a name="example"></a>示例

下面的示例定义一个本机 DLL，其中包含一个用于修改上一个错误的导出函数。

```cpp
// CLRSUPPORTLASTERROR_dll.cpp
// compile with: /LD
#include <windows.h>
#include <math.h>

#pragma unmanaged
__declspec(dllexport) double MySqrt(__int64 n) {
   SetLastError(DWORD(-1));
   return sqrt(double(n));
}
```

## <a name="example"></a>示例

下面的示例使用 DLL，演示了如何使用 **/CLRSUPPORTLASTERROR**。

```cpp
// CLRSUPPORTLASTERROR_client.cpp
// compile with: /clr CLRSUPPORTLASTERROR_dll.lib /link /clrsupportlasterror:systemdll
// processor: x86
#include <windows.h>
#include <wininet.h>
#include <stdio.h>
#include <math.h>

#pragma comment(lib, "wininet.lib")

double MySqrt(__int64 n);

#pragma managed
int main() {
   double   d = 0.0;
   __int64 n = 65;
   HANDLE  hGroup = NULL;
   GROUPID groupID;
   DWORD   dwSet = 127, dwGet = 37;

   SetLastError(dwSet);
   d = MySqrt(n);
   dwGet = GetLastError();

   if (dwGet == DWORD(-1))
      printf_s("GetLastError for application call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for application call failed (%d).\n",
             dwGet);

   hGroup = FindFirstUrlCacheGroup(0, CACHEGROUP_SEARCH_ALL,
                           0, 0, &groupID, 0);
   dwGet = GetLastError();
   if (dwGet == 183)
      printf_s("GetLastError for system call succeeded (%d).\n",
             dwGet);
   else
      printf_s("GetLastError for system call failed (%d).\n",
             dwGet);
}
```

```Output
GetLastError for application call failed (127).
GetLastError for system call succeeded (183).
```

## <a name="see-also"></a>另请参阅

[MSVC 链接器参考](linking.md)<br/>
[MSVC 链接器选项](linker-options.md)
