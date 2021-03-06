---
description: 详细了解：使用库和组件
title: 在 C++ 项目中使用库和组件
ms.date: 12/18/2020
f1_keywords:
- VC.Project.References
helpviewer_keywords:
- Add References Dialog Box (C++)
- .NET Framework (C++), Add References Dialog Box
ms.assetid: 12b8f571-0f21-40b3-9404-5318a57e9cb5
ms.openlocfilehash: c8e7cb41fad6a974ac677228d884a31e4fa92ce1
ms.sourcegitcommit: 2b2c3fa9244e31db35ea33554dea0efcab490f3c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/18/2020
ms.locfileid: "97682448"
---
# <a name="consuming-libraries-and-components"></a>使用库和组件

通常，C++ 项目需要调用二进制文件中的函数或访问其中的数据，例如静态库（LIB 文件）、DLL、Windows 运行时组件、COM 组件或 .NET 程序集。 在这些情况下，必须配置项目，使它可以在生成时找到该二进制文件。 具体步骤取决于项目的类型、二进制文件的类型以及二进制文件是否在与项目相同的解决方案中生成。

## <a name="consuming-libraries-downloaded-via-vcpkg"></a>使用通过 vcpkg 下载的库

若要使用通过 vcpkg  包管理器下载的库，可以忽略以下说明。 请参阅 [vcpkg：用于 Windows、Linux 和 MacOS](vcpkg.md) 的 C++ 包管理器以了解详细信息。

## <a name="consuming-static-libraries"></a>使用静态库

如果在同一个解决方案中生成静态库项目：

1. #<a name="include-the-header-files-for-the-static-library-using-quotation-marks-in-a-typical-solution-the-path-starts-with-library-project-name-intellisense-will-help-you-find-it"></a>使用引号包含静态库的头文件。 在典型解决方案中，路径将以 `../<library project name>` 开头。 IntelliSense 将帮助你找到它。
2. 添加对静态库项目的引用。 在“解决方案资源管理器”中的应用程序项目节点下右键单击“引用”，然后选择“添加引用”    。

如果静态库不是解决方案的一部分：

1. 右键单击“解决方案资源管理器”中的应用程序项目节点，然后选择“属性”   。
2. 在“VC++ 目录”属性页中，将包含 LIB 文件的目录的路径添加到“库路径” 。 然后，将库标头文件的路径添加到“包含目录”。  
3. 在“链接器”>“输入”属性页中，将 LIB 文件的名称添加到“附加依赖项” 。

## <a name="dynamic-link-libraries"></a>动态链接库

如果 DLL 作为与应用程序相同的解决方案的一部分生成，请执行与静态库相同的步骤。

如果 DLL 不是应用程序解决方案的一部分，则需要 DLL 文件、包含导出函数和类的原型的头文件以及提供所需链接信息的 LIB 文件。

1. 将 DLL 复制到项目的输出文件夹，或复制到 DLL 的标准 Windows 搜索路径中的另一个文件夹。 请参阅[动态链接库搜索顺序](/windows/win32/dlls/dynamic-link-library-search-order)。
2. 按照适用于静态库的步骤 1-3 来提供头文件和 LIB 文件的路径。

## <a name="com-objects"></a>COM 对象

如果本机 C++ 应用程序需要使用某个 COM 对象，并且该对象已注册  ，则只需调用 CoCreateInstance 并传入该对象的 CLSID。 系统将在 Windows 注册表中找到它并进行加载。 C++/CLI 项目可以采用相同的方式使用 COM 对象。 也可以从“添加引用”>“COM”列表添加对它的引用并通过其[运行时可调用包装器](/dotnet/framework/interop/runtime-callable-wrapper)使用它。

## <a name="net-assemblies-and-windows-runtime-components"></a>.NET 程序集和 Windows 运行时组件

在 UWP 或 C++/CLI 项目中，可通过添加对程序集或组件的引用  ，来使用 .NET 程序集或 Windows 运行时组件。 在 UWP 或 C++/CLI 项目的“引用”节点下，可看到对常用组件的引用。 在“解决方案资源管理器”中，右键单击“引用”节点，以显示“引用管理器”并浏览系统上提供的其他组件  。 单击“浏览”按钮，导航到包含自定义组件的任何文件夹。 由于 .NET 程序集和 Windows 运行时组件包含内置类型信息，因此可以通过右键单击并选择“在对象浏览器中查看”  来查看其方法和类。

## <a name="reference-properties"></a>引用属性

每类引用均有属性。 你可以采用以下两种方式来查看属性：在解决方案资源管理器中选择引用并按“Alt + Enter”  ，或者右键单击并选择“属性”  。 有些属性为只读属性，有些可进行修改。 然而，你通常无需手动修改这些属性。

### <a name="activex-reference-properties"></a>ActiveX 引用属性

ActiveX 引用属性仅可用于对 COM 组件的引用。 只有在“引用”窗格中选中了 COM 组件时，才会显示这些属性。 不可修改这些属性。

- **控件完整路径**

   显示所引用控件的目录路径。

- **控件 GUID**

   显示 ActiveX 控件的 GUID。

- **控件版本**

   显示所引用的 ActiveX 控件的版本。

- **类型库名称**

   显示所引用的类型库的名称。

- **包装工具**

   显示用于从所引用的 COM 库或 ActiveX 控件中生成互操作程序集的工具。

### <a name="assembly-reference-properties-ccli"></a>程序集引用属性 (C++/CLI)

程序集引用属性仅用于对 C++/CLI 项目中 .NET Framework 程序集的引用。 只有在“引用”窗格中选中 .NET Framework 程序集时，才会显示这些属性。 不可修改这些属性。

- **相对路径**

   显示项目目录到所引用程序集的相对路径。

### <a name="build-properties"></a>生成属性

以下属性可用于各种类型的引用。 它们使你可以指定如何用引用进行生成。

- **复制本地**

   指定是否在生成期间自动将所引用的程序集复制到目标位置。

- 复制本地附属程序集 (C++/CLI)

   指定是否在生成期间将所引用程序集的附属程序集复制到目标位置。 仅在“复制本地”为 `true` 时使用。

- **引用程序集输出**

   指定在生成过程中使用此程序集。 如果是 `true`，则在生成期间在编译器命令行上使用此程序集。

### <a name="project-to-project-reference-properties"></a>项目到项目引用属性

以下属性定义从“引用”窗格中选中的项目到同一解决方案中另一项目的项目到项目引用。 有关详细信息，请参阅[管理项目中的引用](/visualstudio/ide/managing-references-in-a-project)。

- **链接库依赖项**

   此属性为 True 时，项目系统会将不相关项目生成的 LIB 文件链接到相关项目。 通常，需要指定为 True。

- **项目标识符**

   唯一标识独立项目。 属性值是不可修改的内部系统 GUID。

- **使用库依赖项输入**

   当此属性为 False 时，项目系统不会将库中由不相关项目生成的 OBJ 文件链接到相关项目。 因此，此值会禁用增量链接。 通常，需要指定为 False，因为如果存在多个不相关项目，则构建应用程序可能会花很长时间。

### <a name="read-only-reference-properties-com--net"></a>只读引用属性（COM 和 .NET）

以下属性位于 COM 和 .NET 程序集引用上，且不可修改。

- **程序集名称**

   显示所引用的程序集的程序及名称。

- **区域性**

   显示所选引用的区域性。

- **说明**

   显示所选引用的描述。

- **完整路径**

   显示所引用的程序集的目录路径。

- **标识**

   对于 .NET Framework 程序集，显示完整路径。 对于 COM 组件，显示 GUID。

- **标签**

   显示引用的标签。

- **名称**

   显示引用的名称。

- **公钥标记**

   显示用于标识所引用的程序集的公钥标记。

- **强名称**

   如果引用的汇编有强名称，则为 `true`。 强名称程序集的版本是唯一的。

- **Version**

   显示所引用的程序集的版本。

## <a name="see-also"></a>请参阅

[C++ 项目属性页参考](reference/property-pages-visual-cpp.md)<br>
[在 Visual Studio 中设置 C++ 编译器并生成属性](working-with-project-properties.md)
