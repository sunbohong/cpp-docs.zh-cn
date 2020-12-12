---
description: 了解详细信息： TN058： MFC 模块状态实现
title: TN058：MFC 模块状态实现
ms.date: 06/28/2018
helpviewer_keywords:
- thread state [MFC]
- module states [MFC], managing state data
- TN058
- MFC, managing state data
- module states [MFC], switching
- DLLs [MFC], module states
- process state [MFC]
ms.assetid: 72f5b36f-b3da-4009-a144-24258dcd2b2f
ms.openlocfilehash: c4b300b9aa184e9fa1c6cfd5a8cf668d163d85ef
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97214775"
---
# <a name="tn058-mfc-module-state-implementation"></a>TN058：MFC 模块状态实现

> [!NOTE]
> 以下技术说明在首次包括在联机文档中后未更新。 因此，某些过程和主题可能已过时或不正确。 要获得最新信息，建议你在联机文档索引中搜索热点话题。

本技术说明介绍 MFC "模块状态" 结构的实现。 了解模块状态实现对于使用 DLL 中的 MFC 共享 Dll (或 OLE 进程内服务器) 至关重要。

阅读本说明之前，请参阅 [创建新文档、窗口和视图](../mfc/creating-new-documents-windows-and-views.md)中的 "管理 MFC 模块的状态数据"。 本文包含有关此主题的重要使用情况信息和概述信息。

## <a name="overview"></a>概述

有三种类型的 MFC 状态信息：模块状态、进程状态和线程状态。 有时可以组合这些状态类型。 例如，MFC 的句柄映射既是模块本地的，也是线程本地的。 这允许两个不同的模块在每个线程中具有不同的映射。

进程状态和线程状态类似。 这些数据项是在传统上是全局变量的内容，但需要特定于给定的进程或线程才能适当 Win32s 支持或正确的多线程支持。 给定数据项适用的类别取决于该项及其在进程和线程边界方面所需的语义。

模块状态是唯一的，因为它可以包含真正的全局状态或处理本地或线程本地的状态。 此外，它还可以快速切换。

## <a name="module-state-switching"></a>模块状态切换

每个线程都包含指向 "当前" 或 "活动" 模块状态的指针 (并不令人吃惊，指针是 MFC 的线程本地状态) 的一部分。 当执行线程传递模块边界（如调用到 OLE 控件或 DLL 的应用程序）或回调回应用程序的 OLE 控件时，将更改此指针。

当前模块状态通过调用切换 `AfxSetModuleState` 。 大多数情况下，你永远不会直接处理 API。 在许多情况下，MFC 将为您调用 (在 WinMain、OLE 入口点、等 ) 上。 `AfxWndProc` 这是通过静态链接的特殊中的任何组件完成的 `WndProc` ，特殊的 `WinMain` (或 `DllMain`) 知道哪个模块状态应是最新的。 可以通过查看 DLLMODUL 来查看此代码。CPP 或 APPMODUL。MFC\SRC 目录中的 CPP。

很少需要设置模块状态，然后再将其设置回。 大多数情况下，您希望将自己的模块状态 "推送" 为当前模块状态，然后在完成后，"弹出" 原始上下文。 这是由宏 [AFX_MANAGE_STATE](reference/extension-dll-macros.md#afx_manage_state) 和特殊类完成的 `AFX_MAINTAIN_STATE` 。

`CCmdTarget` 具有用于支持模块状态切换的特殊功能。 具体而言， `CCmdTarget` 是用于 ole 自动化和 OLE COM 入口点的根类。 与向系统公开的任何其他入口点一样，这些入口点必须设置正确的模块状态。 给定如何 `CCmdTarget` 知道 "正确" 模块状态应该是什么结果，这是因为它会 "记住" "当前" 模块状态在构造时的状态，以便在以后调用时，它可以将当前模块状态设置为 "已记住" 值。 因此，给定 `CCmdTarget` 对象所关联的模块状态是构造对象时的当前模块状态。 请简单简单地加载 INPROC 服务器、创建对象并调用其方法。

1. 使用 OLE 加载 DLL `LoadLibrary` 。

1. `RawDllMain` 首先调用。 它将模块状态设置为 DLL 的已知静态模块状态。 出于此原因 `RawDllMain` ，将静态链接到 DLL。

1. 调用与我们的对象关联的类工厂的构造函数。 `COleObjectFactory` 派生自，因此 `CCmdTarget` ，它会记住它所实例化的模块状态。 这一点很重要，即当要求类工厂创建对象时，它现在知道要使其成为最新状态的模块状态。

1. `DllGetClassObject` 调用以获取类工厂。 MFC 会搜索与此模块关联的类工厂列表，并将其返回。

1. 调用 `COleObjectFactory::XClassFactory2::CreateInstance`。 在创建对象并将其返回之前，此函数将模块状态设置为第3步中当前的模块状态， (实例化) 时的当前状态 `COleObjectFactory` 。 此操作在 [METHOD_PROLOGUE](com-interface-entry-points.md)中完成。

1. 当创建对象时，它也是一 `CCmdTarget` 种衍生方法，并以 `COleObjectFactory` 记住哪个模块状态处于活动状态，因此这种新对象。 现在对象知道在调用时要切换到的模块状态。

1. 客户端从其调用接收的 OLE COM 对象调用函数 `CoCreateInstance` 。 调用对象时，它将使用 `METHOD_PROLOGUE` 来切换模块状态，就像一样 `COleObjectFactory` 。

正如您所看到的，在创建模块状态时，模块状态将从对象传播到对象。 必须正确设置模块状态，这一点很重要。 如果未设置此项，则您的 DLL 或 COM 对象可能会与调用它的 MFC 应用程序很糟糕，或者可能找不到自己的资源，或者可能以其他电影院方式失败。

请注意，某些类型的 Dll （具体而言，"MFC 扩展" Dll）实际上不会将模块状态切换到其 `RawDllMain` (中，它们甚至不会有 `RawDllMain`) 。 这是因为它们在使用它们的应用程序中实际存在。 它们很多是正在运行的应用程序的一部分，其目的是修改应用程序的全局状态。

OLE 控件和其他 Dll 非常不同。 它们不需要修改调用应用程序的状态;调用它们的应用程序甚至可能不是 MFC 应用程序，因此可能没有要修改的状态。 这就是我们的模块状态切换的原因。

对于 DLL 中的导出函数（如在 DLL 中启动对话框的函数），需要将以下代码添加到函数的开头：

```cpp
AFX_MANAGE_STATE(AfxGetStaticModuleState())
```

这会将当前模块状态替换为从 [AfxGetStaticModuleState](reference/extension-dll-macros.md#afxgetstaticmodulestate) 返回的状态，直到当前范围结束。

如果未使用 AFX_MODULE_STATE 宏，将出现 Dll 中资源的问题。 默认情况下，MFC 使用主应用程序的资源句柄来加载资源模板。 此模板实际存储在 DLL 中。 根本原因是 MFC 的模块状态信息尚未通过 AFX_MODULE_STATE 宏进行切换。 资源句柄将从 MFC 的模块状态中恢复。 不切换模块状态将导致使用错误的资源句柄。

AFX_MODULE_STATE 不需要放在 DLL 中的每个函数中。 例如， `InitInstance` 可以在不 AFX_MODULE_STATE 的情况下，应用程序中的 mfc 代码调用，因为 mfc 会自动将模块状态转移 `InitInstance` 到前面，然后在返回后切换回 `InitInstance` 。 对于所有消息映射处理程序也是如此。 在路由任何消息之前，普通 MFC Dll 实际上有一个特殊的主窗口过程，该过程会自动切换模块状态。

## <a name="process-local-data"></a>处理本地数据

处理本地数据并不是如此重要的问题，因为它不是 Win32s DLL 模型的难点。 在 Win32s 中，所有 Dll 共享其全局数据，即使是由多个应用程序加载时也是如此。 这与 "实际" Win32 DLL 数据模型非常不同，其中每个 DLL 在附加到 DLL 的每个进程中获取其数据空间的单独副本。 为了增加复杂性，在 Win32s DLL 中的堆上分配的数据实际上是特定于进程的 (，) 拥有所有权。 请考虑以下数据和代码：

```cpp
static CString strGlobal; // at file scope

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, strGlobal);
}
```

如果上面的代码位于 DLL 中并且 DLL 由两个进程 A 和 (B 加载，则会发生什么情况，事实上，这是同一应用程序) 的两个实例。 调用 `SetGlobalString("Hello from A")` 。 因此，内存将分配给 `CString` 进程 a 上下文中的数据。请记住，本身是全局的，对 `CString` a 和 B 均可见。现在 B 调用 `GetGlobalString(sz, sizeof(sz))` 。 B 将能够查看集合中的数据。 这是因为，Win32s 在 Win32 等进程之间不提供保护。 这是第一个问题;在许多情况下，不需要让一个应用程序影响被视为属于不同应用程序的全局数据。

还有其他问题。 假设现在会退出。 退出时，"" 字符串使用的内存 `strGlobal` 可供系统使用，也就是说，由操作系统分配的所有内存将自动释放。 它不会被释放，因为 `CString` 析构函数正在被调用; 尚未调用它。 它只是因为分配它的应用程序离开了场景。 现在，如果调用了 B `GetGlobalString(sz, sizeof(sz))` ，则它可能不会获得有效的数据。 其他一些应用程序可能已使用该内存进行了其他操作。

显然存在问题。 MFC 2.x 使用称为线程本地存储 (TLS) 的技术。 MFC 1.x 会将 Win32s 下的 TLS 索引分配为进程本地存储索引（即使未调用该索引），然后将基于该 TLS 索引引用所有数据。 这类似于在 Win32 上用于存储线程本地数据的 TLS 索引 (参见下面的详细信息) 。 这会导致每个 MFC DLL 每个进程使用至少两个 TLS 索引。 当你考虑加载多个 OLE 控件 Dll (OCXs) 时，你很快就会用完 TLS 索引， (只有64可用) 。 此外，MFC 必须将所有这些数据放在一个位置，并将其放在一个结构中。 它不是非常可扩展的，并且在使用 TLS 索引方面并不理想。

MFC 4.x 使用一组类模板来处理这种情况，您可以围绕应处理本地数据的数据进行 "换行"。 例如，上面提到的问题可以通过编写来解决：

```cpp
struct CMyGlobalData : public CNoTrackObject
{
    CString strGlobal;
};
CProcessLocal<CMyGlobalData> globalData;

__declspec(dllexport)
void SetGlobalString(LPCTSTR lpsz)
{
    globalData->strGlobal = lpsz;
}

__declspec(dllexport)
void GetGlobalString(LPCTSTR lpsz, size_t cb)
{
    StringCbCopy(lpsz, cb, globalData->strGlobal);
}
```

MFC 在两个步骤中实现此操作。 首先，Win32 __Tls \*__ api 的顶层有 (**TlsAlloc**、 **TlsSetValue**、 **TlsGetValue** 等 ) ，无论有多少个 DLL，每个进程仅使用两个 Tls 索引。 其次， `CProcessLocal` 提供模板以访问此数据。 它会重写操作员 > 这就允许您看到的直观语法。 包装的所有对象都 `CProcessLocal` 必须派生自 `CNoTrackObject` 。 `CNoTrackObject`提供一个较低级别分配器 (**LocalAlloc** / **LocalFree**) 和一个虚拟析构函数，以便 MFC 可以在进程终止时自动销毁进程本地对象。 如果需要其他清理，此类对象可以具有自定义析构函数。 上面的示例不需要一个，因为编译器将生成一个默认析构函数以销毁嵌入的 `CString` 对象。

此方法还有其他一些有趣的优点。 不只会 `CProcessLocal` 自动销毁所有对象，而是在需要时才对其进行构造。 `CProcessLocal::operator->` 第一次调用时，将实例化关联的对象，而不会更早地实例化。 在上面的示例中，这意味着在 `strGlobal` 第一次或调用之前，将不会构造 "" 字符串 `SetGlobalString` `GetGlobalString` 。 在某些情况下，这有助于减少 DLL 启动时间。

## <a name="thread-local-data"></a>线程本地数据

类似于处理本地数据，当数据必须是给定线程的本地数据时，使用线程本地数据。 也就是说，需要为访问该数据的每个线程提供单独的数据实例。 这可以用来代替广泛的同步机制。 如果数据无需由多个线程共享，则这种机制可能会很昂贵且不必要。 假设有一个 `CString` 对象 (与上面) 的示例非常类似。 我们可以将其与模板一起使用来使其成为本地线程 `CThreadLocal` ：

```cpp
struct CMyThreadData : public CNoTrackObject
{
    CString strThread;
};
CThreadLocal<CMyThreadData> threadData;

void MakeRandomString()
{
    // a kind of card shuffle (not a great one)
    CString& str = threadData->strThread;
    str.Empty();
    while (str.GetLength() != 52)
    {
        unsigned int randomNumber;
        errno_t randErr;
        randErr = rand_s(&randomNumber);

        if (randErr == 0)
        {
            TCHAR ch = randomNumber % 52 + 1;
            if (str.Find(ch) <0)
            str += ch; // not found, add it
        }
    }
}
```

如果 `MakeRandomString` 是从两个不同的线程调用的，则每个线程都将以不同的方式 "无序"，而不会干扰其他线程。 这是因为实际上 `strThread` 每个线程都有一个实例，而不只是一个全局实例。

请注意如何使用引用来捕获 `CString` 一次地址，而不是每次循环迭代一次。 循环代码可能已在 `threadData->strThread` 使用 "" 的任何地方编写 `str` ，但在执行时代码会变得很慢。 当循环中出现此类引用时，最好缓存对数据的引用。

`CThreadLocal`类模板使用的机制与相同的 `CProcessLocal` 实现方法相同。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
