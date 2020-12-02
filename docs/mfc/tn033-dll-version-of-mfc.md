---
title: TN033：MFC 的 DLL 版本
description: 演示如何将 MFC 共享动态链接库与 MFC 应用程序和 MFC 扩展 Dll 一起使用。
ms.date: 11/30/2020
helpviewer_keywords:
- MFC DLLs [MFC], writing MFC extension DLLS
- AFXDLL library
- DLLs [MFC], MFC
- DLL version of MFC [MFC]
- TN033
ms.openlocfilehash: b9330fe7c756f962a8b06a04b840bfda343f3a49
ms.sourcegitcommit: 432c24dde31c400437c4320e8432b1ddb232f844
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/01/2020
ms.locfileid: "96440316"
---
# <a name="tn033-dll-version-of-mfc"></a>TN033：MFC 的 DLL 版本

本说明介绍了如何使用 *`MFCxx.DLL`* 和 (， *`MFCxxD.DLL`* 其中 *XX* 是使用 MFC 应用程序和 mfc 扩展 dll) 共享动态链接库的 MFC 版本号。 有关常规 MFC Dll 的详细信息，请参阅 [将 MFC 作为 DLL 的一部分使用](../mfc/tn011-using-mfc-as-part-of-a-dll.md)。

本技术说明介绍了 Dll 的三个方面。 最后两个适用于更高级的用户：

- [如何生成 MFC 扩展 DLL](#_mfcnotes_how_to_write_an_mfc_extension_dll)

- [如何生成使用 MFC 的 DLL 版本的 MFC 应用程序](#_mfcnotes_writing_an_application_that_uses_the_dll_version)

- [如何实现 MFC 共享动态链接库](#_mfcnotes_how_the_mfc30.dll_is_implemented)

如果你有兴趣使用可以与非 MFC 应用程序一起使用的 MFC 构建 DLL (称为 *常规 MFC DLL*) ，请参阅 [技术说明 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md)。

## <a name="overview-of-mfcxxdll-support-terminology-and-files"></a>MFCxx.DLL 支持概述：术语和文件

**常规 MFC dll**：使用常规 mfc dll 生成使用一些 MFC 类的独立 DLL。 跨应用/DLL 边界的接口为 "C" 接口，客户端应用程序不一定是 MFC 应用程序。

规则 MFC Dll 是 MFC 1.0 支持的 Dll 版本。 [技术说明 11](../mfc/tn011-using-mfc-as-part-of-a-dll.md)和 MFC 高级概念示例中对它们进行了介绍 [`DLLScreenCap`](../overview/visual-cpp-samples.md) 。

> [!NOTE]
> 从 Visual C++ 版本4.0 起，术语 **USRDLL** 已过时，已由静态链接到 mfc 的规则 mfc DLL 替换。 你还可以生成动态链接到 MFC 的规则 MFC DLL。

MFC 3.0 (及更高版本) 支持具有所有新功能（包括 OLE 类和数据库类）的常规 MFC Dll。

**AFXDLL**：也称为 "共享版本的 MFC 库"。 它是 MFC 2.0 中添加的新 DLL 支持。 MFC 库本身位于多个 Dll 中 (如下) 所述。 客户端应用程序或 DLL 动态链接其所需的 Dll。 跨应用程序/DLL 边界的接口是 c + +/MFC 类接口。 客户端应用程序必须是 MFC 应用程序。 此 DLL 支持所有 MFC 3.0 功能 (异常：数据库类) 不支持 UNICODE。

> [!NOTE]
> 到 Visual C++ 版本4.0 中，这种类型的 DLL 称为 "扩展 DLL"。

此注释将使用 *`MFCxx.DLL`* 来引用整个 MFC DLL 集，其中包括：

- 调试： *`MFCxxD.DLL`* 组合) 和 *`MFCSxxD.LIB`* (静态)  (。

- Release： *`MFCxx.DLL`* 组合) 和 *`MFCSxx.LIB`* (静态)  (。

- Unicode 调试： *`MFCxxUD.DLL`* 组合) 和 *`MFCSxxD.LIB`* (静态)  (。

- Unicode 版本： *`MFCxxU.DLL`* 组合) 和 *`MFCSxxU.LIB`* (静态)  (。

> [!NOTE]
> *`MFCSxx[U][D].LIB`* 库与 MFC 共享 dll 结合使用。 这些库包含必须静态链接到应用程序或 DLL 的代码。

应用程序链接到相应的导入库：

- Debug.exe *`MFCxxD.LIB`*

- 拆卸 *`MFCxx.LIB`*

- Unicode 调试： *`MFCxxUD.LIB`*

- Unicode 版本： *`MFCxxU.LIB`*

*MFC 扩展 dll* 是扩展 *`MFCxx.DLL`* (或其他 MFC 共享 DLL) 的 dll。 在这里，MFC 组件体系结构正在进行。 如果从 MFC 类派生有用的类，或生成另一个类似 MFC 的工具包，则可以将其放置在 DLL 中。 *`MFCxx.DLL`* 与最终的客户端应用程序一样，DLL 使用。 MFC 扩展 DLL 允许可重用的叶类、可重复使用的基类和可重用的视图和文档类。

## <a name="pros-and-cons"></a>优点和缺点

为什么要使用 MFC 的共享版本

- 使用共享库可能会导致较小的应用程序。  (最少使用 MFC 库的应用程序小于 10K) 。

- MFC 的共享版本支持 MFC 扩展 Dll 和常规 MFC Dll。

- 生成使用共享 MFC 库的应用程序比静态链接的 MFC 应用程序更快。 这是因为不需要链接 MFC 本身。 在 **`DEBUG`** 链接器必须压缩调试信息的生成中尤其如此。 当你的应用程序链接到已包含调试信息的 DLL 时，需要压缩的调试信息会更少。

为什么不应使用共享版本的 MFC：

- 如果要传送使用共享库的应用程序，则需要 *`MFCxx.DLL`* 随程序一起传送和其他库。 *`MFCxx.DLL`* 可像多个 Dll 一样自由再发行，但你仍必须在安装程序中安装 DLL。 此外，您还必须为您的程序和 MFC Dll 本身使用其他可再发行库。

## <a name="how-to-write-an-mfc-extension-dll"></a><a name="_mfcnotes_how_to_write_an_mfc_extension_dll"></a> 如何编写 MFC 扩展 DLL

MFC 扩展 DLL 是一个 DLL，其中包含用于扩展 MFC 类功能的类和函数。 MFC 扩展 DLL 以应用程序使用的相同方式使用共享 MFC Dll，还需要注意一些其他事项：

- 生成过程类似于生成使用共享 MFC 库的应用程序，其中包含几个附加的编译器和链接器选项。

- MFC 扩展 DLL 没有 `CWinApp` 派生的类。

- MFC 扩展 DLL 必须提供特殊的 `DllMain` 。 工作程序向导提供了一个 `DllMain` 可修改的函数。

- `CDynLinkLibrary`如果 mfc 扩展 dll 将 `CRuntimeClass` 类型或资源导出到应用程序，MFC 扩展 dll 通常会提供一个用于创建的初始化例程。 `CDynLinkLibrary`如果必须由 MFC 扩展 DLL 维护每个应用程序的数据，则可以使用的派生类。

下面更详细地介绍了这些注意事项。 另请参阅 MFC 高级概念示例 [`DLLHUSK`](../overview/visual-cpp-samples.md) 。 它演示了如何执行以下操作：

- 使用共享库生成应用程序。  (*`DLLHUSK.EXE`* 是动态链接到 mfc 库和其他 dll 的 mfc 应用程序。 ) 

- 生成 MFC 扩展 DLL。  (它显示了 `_AFXEXT` 生成 MFC 扩展 DLL 时使用的特殊标志，如 get。 ) 

- 构建 MFC 扩展 Dll 的两个示例。 其中一个示例显示了 MFC 扩展 DLL 的基本结构，其中包含受限的导出 (TESTDLL1) ，另一个示例将)  (TESTDLL2 导出整个类接口。

客户端应用程序和任何 MFC 扩展 Dll 都必须使用相同版本的 *`MFCxx.DLL`* 。 遵循 MFC Dll 的约定，同时提供 **`/release`**) 版本的 mfc 扩展 DLL 的调试和发布 (。 这种做法允许客户端程序构建其应用程序的调试版本和发布版本，并将它们与所有 Dll 的相应调试或发布版本链接。

> [!NOTE]
> 由于 c + + 名称重整和导出问题，同一 DLL 的调试版本和发布版本在不同平台上的调试版本和发布版本可能不同。 该版本 *`MFCxx.DLL`* 有大约2000个导出的入口点; 调试 *`MFCxxD.DLL`* 包含大约3000个导出的入口点。

### <a name="quick-note-on-memory-management"></a>有关内存管理的快速说明

本技术说明结尾附近的 "内存管理" 一节介绍了的实现， *`MFCxx.DLL`* 以及 MFC 的共享版本。 此处描述了只需知道如何实现 MFC 扩展 DLL 所需的信息。

*`MFCxx.DLL`* 加载到客户端应用程序的地址空间中的所有 MFC 扩展 Dll 都将使用相同的内存分配器、资源加载和其他 MFC "全局" 状态，就好像它们在同一应用程序中一样。 这是很重要的，因为静态链接到 MFC 的非 MFC DLL 库和常规 MFC Dll 的执行方式完全相反：每个 DLL 都从其自身的内存池中分配。

如果 MFC 扩展 DLL 分配内存，则该内存可以自由地与任何其他应用程序分配的对象混合使用。 此外，如果使用共享 MFC 库的应用程序发生故障，则操作系统将维护共享该 DLL 的任何其他 MFC 应用程序的完整性。

同样，其他 "全局" MFC 状态（如要从中加载资源的当前可执行文件）也会在客户端应用程序、所有 MFC 扩展 Dll 及其 *`MFCxx.DLL`* 自身之间共享。

### <a name="building-an-mfc-extension-dll"></a>生成 MFC 扩展 DLL

可以使用执行程序向导创建 MFC 扩展 DLL 项目，并自动生成相应的编译器和链接器设置。 它还会生成一个 `DllMain` 可修改的函数。

如果要将现有项目转换为 MFC 扩展 DLL，请从使用共享版本的 MFC 生成的标准设置开始。 然后进行以下更改：

- 添加 **`/D_AFXEXT`** 到编译器标志。 在 "项目属性" 对话框中，选择 " **c/c + +**  >  **预处理器**" 类别。 将添加 `_AFXEXT` 到 " **定义宏** " 字段，并用分号分隔每个项。

- 删除 **`/Gy`** 编译器开关。 在 "项目属性" 对话框中，选择 " **c/c + +**  >  **代码生成**" 类别。 请确保未启用 " **启用 Function-Level 链接** " 属性。 此设置可以更轻松地导出类，因为链接器不会删除未引用的函数。 如果原始项目生成了静态链接到 MFC 的规则 MFC DLL，请将 **`/MT`** (或 **`/MTd`**) 编译器选项更改为 **`/MD`** (或 **`/MDd`**) 。

- 使用链接选项生成导出库 **`/DLL`** 。 当你创建新目标并将 Win32 Dynamic-Link 库指定为目标类型时，将设置此选项。

### <a name="changing-your-header-files"></a>更改标头文件

MFC 扩展 DLL 的常用目标是将一些常用功能导出到一个或多个可以使用该功能的应用程序。 实质上，DLL 导出类和全局函数以供客户端应用程序使用。

若要确保将每个成员函数标记为按需导入或导出，请使用特殊声明 `__declspec(dllexport)` 和 `__declspec(dllimport)` 。 当客户端应用程序使用你的类时，你希望将它们声明为 `__declspec(dllimport)` 。 MFC 扩展 DLL 本身生成时，应将函数声明为 `__declspec(dllexport)` 。 生成的 DLL 还必须导出函数，以便客户端程序在加载时可以绑定到它们。

若要导出整个类，请 `AFX_EXT_CLASS` 在类定义中使用。 在定义时，框架会将此宏定义为 `__declspec(dllexport)` `_AFXDLL` `_AFXEXT` ，但将其定义为 " `__declspec(dllimport)` `_AFXEXT` 未定义时"。 `_AFXEXT` 仅在生成 MFC 扩展 DLL 时定义。 例如：

```cpp
class AFX_EXT_CLASS CExampleExport : public CObject
{ /* ... class definition ... */ };
```

### <a name="not-exporting-the-entire-class"></a>不导出整个类

有时，你可能只需要导出类的单个必需成员。 例如，如果导出 `CDialog` 派生类，可能只需要导出构造函数和 `DoModal` 调用。 您可以使用 DLL 的 .DEF 文件导出这些成员，但也可以在 `AFX_EXT_CLASS` 需要导出的各个成员上使用非常相似的方式。

例如：

```cpp
class CExampleDialog : public CDialog
{
public:
    AFX_EXT_CLASS CExampleDialog();
    AFX_EXT_CLASS int DoModal();
    // rest of class definition
    // ...
};
```

当你执行此操作时，你可能会遇到其他问题，因为你不会导出类的所有成员。 问题在于 MFC 宏的工作方式。 MFC 的一些帮助程序宏实际上声明或定义数据成员。 您的 DLL 还需要导出这些数据成员。

例如，在生成 MFC 扩展 DLL 时，DECLARE_DYNAMIC 宏定义如下：

```cpp
#define DECLARE_DYNAMIC(class_name) \
protected: \
    static CRuntimeClass* PASCAL _GetBaseClass(); \
    public: \
    static AFX_DATA CRuntimeClass class##class_name; \
    virtual CRuntimeClass* GetRuntimeClass() const; \
```

开始在 `static AFX_DATA` 类中声明静态对象的行。 若要正确导出此类并从客户端 EXE 访问运行时信息，需要导出此静态对象。 由于静态对象是用修饰符声明的 `AFX_DATA` ，因此只需在 `AFX_DATA` `__declspec(dllexport)` 生成 DLL 时定义为。 将其定义为 `__declspec(dllimport)` 生成客户端可执行文件时。

如上所述， `AFX_EXT_CLASS` 已经以这种方式定义。 只需将重定义为与 `AFX_DATA` `AFX_EXT_CLASS` 类定义相同。

例如：

```cpp
#undef  AFX_DATA
#define AFX_DATA AFX_EXT_CLASS
class CExampleView : public CView
{
    DECLARE_DYNAMIC()
    // ... class definition ...
};
#undef  AFX_DATA
#define AFX_DATA
```

MFC 始终 `AFX_DATA` 对它在其宏中定义的数据项使用符号，因此此方法适用于所有此类方案。 例如，它将适用于 DECLARE_MESSAGE_MAP。

> [!NOTE]
> 如果要导出整个类，而不是导出类的所选成员，则会自动导出静态数据成员。

您可以使用相同的方法自动导出 `CArchive` 使用 DECLARE_SERIAL 和 IMPLEMENT_SERIAL 宏的类的提取运算符。 使用以下代码通过括号) 标头文件中 (的类声明来导出 archive 运算符：

```cpp
#undef AFX_API
#define AFX_API AFX_EXT_CLASS

/* your class declarations here */

#undef AFX_API
#define AFX_API
```

### <a name="limitations-of-_afxext"></a>_AFXEXT 的限制

`_AFXEXT`只要你没有 mfc 扩展 dll 的多个层，就可以使用 mfc 扩展 dll 的预处理器符号。 如果 MFC 扩展 DLL 调用或派生自你自己的 MFC 扩展 DLL 中的类，然后从 MFC 类派生，则必须使用你自己的预处理器符号以避免歧义。

问题在于，在 Win32 中，你必须将任何数据显式声明为 `__declspec(dllexport)` 从 dll 中导出数据，并 `__declspec(dllimport)` 将其从 dll 导入。 定义时 `_AFXEXT` ，MFC 标头确保 `AFX_EXT_CLASS` 定义正确。

如果有多个层，则一个符号（例如） `AFX_EXT_CLASS` 不能满足要求： MFC 扩展 dll 可以导出自己的类，还可以从其他 MFC 扩展 dll 导入其他类。 若要处理此问题，请使用特殊的预处理器符号，该符号指示你正在生成 DLL 本身，而不是使用 DLL。 例如，假设有两个 MFC 扩展 Dll： *`A.DLL`* 和 *`B.DLL`* 。 它们分别导出和中的一些类 *`A.H`* *`B.H`* 。 *`B.DLL`* 使用中的类 *`A.DLL`* 。 头文件类似于以下形式：

```cpp
/* A.H */
#ifdef A_IMPL
    #define CLASS_DECL_A   __declspec(dllexport)
#else
    #define CLASS_DECL_A   __declspec(dllimport)
#endif

class CLASS_DECL_A CExampleA : public CObject
{ /* ... class definition ... */ };

/* B.H */
#ifdef B_IMPL
    #define CLASS_DECL_B   __declspec(dllexport)
#else
    #define CLASS_DECL_B   __declspec(dllimport)
#endif

class CLASS_DECL_B CExampleB : public CExampleA
{ /* ... class definition ... */ };
```

生成时，它是在生成时生成的， *`A.DLL`* **`/DA_IMPL`** *`B.DLL`* 它是通过生成的 **`/DB_IMPL`** 。 通过对每个 DLL 使用单独的符号， `CExampleB` 会导出并 `CExampleA` 在生成时导入 *`B.DLL`* 。 `CExampleA` 当 *`A.DLL`* 由 *`B.DLL`* 或其他某个客户端使用时，将在生成和导入时导出。

使用内置 `AFX_EXT_CLASS` 和 `_AFXEXT` 预处理器符号时，不能执行这种类型的分层。 上面所述的方法以 MFC 的相同方式解决了这一问题。 MFC 在生成其 OLE、数据库和网络 MFC 扩展 Dll 时使用此方法。

### <a name="not-exporting-the-entire-class"></a>不导出整个类

同样，如果不导出整个类，则必须特别小心。 确保正确导出 MFC 宏创建的必需数据项。 可以通过重新定义 `AFX_DATA` 特定类的宏来完成此操作。 请在不导出整个类时重新定义它。

例如：

```cpp
// A.H
#ifdef A_IMPL
    #define CLASS_DECL_A  _declspec(dllexport)
#else
    #define CLASS_DECL_A  _declspec(dllimport)
#endif

#undef  AFX_DATA
#define AFX_DATA CLASS_DECL_A

class CExampleA : public CObject
{
    DECLARE_DYNAMIC()
    CLASS_DECL_A int SomeFunction();
    // class definition
    // ...
};

#undef AFX_DATA
#define AFX_DATA
```

### <a name="dllmain"></a>DllMain

下面是应放置在 MFC 扩展 DLL 的主源文件中的代码。 它应位于标准包含之后。 当使用执行程序向导为 MFC 扩展 DLL 创建起始文件时，它将 `DllMain` 为你提供。

```cpp
#include "afxdllx.h"

static AFX_EXTENSION_MODULE extensionDLL;

extern "C" int APIENTRY
DllMain(HINSTANCE hInstance, DWORD dwReason, LPVOID)
{
   if (dwReason == DLL_PROCESS_ATTACH)
   {
      // MFC extension DLL one-time initialization
      if (!AfxInitExtensionModule(
             extensionDLL, hInstance))
         return 0;

      // TODO: perform other initialization tasks here
   }
   else if (dwReason == DLL_PROCESS_DETACH)
   {
      // MFC extension DLL per-process termination
      AfxTermExtensionModule(extensionDLL);

      // TODO: perform other cleanup tasks here
   }
   return 1;   // ok
}
```

对的调用将 `AfxInitExtensionModule` 捕获模块的运行时类 (`CRuntimeClass` 结构) 及其对象工厂 (`COleObjectFactory` 对象) 以后在创建对象时使用 `CDynLinkLibrary` 。  (可选的) 调用，以便 `AfxTermExtensionModule` 在每个进程分离时，使 mfc 清除 mfc 扩展 dll (这会在进程退出时发生，或者在 `FreeLibrary` 从 MFC 扩展 DLL 调用) 卸载 DLL 时。 由于大多数 MFC 扩展 Dll 都不会动态地 (加载，因此它们通过其导入库进行链接) ， `AfxTermExtensionModule` 通常不需要调用。

如果你的应用程序动态加载和释放 MFC 扩展 Dll，请确保调用， `AfxTermExtensionModule` 如上面所示。 另外，请务必使用 `AfxLoadLibrary` 和 `AfxFreeLibrary` (而不是 Win32 `LoadLibrary` 函数 `FreeLibrary` ，如果应用程序使用多个线程或动态加载 MFC 扩展 DLL，则) 。 使用 `AfxLoadLibrary` 并 `AfxFreeLibrary` 确保加载并卸载 MFC 扩展 DLL 时执行的启动和关闭代码不会损坏全局 MFC 状态。

标头文件 *`AFXDLLX.H`* 包含 MFC 扩展 dll 中使用的结构的特殊定义，如和的定义 `AFX_EXTENSION_MODULE` `CDynLinkLibrary` 。

必须按如下所示声明全局 *extensionDLL* 。 与 MFC 的16位版本不同，你可以在这段时间内分配内存和调用 MFC 函数，因为在调用时，将 *`MFCxx.DLL`* 完全初始化 `DllMain` 。

### <a name="sharing-resources-and-classes"></a>共享资源和类

简单 MFC 扩展 Dll 只需将几个低带宽函数导出到客户端应用程序。 更多用户界面密集型 Dll 可能需要将资源和 c + + 类导出到客户端应用程序。

导出资源通过资源列表来进行。 在每个应用程序中，都是对象的单独链接列表 `CDynLinkLibrary` 。 查找资源时，加载资源的大多数标准 MFC 实现 (`AfxGetResourceHandle`) ，如果未找到，则会遍历 `CDynLinkLibrary` 尝试加载所请求资源的对象的列表。

给定 c + + 类名的 c + + 对象动态创建类似。 MFC 对象反序列化机制需要所有 `CRuntimeClass` 已注册的对象，以便它可以通过基于之前存储的内容的所需类型的 c + + 对象动态创建来重新构造。

如果希望客户端应用程序使用 MFC 扩展 DLL 中的类 `DECLARE_SERIAL` ，则需要导出类，使其对客户端应用程序可见。 还可以通过浏览列表完成此操作 `CDynLinkLibrary` 。

在 MFC 高级概念示例中 [`DLLHUSK`](../overview/visual-cpp-samples.md) ，列表如下所示：

```Example
head ->   DLLHUSK.EXE   - or - DLLHUSK.EXE
               |                    |
          TESTDLL2.DLL         TESTDLL2.DLL
               |                    |
          TESTDLL1.DLL         TESTDLL1.DLL
               |                    |
               |                    |
           MFC90D.DLL           MFC90.DLL
```

该 *`MFCxx.DLL`* 条目通常出现在 "资源和类" 列表中。 *`MFCxx.DLL`* 包括所有标准 MFC 资源，包括所有标准命令 Id 的提示字符串。 将其放在列表的末尾后，Dll 和客户端应用程序本身就可以依赖中的共享资源 *`MFCxx.DLL`* ，而无需拥有自己的副本。

将所有 Dll 的资源和类名称合并到客户端应用程序的命名空间中的缺点是必须小心选取哪些 Id 或名称。 您可以通过不将资源或 `CDynLinkLibrary` 对象导出到客户端应用程序来禁用此功能。 该 [`DLLHUSK`](../overview/visual-cpp-samples.md) 示例通过使用多个头文件来管理共享资源命名空间。 有关使用共享资源文件的更多提示，请参阅 [技术说明 35](../mfc/tn035-using-multiple-resource-files-and-header-files-with-visual-cpp.md) 。

### <a name="initializing-the-dll"></a>初始化 DLL

如上所述，通常要创建一个 `CDynLinkLibrary` 对象，用于将资源和类导出到客户端应用程序。 你需要提供已导出的入口点以初始化 DLL。 最简单的情况是，它 `void` 不采用任何参数并返回任何内容，但它可以是你喜欢的任何内容。

如果使用此方法，每个要使用 DLL 的客户端应用程序都必须调用此初始化例程。 你还可以 `CDynLinkLibrary` 在调用后在中分配此对象 `DllMain` `AfxInitExtensionModule` 。

初始化例程必须 `CDynLinkLibrary` 在当前应用程序的堆中创建一个对象，并将其连接到 MFC 扩展 DLL 信息。 可以通过定义函数（如下所示）来执行此操作：

```cpp
extern "C" extern void WINAPI InitXxxDLL()
{
    new CDynLinkLibrary(extensionDLL);
}
```

在此示例中，例程名称 *InitXxxDLL* 可以是所需的任何内容。 不需要这样做 **`extern "C"`** ，但这会使导出列表更易于维护。

> [!NOTE]
> 如果从规则 MFC DLL 使用 MFC 扩展 DLL，则必须导出此初始化函数。 在使用任何 MFC 扩展 DLL 类或资源之前，必须从规则 MFC DLL 调用此函数。

### <a name="exporting-entries"></a>导出条目

导出类的简单方法是在要导出的 `__declspec(dllimport)` `__declspec(dllexport)` 每个类和全局函数上使用和。 这是一件容易的事情，但与命名 .DEF 文件中的每个入口点相比，其效率更低，如下所述。 这是因为您对导出哪些函数的控制更少。 而且，不能按序号导出函数。 TESTDLL1 和 TESTDLL2 使用此方法导出其条目。

一种更有效的方法是通过在 .DEF 文件中命名每个项来导出每个项。 此方法由使用 *`MFCxx.DLL`* 。 由于我们要从 DLL 中选择性地导出，因此必须确定要导出哪些特定接口。 这是很困难的，因为你必须以 DEF 文件中的条目形式指定链接到链接器的名称。 请勿导出任何 c + + 类，除非确实需要为其设置符号链接。

如果在之前尝试使用 DEF 文件导出 c + + 类，可能需要开发工具来自动生成此列表。 可以使用两阶段链接过程完成此操作。 将 DLL 链接到一次，无任何导出，并允许链接器生成映射文件。 映射文件包含应导出的函数的列表。 进行一些重新安排后，可以使用它来生成 .DEF 文件的导出项。 *`MFCxx.DLL`* 和 OLE 和数据库 MFC 扩展 dll 的导出列表（数一千个数字）使用此过程 (生成，尽管它不是完全自动的，而且) 时需要一次手动优化。

### <a name="cwinapp-vs-cdynlinklibrary"></a>CWinApp 与 CDynLinkLibrary

MFC 扩展 DLL 没有 `CWinApp` 自己的派生对象。 相反，它必须与 `CWinApp` 客户端应用程序的派生对象结合使用。 这意味着客户端应用程序拥有主消息泵、空闲循环等。

如果 MFC 扩展 DLL 需要维护每个应用程序的额外数据，则可以从派生新类， `CDynLinkLibrary` 并在上面的例程中创建它 `InitXxxDLL` 。 在运行时，DLL 可以检查当前应用程序的对象列表， `CDynLinkLibrary` 以查找该特定 MFC 扩展 DLL 的对象。

### <a name="using-resources-in-your-dll-implementation"></a>在 DLL 实现中使用资源

如上所述，默认资源负载会遍历对象列表， `CDynLinkLibrary` 查找包含请求资源的第一个 EXE 或 DLL。 所有 MFC Api 和所有内部代码都使用 `AfxFindResourceHandle` 来浏览资源列表，以查找任何资源，而不管其位于何处。

如果只希望从特定位置加载资源，请使用 Api `AfxGetResourceHandle` 并 `AfxSetResourceHandle` 保存旧句柄并设置新句柄。 在返回到客户端应用程序之前，请务必还原旧资源句柄。 示例 TESTDLL2 使用此方法显式加载菜单。

浏览此列表有一些缺点：稍微慢一些，需要管理资源 ID 范围。 其优点是链接到多个 MFC 扩展 DLL 的客户端应用程序可以使用任何 DLL 提供的资源，而无需指定 DLL 实例句柄。 `AfxFindResourceHandle` 是用于遍历资源列表以查找给定匹配项的 API。 它采用资源的名称和类型，并返回资源句柄，其中它首先查找资源，或为 NULL。

## <a name="writing-an-application-that-uses-the-dll-version"></a><a name="_mfcnotes_writing_an_application_that_uses_the_dll_version"></a> 编写使用 DLL 版本的应用程序

### <a name="application-requirements"></a>应用程序要求

使用 MFC 的共享版本的应用程序必须遵循几个基本规则：

- 它必须具有 `CWinApp` 对象，并遵循消息泵的标准规则。

- 它必须使用一组必需的编译器标志进行编译 (如下) 所示。

- 它必须与 Mfcxx.dll 导入库链接。 通过设置所需的编译器标志，MFC 标头确定应用程序应链接到的库的链接时间。

- 若要运行该可执行文件， *`MFCxx.DLL`* 必须位于路径或 Windows 系统目录中。

### <a name="building-with-the-development-environment"></a>通过开发环境生成

如果使用大多数标准默认值的内部生成文件，则可以轻松地更改项目以生成 DLL 版本。

下面的步骤假定你具有一个正确运行的 MFC 应用程序，该应用程序与用于 *`NAFXCWD.LIB`* 调试的 () 和 *`NAFXCW.LIB`* (用于发布) ，并且你想要将其转换为使用共享版本的 mfc 库。 正在运行 Visual Studio 环境，并具有内部项目文件。

1. 在 " **项目** " 菜单上，选择 " **属性**"。 在 "**项目默认值**" 下的 "**常规**" 页中，将 Microsoft 基础类设置为在 **共享 DLL 中使用 MFC** (mfcxx.dll (d) ) 。

### <a name="building-with-nmake"></a>通过 NMAKE 生成

如果使用的是编译器的外部生成文件功能，或直接使用 NMAKE，则必须编辑生成文件以支持所需的编译器和链接器选项。

所需的编译器标志：

- **`/D_AFXDLL /MD`**
  **`/D_AFXDLL`**

标准 MFC 标头需要 `_AFXDLL` 定义符号。

- **`/MD`** 应用程序必须使用 C 运行时库的 DLL 版本。

所有其他编译器标志都遵循 MFC 默认值 (例如， `_DEBUG` 用于调试) 。

编辑库的链接器列表。 更改 *`NAFXCWD.LIB`* 为 *`MFCxxD.LIB`* ，并将更改 *`NAFXCW.LIB`* 为 *`MFCxx.LIB`* 。 替换 *`LIBC.LIB`* 为 *`MSVCRT.LIB`* 。 与任何其他 MFC 库一样， *`MFCxxD.LIB`* 放置在任何 C 运行时库 **之前** 都非常重要。

可以选择 **`/D_AFXDLL`** 同时添加到发布和调试资源编译器选项 () 实际编译资源的选项 **`/R`** 。 此选项通过共享 MFC Dll 中存在的资源，使最终的可执行文件更小。

进行这些更改后需要完全重新生成。

### <a name="building-the-samples"></a>生成示例

大多数 MFC 示例程序都可从命令行 Visual C++ 或从与 NMAKE 兼容的共享生成文件生成。

若要转换其中的任何示例以使用 *`MFCxx.DLL`* ，可以将 MAK 文件加载到 Visual C++ 中，并按上述方式设置项目选项。 如果使用的是 NMAKE 生成，则可以 `AFXDLL=1` 在 nmake 命令行上指定，它将使用共享 MFC 库生成示例。

MFC 高级概念示例 [DLLHUSK](../overview/visual-cpp-samples.md) 是用 MFC 的 DLL 版本生成的。 此示例不仅阐释了如何生成与链接的应用程序 *`MFCxx.DLL`* ，还说明了 MFC DLL 打包选项的其他功能，如本技术说明稍后部分中所述的 mfc 扩展 dll。

### <a name="packaging-notes"></a>打包笔记

 (和) Dll 的发布版本 *`MFCxx.DLL`* *`MFCxxU.DLL`* 可自由再分发。 Dll 的调试版本不可自由再发行，只应在应用程序开发过程中使用。

调试 Dll 随调试信息一起提供。 通过使用 Visual C++ 调试器，可以跟踪应用程序和 DLL 的执行情况。 发布 Dll (*`MFCxx.DLL`* 和 *`MFCxxU.DLL`*) 不包含调试信息。

如果自定义或重新生成 Dll，则应将其称为 "Mfcxx.dll" 以外的其他内容。 MFC SRC 文件 *`MFCDLL.MAK`* 描述了生成选项，并包含用于重命名 DLL 的逻辑。 重命名文件是必需的，因为这些 Dll 可能由多个 MFC 应用程序共享。 自定义版本的 MFC Dll 替换安装在系统上的 Dll 可能会破坏使用共享 MFC Dll 的其他 MFC 应用程序。

不建议重新生成 MFC Dll。

## <a name="how-the-mfcxxdll-is-implemented"></a><a name="_mfcnotes_how_the_mfc30.dll_is_implemented"></a> 如何实现 MFCxx.DLL

以下部分介绍如何实现 MFC DLL (*`MFCxx.DLL`* 和 *`MFCxxD.DLL`*) 。 如果您想要做的就是在您的应用程序中使用 MFC DLL，则了解此处的详细信息也并不重要。 此处的详细信息并不是了解如何编写 MFC 扩展 DLL 所必需的，但了解此实现可帮助您编写自己的 DLL。

### <a name="implementation-overview"></a>实现概述

MFC DLL 实际上是 MFC 扩展 DLL 的一种特殊情况，如上所述。 对于大量的类，它有大量的导出。 MFC DLL 中还有一些额外的功能，这使得它比常规 MFC 扩展 DLL 更为特殊。

### <a name="win32-does-most-of-the-work"></a>Win32 执行大部分工作

16位版本的 MFC 需要一些特殊的方法，包括堆栈段上的每个应用数据、由某些80x86 程序集代码创建的特殊段、每个进程的异常上下文和其他方法。 在大多数情况下，Win32 直接支持 DLL 中的每进程数据。 大多数情况 *`MFCxx.DLL`* 只是打包到 *`NAFXCW.LIB`* DLL 中。 如果你查看 MFC 源代码，你会发现几个 `#ifdef _AFXDLL` 事例，因为无需进行很多特殊情况。 专门用于处理 Windows 3.1 上的 Win32 的特殊案例 (也称为 Win32s) 。 Win32s 不支持对每个进程的 DLL 数据直接支持。 MFC DLL 必须使用线程本地存储 (TLS) Win32 Api 来获取进程本地数据。

### <a name="impact-on-library-sources-additional-files"></a>对库源、其他文件的影响

`_AFXDLL`版本对普通 MFC 类库源和标头的影响相对较小。 有一个特殊的版本文件 (*`AFXV_DLL.H`*) ，另外还有一个 (*`AFXDLL_.H`*) 包含在主头文件中的头文件 *`AFXWIN.H`* 。 *`AFXDLL_.H`* 标头包括 `CDynLinkLibrary` `_AFXDLL` 应用程序和 MFC 扩展 dll 的类和其他实现详细信息。 *`AFXDLLX.H`* 提供标头以生成 MFC 扩展 dll (参阅上面的详细信息) 。

MFC SRC 中 MFC 库的常规源在 #ifdef 下有一些其他条件代码 `_AFXDLL` 。 另外 (的源文件 *`DLLINIT.CPP`*) 包含用于 MFC 共享版本的额外 DLL 初始化代码和其他粘附。

为了生成 MFC 的共享版本，还提供了其他文件。 有关如何生成 DLL 的详细信息，请参阅下面的 (。 ) 

- 两个 .DEF 文件用于导出 MFC DLL 入口点以用于调试 (*`MFCxxD.DEF`*) 并发布 (*`MFCxx.DEF`*) 版本的 DLL。

- RC 文件 (*`MFCDLL.RC`*) 包含 DLL 的所有标准 MFC 资源和 `VERSIONINFO` 资源。

- 提供了一个 CLW 文件 (*`MFCDLL.CLW`*) ，以允许使用 ClassWizard 浏览 MFC 类。 此功能不特定于 MFC 的 DLL 版本。

### <a name="memory-management"></a>内存管理

使用的应用程序 *`MFCxx.DLL`* 使用由 *`MSVCRTxx.DLL`* 共享的 C 运行时 DLL 提供的通用内存分配器。 应用程序、任何 MFC 扩展 Dll，以及 MFC Dll 使用此共享内存分配器。 通过使用共享 DLL 进行内存分配，MFC Dll 可以分配以后由应用程序释放的内存，反之亦然。 由于应用程序和 DLL 都必须使用相同的分配器，因此不应重写 c + + 全局 **`operator new`** 或 **`operator delete`** 。 相同的规则适用于其他 C 运行时内存分配例程 (例如 `malloc` ，、 `realloc` `free` 和其他) 。

### <a name="ordinals-and-class-__declspecdllexport-and-dll-naming"></a>序号和类 __declspec (dllexport) 和 DLL 命名

我们不会使用 `class` **`__declspec(dllexport)`** c + + 编译器功能。 相反，类库源包含导出的列表 (*`MFCxx.DEF`* 和 *`MFCxxD.DEF`*) 。 仅导出 (函数和数据) 的一组选择入口点。 不导出其他符号，如 MFC 私有实现函数或类。 所有导出都按序号完成，常驻或非居民名称表中不包含字符串名称。

使用 `class` **`__declspec(dllexport)`** 可能是生成较小 dll 的可行替代方法，但在大型 dll （如 MFC）中，默认导出机制具有效率和容量限制。

它的意思是，我们可以将大量功能打包到 *`MFCxx.DLL`* 仅 800 KB 的版本中，而不会影响太多的执行或加载速度。 *`MFCxx.DLL`* 如果使用此方法，则会增加 100 KB。 此方法使您能够在 DEF 文件的末尾添加其他入口点。 它允许简单的版本控制，不会影响按序号导出的速度和大小效率。 MFC 类库中的主要版本修订将更改库名称。 也就是说， *`MFC30.DLL`* 是包含 MFC 类库版本3.0 的可再发行 DLL。 例如，在假设 MFC 3.1 中升级此 DLL 时，将改为命名该 DLL *`MFC31.DLL`* 。 同样，如果修改 MFC 源代码以生成 MFC DLL 的自定义版本，请使用不同的名称 (并且最好是名称) 中没有 "MFC" 的名称。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
