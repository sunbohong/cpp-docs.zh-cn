---
title: 如何：在通用 Windows 平台应用中使用现有 C++ 代码
description: 在通用 Windows 平台应用中使用现有代码应用和库的方法。
ms.date: 09/04/2020
ms.assetid: 87e5818c-3081-42f3-a30d-3dca2cf0645c
ms.openlocfilehash: 1e946d588f1a14018ebb11a60b319c2d54658f25
ms.sourcegitcommit: 0df2b7ab4e81284c5248e4584767591dcc1950c3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "89609129"
---
# <a name="how-to-use-existing-c-code-in-a-universal-windows-platform-app"></a>如何：在通用 Windows 平台应用中使用现有 C++ 代码

可以通过多种方式在通用 Windows 平台 (UWP) 项目中使用现有的 c + + 代码。 某些方法不需要通过组件扩展重新编译代码 (c + +/CX) 启用 (也就是说，具有 `/ZW` 选项) ，还有一些操作。 可能需要在标准 c + + 中保存代码，或者为某些代码保留经典 Win32 编译环境。 你仍可以通过适当的体系结构选择来实现此目的。 假设你的所有代码都包含 UWP UI，以及向 c #、Visual Basic 和 JavaScript 调用方公开的类型。 此代码应位于 Windows 应用项目和 Windows 运行时组件项目中。 仅从 c + + (（包括 c + +/CX) ）调用的代码可以位于用 `/ZW` 选项或标准 c + + 项目进行编译的项目中。 不使用不允许的 Api 的仅二进制代码可以通过将其作为静态库链接来使用。 或者，你可以将应用作为内容打包，并将其加载到 DLL 中。

要在 UWP 环境中运行桌面程序，最简单的方法或许是使用桌面桥技术。 它们包括桌面应用程序转换器，它将现有应用程序打包为 UWP 应用，无需更改代码。 有关详细信息，请参阅[桌面桥](/windows/uwp/porting/desktop-to-uwp-root)。

本文的其余部分将讨论如何将 c + + 库 (Dll 和静态库移植到通用 Windows 平台) 。 你可能想要移植代码，以便可以将核心 c + + 逻辑与多个 UWP 应用一起使用。

UWP 应用在受保护的环境中运行。 因此，不允许许多可能危及平台安全的 Win32、COM 和 CRT API 调用。 `/ZW`编译器选项可检测此类调用并生成错误。 你可以使用应用程序上的应用认证工具包来检测调用不允许的 Api 的代码。 有关详细信息，请参见 [Windows 应用认证工具包](/windows/uwp/debug-test-perf/windows-app-certification-kit)。

如果源代码可用于库，则可以尝试消除不允许的 API 调用。 有关不允许的 Api 的列表，请参阅适用于 [UWP 应用的 Win32 和 COM api](/uwp/win32-and-com/win32-and-com-for-uwp-apps) 和 [通用 Windows 平台应用中不支持的 CRT 函数](../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md)。 可通过 [UWP 应用中的 Windows API 替代项](/uwp/win32-and-com/alternatives-to-windows-apis-uwp)，找到一些替代项。

如果只是尝试从通用 Windows 项目添加引用到经典桌面库，会收到一条错误消息，指出库不兼容。 如果是静态库，则可以通过将库 (*`.lib`* 文件) 添加到链接器输入（与在经典 Win32 应用程序中相同的方式）来链接到库。 如果只有二进制库可用，则这是唯一的选择。 静态库链接到应用的可执行文件。 但是，在 UWP 应用中使用的 Win32 DLL 必须通过将其包含在项目中并将其标记为内容来打包到应用中。 若要在 UWP 应用中加载 Win32 DLL，还必须调用， [`LoadPackagedLibrary`](/windows/win32/api/winbase/nf-winbase-loadpackagedlibrary) 而不是 `LoadLibrary` 或 `LoadLibraryEx` 。

如果你有 DLL 或静态库的源代码，则可以使用编译器选项将其重新编译为 UWP 项目 `/ZW` 。 然后，可以使用 **解决方案资源管理器**添加对它的引用，并在 c + + UWP 应用中使用它。 使用导出库链接 DLL。

若要向其他语言中的调用方公开功能，则可以将库转换为 Windows 运行时组件。 Windows 运行时组件与普通 Dll 的不同之处在于，它们包含以 *`.winmd`* .net 和 JavaScript 使用者要求的方式描述内容的文件格式的元数据。  若要向其他语言公开 API 元素，你可以添加 c + +/CX 构造（如 ref 类）并使其成为公共的。 在 Windows 10 及更高版本中，建议 [c + +/WinRT 库](https://github.com/microsoft/cppwinrt) 而不是 c + +/cx

前面的讨论不适用于 COM 组件，但必须以不同的方式进行处理。 如果 COM 服务器位于 EXE 或 DLL 中，则可以在通用 Windows 项目中使用它。 将其打包为 [免注册 COM 组件](/windows/win32/sbscs/creating-registration-free-com-objects)，将其作为内容文件添加到项目，并使用对其进行实例化 [`CoCreateInstanceFromApp`](/windows/win32/api/combaseapi/nf-combaseapi-cocreateinstancefromapp) 。 有关详细信息，请参阅[在 Windows 应用商店 C++ 项目中使用 Free-COM DLL](/archive/blogs/win8devsupport/using-free-com-dll-in-windows-store-c-project)。

如果要将现有 COM 库移植到 UWP，还可以将其转换为 Windows 运行时组件。 对于此类端口，建议使用 c + +/WinRT 库，但也可以使用 [ (WRL) 的 Windows 运行时 c + + 模板库 ](../windows/windows-runtime-cpp-template-library-wrl.md)。 WRL 已被弃用，并且它不支持 ATL 和 OLE 的所有功能。 这种端口是否可行取决于组件需要的 COM、ATL 和 OLE 功能。

无论选择哪种开发方案，都应注意一些宏定义。 你可以在代码中使用这些宏，以便在经典桌面 Win32 和 UWP 下有条件地编译代码。

```cpp
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PC_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_PHONE_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_APP)
#if WINAPI_FAMILY_PARTITION(WINAPI_PARTITION_DESKTOP)
```

这些语句分别适用于 UWP 应用、Windows Phone 应用商店应用、都适用或都不适用（仅针对经典 Win32 桌面）。 这些宏仅在8.1 和更高版本 Windows SDK 中可用。

本文包含以下过程：

- [在 UWP 应用中使用 Win32 DLL](#BK_Win32DLL)

- [在 UWP 应用中使用本机 C++ 静态库](#BK_StaticLib)

- [将 C++ 库移植到 Windows 运行时组件](#BK_WinRTComponent)

## <a name="using-a-win32-dll-in-a-uwp-app"></a><a name="BK_Win32DLL"></a> 在 UWP 应用中使用 Win32 DLL

为了获得更好的安全性和可靠性，通用 Windows 应用在受限的运行时环境中运行。 你不能像在经典 Windows 桌面应用程序中那样使用任何本机 DLL。 如果你有 DLL 的源代码，则可以移植此代码，以便使其在 UWP 上运行。 你首先更改几个项目设置和项目文件元数据，以将此项目标识为 UWP 项目。 你将使用选项重新编译库代码 `/ZW` ，这将启用 c + +/cx 由于与该环境相关联的更严格的控件，UWP 应用中不允许某些 API 调用。 有关详细信息，请参阅 [UWP 应用的 Win32 和 COM api](/uwp/win32-and-com/win32-and-com-for-uwp-apps)。

如果你的本机 DLL 使用 `__declspec(dllexport)` 导出函数，则可以通过将 DLL 重新编译为 UWP 项目，从 UWP 应用中调用这些函数。 例如，假设有一个名为 *Giraffe* 的 Win32 DLL 项目，该项目使用类似于以下标头文件的代码导出几个类及其方法：

```cpp
// giraffe.h
// Define GIRAFFE_EXPORTS when building this DLL
#pragma once

#ifdef GIRAFFE_EXPORTS
#define GIRAFFE_API __declspec(dllexport)
#else
#define GIRAFFE_API
#endif

GIRAFFE_API int giraffeFunction();

class Giraffe
{
    int id;
        Giraffe(int id_in);
    friend class GiraffeFactory;

public:
    GIRAFFE_API int GetID();
};

class GiraffeFactory
{
    static int nextID;

public:
    GIRAFFE_API GiraffeFactory();
    GIRAFFE_API static int GetNextID();
    GIRAFFE_API static Giraffe* Create();
};
```

以下代码文件：

```cpp
// giraffe.cpp
#include "pch.h"
#include "giraffe.h"

Giraffe::Giraffe(int id_in) : id(id_in)
{
}

int Giraffe::GetID()
{
    return id;
}

int GiraffeFactory::nextID = 0;

GiraffeFactory::GiraffeFactory()
{
    nextID = 0;
}

int GiraffeFactory::GetNextID()
{
    return nextID;
}

Giraffe* GiraffeFactory::Create()
{
    return new Giraffe(nextID++);
}

int giraffeFunction();
```

项目 (中的其他内容 *`pch.h`* ， *`dllmain.cpp`*) 是标准 Win32 项目模板的一部分。 此代码定义宏 `GIRAFFE_API` ，在 `__declspec(dllexport)` 定义时解析为 `GIRAFFE_EXPORTS` 。 也就是说，当项目生成为 DLL，而不是当客户端使用标题时，将定义此方法 *`giraffe.h`* 。 此 DLL 可以在 UWP 项目中使用，而无需更改源代码。 只需更改某些项目设置和属性。

当你具有使用公开函数的本机 DLL 时，以下过程适用 `__declspec(dllexport)` 。

### <a name="to-port-a-native-dll-to-the-uwp-without-creating-a-new-project"></a>若要在无需创建新项目的情况下将本机 DLL 移植到 UWP

1. 在 Visual Studio 中打开 DLL 项目。

1. 打开 DLL 项目的 " **项目属性** "，并将 **配置** 设置为 " **所有配置**"。

1. 在“项目属性”的“C/C++” > “常规”选项卡下，将“使用 Windows 运行时扩展”设置为“是(/ZW)”********************。 此属性 (c + +/CX) 启用组件扩展。

1. 在 **解决方案资源管理器**中，选择项目节点，打开快捷菜单，然后选择 " **卸载项目**"。 然后，在卸载的项目节点上打开快捷菜单，然后选择编辑项目文件。 找到 `WindowsTargetPlatformVersion` 元素，并将其替换为下列元素。

    ```xml
    <AppContainerApplication>true</AppContainerApplication>
    <ApplicationType>Windows Store</ApplicationType>
    <WindowsTargetPlatformVersion>10.0.10156.0</WindowsTargetPlatformVersion>
    <WindowsTargetPlatformMinVersion>10.0.10156.0</WindowsTargetPlatformMinVersion>
    <ApplicationTypeRevision>10.0</ApplicationTypeRevision>
    ```

   关闭该 *`.vcxproj`* 文件，再次打开快捷菜单，然后选择 " **重新加载项目**"。

   **解决方案资源管理器** 现在会将项目标识为通用 Windows 项目。

1. 请确保预编译的头文件的名称正确。 在 " **预编译标头** " 部分中，您可能需要将 **预编译头文件** 从更改 *`pch.h`* 为， *`stdafx.h`* 或者，如果您看到类似于下面的错误，则可能需要另一种方法：

   > 错误 C2857：在 **`/Ycpch.h`** 源文件中找不到用命令行选项指定的 "#include" 语句

   问题在于，较旧的项目模板对预编译标头文件使用不同的命名约定。 Visual Studio 2019 和更高版本的项目使用 *`pch.h`* 。

1. 生成项目。 你可能会收到一些有关不兼容的命令行选项的错误。 例如，许多较旧的 C++ 项目中默认设置有“启用最小重新生成(/Gm)”这一常用选项（但现在已弃用），它与 `/ZW` 不兼容****。

   当你为通用 Windows 平台进行编译时，某些功能不可用。 你将看到有关任何问题的编译器错误。 解决这些错误，直到有一个干净的生成。

1. 若要在同一解决方案中的 uwp 应用中使用该 DLL，请打开 uwp 项目节点的快捷菜单，然后选择 "**添加**  >  **引用**"。

   在 "**项目**" "  >  **解决方案**" 下，选择 DLL 项目旁边的复选框，然后选择 "**确定"** 按钮。

1. 在 UWP 应用的文件中包含库的标头文件 () *`pch.h`* 。

    ```cpp
    #include "..\Giraffe\giraffe.h"
    ```

1. 照常将代码添加到 UWP 项目中，以从 DLL 中调用函数并创建类型。

    ```cpp
    MainPage::MainPage()
    {
        InitializeComponent();
        GiraffeFactory gf;
        Giraffe* g = gf.Create();
        int id = g->GetID();
    }
    ```

## <a name="using-a-native-c-static-library-in-a-uwp-app"></a><a name="BK_StaticLib"></a> 在 UWP 应用中使用本机 c + + 静态库

你可以在 UWP 项目中使用本机 C++ 静态库，但有一些限制和局限需要注意。 请先阅读 [C++/CX 中的静态库](../cppcx/static-libraries-c-cx.md)。 你可以从 UWP 应用访问静态库中的本机代码，但不建议在此类静态库中创建公共 ref 类型。 如果使用 `/ZW` 选项编译静态库，则管理员（实际是经过伪装的链接器）会发出警告：

> LNK4264: 正在将使用 /ZW 编译的对象文件归档到静态库中；请注意，创作 Windows 运行时类型时，建议不要与包含 Windows 运行时元数据的静态库链接

但是，可以在 UWP 应用中使用静态库，而无需对其进行重新编译 `/ZW` 。 库不能声明任何 ref 类型或使用 c + +/CX 构造。 但是，如果您的目的只是使用本机代码库，则可以通过执行以下步骤来执行此操作。

### <a name="to-use-a-native-c-static-library-in-a-uwp-project"></a>若要在 UWP 项目中使用本机 C++ 静态库

1. 在 UWP 项目的项目属性中，选择左窗格中的 "**配置属性**" "  >  **链接器**"  >  **"输入**"。 在右窗格中，将路径添加到库中的“其他依赖项”**** 属性中。 例如，对于项目中放置其输出的库 *`<SolutionFolder>\Debug\MyNativeLibrary\MyNativeLibrary.lib`* ，请添加相对路径 *`Debug\MyNativeLibrary\MyNativeLibrary.lib`* 。

1. 添加一个 include 语句，以便在 *`pch.h`* (如果存在) ，或在任何文件中引用该头文件， *`.cpp`* 并开始添加使用库的代码。

   ```cpp
   #include "..\MyNativeLibrary\MyNativeLibrary.h"
   ```

   请勿在**解决方案资源管理器**的 "**引用**" 节点中添加引用。 该机制仅适用于 Windows 运行时组件。

## <a name="porting-a-c-library-to-a-windows-runtime-component"></a><a name="BK_WinRTComponent"></a> 将 c + + 库移植到 Windows 运行时组件

假设要从 UWP 应用使用静态库中的本机 Api。 如果你具有本机库的源代码，则可以将代码移植到 Windows 运行时组件。 它将不再是静态库;将其转换为可在任何 c + + UWP 应用程序中使用的 DLL。 此过程介绍如何创建使用 c + +/CX 扩展的新 Windows 运行时组件。 有关创建使用 c + +/WinRT 的组件的信息，请参阅 [使用 c + +/WinRT Windows 运行时组件](/windows/uwp/winrt-components/create-a-windows-runtime-component-in-cppwinrt)。

当你使用 c + +/CX 时，可以添加引用类型和其他可供任何 UWP 应用代码中的客户端使用的其他 c + +/CX 构造。 可以从 c #、Visual Basic 或 JavaScript 访问这些类型。 基本过程：

-  (通用 Windows) 项目创建 Windows 运行时组件，
- 将静态库的代码复制到其中，然后
- 解决由选项导致的编译器中的任何错误 `/ZW` 。

### <a name="to-port-a-c-library-to-a-windows-runtime-component"></a>若要将 C++ 库移植到 Windows 运行时组件

1.  (通用 Windows) 项目创建 Windows 运行时组件。

1. 关闭该项目。

1. 在 **Windows 文件资源管理器**中，找到新项目。 然后，找到包含要移植的代码的 c + + 库项目。 将源文件 (头文件、代码文件和任何其他资源（包括从 c + + 库项目中) 的子目录）复制到其中。 将其粘贴到新的项目文件夹，确保保留相同的文件夹结构。

1. 重新打开 Windows 运行时组件项目。 在**解决方案资源管理器**中打开项目节点的快捷菜单，然后选择 "**添加**  >  **现有项**"。

1. 从原始项目中选择要添加的所有文件，然后选择 **"确定"**。 如果子文件夹需要，则重复。

1. 你现在可能有一些重复代码。 如果有多个预编译标头 (说， *`stdafx.h`* 和 *`pch.h`*) ，请选择要保留的一个。 将任何所需的代码（比如 include 语句）复制到你要保留的标头中。 然后，删除另一个，在 "项目属性" 中的 " **预编译头**" 下，确保标头文件的名称正确。

   如果更改了要用作预编译标头的文件，请确保预编译标头选项适用于每个文件。 依次选择每个 *`.cpp`* 文件，打开其属性窗口，并确保所有设置为 **使用 (/yu) **，预编译标头除外，应将该标头设置为 **创建 (/yc) **。

1. 生成项目并解决任何错误。 这些错误可能是由于使用选项导致的 `/ZW` ，也可能是由 Windows SDK 的新版本引起的。 或者，它们可能反映依赖项（如库依赖的头文件）或旧项目和新项目之间的项目设置差异。

1. 将公共 ref 类型添加到你的项目，或将普通类型转换为 ref 类型。 使用这些类型可向要从 UWP 应用调用的功能公开入口点。

1. 通过从 UWP 应用项目添加对组件的引用来测试该组件，然后添加某些代码来调用你创建的公共 API。

## <a name="see-also"></a>请参阅

[移植到通用 Windows 平台](../porting/porting-to-the-universal-windows-platform-cpp.md)
