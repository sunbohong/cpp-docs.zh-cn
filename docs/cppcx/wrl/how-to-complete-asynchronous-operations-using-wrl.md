---
description: 了解详细信息：如何：使用 WRL 完成异步操作
title: 如何：使用 WRL 完成异步操作
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 02173eae-731b-49bc-b412-f1f69388b99d
ms.openlocfilehash: f8c929d737f113d995b5d171896517b3d94a6aa4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97124587"
---
# <a name="how-to-complete-asynchronous-operations-using-wrl"></a>如何：使用 WRL 完成异步操作

本文档演示如何使用 Windows 运行时 c + + 模板库 (WRL) 启动异步操作，并在操作完成时执行工作。

本文档显示了两个示例。 第一个示例启动异步计时器并等待计时器过期。 在此示例中，您将在创建 timer 对象时指定异步操作。 第二个示例运行后台工作线程。 此示例演示如何使用返回接口的 Windows 运行时方法 `IAsyncInfo` 。 [回调](callback-function-wrl.md)函数是这两个示例的重要部分，因为它使它们能够指定事件处理程序来处理异步操作的结果。

有关创建组件实例和检索属性值的更多基本示例，请参阅 [如何：激活和使用 Windows 运行时组件](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)。

> [!TIP]
> 这些示例使用 lambda 表达式来定义回调。 你还可以使用函数对象 (函子) 、函数指针或 [std：： function](../../standard-library/function-class.md) 对象。 有关 c + + lambda 表达式的详细信息，请参阅 [Lambda 表达式](../../cpp/lambda-expressions-in-cpp.md)。

## <a name="example-working-with-a-timer"></a>示例：使用计时器

以下步骤启动异步计时器并等待计时器过期。 下面是完整的示例。

> [!WARNING]
> 尽管通常在通用 Windows 平台 (UWP) 应用程序中使用 Windows 运行时 c + + 模板库，但本示例使用控制台应用程序进行说明。 某些函数（如）在 `wprintf_s` UWP 应用中不可用。 有关可在 UWP 应用中使用的类型和函数的详细信息，请参阅 [通用 Windows 平台应用中不支持的 CRT 函数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) 以及 [Uwp 应用的 Win32 和 COM](/uwp/win32-and-com/win32-and-com-for-uwp-apps)。

1. 包括 (`#include`) 任何所需的 Windows 运行时、Windows 运行时 c + + 模板库或 c + + 标准库标头。

   [!code-cpp[wrl-consume-async#2](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_1.cpp)]

   `Windows.System.Threading.h` 声明使用异步计时器所需的类型。

   我们建议您在 .cpp 文件中使用 `using namespace` 指令使代码更具可读性。

2. 初始化 Windows 运行时。

   [!code-cpp[wrl-consume-async#3](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_2.cpp)]

3. 为接口创建激活工厂 `ABI::Windows::System::Threading::IThreadPoolTimer` 。

   [!code-cpp[wrl-consume-async#4](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_3.cpp)]

   Windows 运行时使用完全限定的名称标识类型。 `RuntimeClass_Windows_System_Threading_ThreadPoolTimer`参数是由 Windows 运行时提供的字符串，它包含所需的运行时类名称。

4. 创建一个 [事件](event-class-wrl.md) 对象，用于将计时器回调同步到主应用。

   [!code-cpp[wrl-consume-async#5](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_4.cpp)]

   > [!NOTE]
   > 此事件仅用于演示，作为控制台应用程序的一部分。 此示例使用事件确保异步操作在应用退出前完成。 在大多数应用中，通常不会等待异步操作完成。

5. 创建一个 `IThreadPoolTimer` 在两秒钟后过期的对象。 使用 `Callback` 函数可以 (对象) 创建事件处理程序 `ABI::Windows::System::Threading::ITimerElapsedHandler` 。

   [!code-cpp[wrl-consume-async#6](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_5.cpp)]

6. 将消息打印到控制台并等待计时器回调完成。 所有 `ComPtr` 和 RAII 对象都离开范围并自动释放。

   [!code-cpp[wrl-consume-async#7](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_6.cpp)]

下面是完整的示例：

[!code-cpp[wrl-consume-async#1](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_7.cpp)]

### <a name="compiling-the-code"></a>编译代码

若要编译代码，请复制代码，然后将其粘贴到 Visual Studio 项目中，或粘贴到一个名为的文件中， `wrl-consume-async.cpp` 然后在 Visual Studio 命令提示符窗口中运行以下命令。

`cl.exe wrl-consume-async.cpp runtimeobject.lib`

## <a name="example-working-with-a-background-thread"></a>示例：使用后台线程

以下步骤启动工作线程，并定义该线程执行的操作。 下面是完整的示例。

> [!TIP]
> 此示例演示如何使用 `ABI::Windows::Foundation::IAsyncAction` 接口。 可以将此模式应用于任何实现的接口 `IAsyncInfo` ： `IAsyncAction` 、 `IAsyncActionWithProgress` 、 `IAsyncOperation` 和 `IAsyncOperationWithProgress` 。

1. 包括 (`#include`) 任何所需的 Windows 运行时、Windows 运行时 c + + 模板库或 c + + 标准库标头。

   [!code-cpp[wrl-consume-asyncOp#2](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_8.cpp)]

   Windows.System。Thread 声明使用工作线程所需的类型。

   建议 `using namespace` 在 .cpp 文件中使用指令，使代码更具可读性。

2. 初始化 Windows 运行时。

   [!code-cpp[wrl-consume-asyncOp#3](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_9.cpp)]

3. 为接口创建激活工厂 `ABI::Windows::System::Threading::IThreadPoolStatics` 。

   [!code-cpp[wrl-consume-asyncOp#4](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_10.cpp)]

4. 创建一个 [事件](event-class-wrl.md) 对象，它将工作线程完成同步到主应用。

   [!code-cpp[wrl-consume-asyncOp#5](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_11.cpp)]

   > [!NOTE]
   > 此事件仅用于演示，作为控制台应用程序的一部分。 此示例使用事件确保异步操作在应用退出前完成。 在大多数应用中，通常不会等待异步操作完成。

5. 调用 `IThreadPoolStatics::RunAsync` 方法以创建工作线程。 使用 `Callback` 函数定义操作。

   [!code-cpp[wrl-consume-asyncOp#6](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_12.cpp)]

   `IsPrime`函数在下面的完整示例中定义。

6. 将消息打印到控制台并等待线程完成。 所有 `ComPtr` 和 RAII 对象都离开范围并自动释放。

   [!code-cpp[wrl-consume-asyncOp#7](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_13.cpp)]

下面是完整的示例：

[!code-cpp[wrl-consume-asyncOp#1](../codesnippet/CPP/how-to-complete-asynchronous-operations-using-wrl_14.cpp)]

### <a name="compiling-the-code"></a>编译代码

若要编译代码，请复制代码，然后将其粘贴到 Visual Studio 项目中，或粘贴到一个名为的文件中， `wrl-consume-asyncOp.cpp` 然后在 **Visual Studio 命令提示符** 窗口中运行以下命令。

`cl.exe wrl-consume-asyncOp.cpp runtimeobject.lib`

## <a name="see-also"></a>请参阅

[Windows 运行时 C++ 模板库 (WRL)](windows-runtime-cpp-template-library-wrl.md)
