---
description: 了解详细信息：如何：使用 WRL 处理事件
title: 如何：使用 WRL 处理事件
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1c77543f-7b0c-4a94-93bf-e3225885ed76
ms.openlocfilehash: b1be04c1356594e2dc2060d031f35d836ad277bb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97229179"
---
# <a name="how-to-handle-events-using-wrl"></a>如何：使用 WRL 处理事件

本文档演示如何使用 Windows 运行时 c + + 模板库 (WRL) 订阅和处理 Windows 运行时对象的事件。

有关创建该组件的实例并检索属性值的更多基本示例，请参阅 [如何：激活和使用 Windows 运行时组件](how-to-activate-and-use-a-windows-runtime-component-using-wrl.md)。

## <a name="subscribing-to-and-handling-events"></a>订阅和处理事件

以下步骤启动 `ABI::Windows::System::Threading::IDeviceWatcher` 对象，并使用事件处理程序监视进度。 `IDeviceWatcher`接口使你能够以异步方式枚举设备，或在后台枚举设备，并在添加、删除或更改设备时接收通知。 [回调](callback-function-wrl.md)函数是此示例的重要部分，因为它使它能够指定处理后台操作结果的事件处理程序。 下面是完整的示例。

> [!WARNING]
> 尽管通常在通用 Windows 平台应用程序中使用 Windows 运行时 c + + 模板库，但本示例使用控制台应用程序进行说明。 `wprintf_s`通用 Windows 平台应用中无法使用等函数。 有关可在通用 Windows 平台应用中使用的类型和函数的详细信息，请参阅 [通用 Windows 平台应用中不支持的 CRT 函数](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md) 、适用 [于 UWP 应用的 Win32 和 COM](/uwp/win32-and-com/win32-and-com-for-uwp-apps)。

1. 包括 (`#include`) 任何所需的 Windows 运行时、Windows 运行时 c + + 模板库或 c + + 标准库标头。

   [!code-cpp[wrl-consume-event#2](../codesnippet/CPP/how-to-handle-events-using-wrl_1.cpp)]

   `Windows.Devices.Enumeration.h` 声明枚举设备所需的类型。

   我们建议您在 .cpp 文件中使用 `using namespace` 指令使代码更具可读性。

2. 声明应用的局部变量。 此示例包含枚举的设备数和注册令牌的计数，使其能够在以后取消对事件的订阅。

   [!code-cpp[wrl-consume-event#7](../codesnippet/CPP/how-to-handle-events-using-wrl_2.cpp)]

3. 初始化 Windows 运行时。

   [!code-cpp[wrl-consume-event#3](../codesnippet/CPP/how-to-handle-events-using-wrl_3.cpp)]

4. 创建一个 [事件](event-class-wrl.md) 对象，以便将枚举过程的完成同步到主应用。

   [!code-cpp[wrl-consume-event#4](../codesnippet/CPP/how-to-handle-events-using-wrl_4.cpp)]

   > [!NOTE]
   > 此事件仅用于演示，作为控制台应用程序的一部分。 此示例使用事件确保异步操作在应用退出前完成。 在大多数应用中，通常不会等待异步操作完成。

5. 为接口创建激活工厂 `IDeviceWatcher` 。

   [!code-cpp[wrl-consume-event#5](../codesnippet/CPP/how-to-handle-events-using-wrl_5.cpp)]

   Windows 运行时使用完全限定的名称标识类型。 `RuntimeClass_Windows_Devices_Enumeration_DeviceInformation`参数是由 Windows 运行时提供的字符串，它包含所需的运行时类名称。

6. 创建 `IDeviceWatcher` 对象。

   [!code-cpp[wrl-consume-event#6](../codesnippet/CPP/how-to-handle-events-using-wrl_6.cpp)]

7. 使用 `Callback` 函数订阅 `Added` 、 `EnumerationCompleted` 和 `Stopped` 事件。

   [!code-cpp[wrl-consume-event#8](../codesnippet/CPP/how-to-handle-events-using-wrl_7.cpp)]

   此 `Added` 事件处理程序将增加枚举设备的计数。 在找到十个设备后，它将停止枚举过程。

   `Stopped`事件处理程序将删除事件处理程序并设置完成事件。

   该 `EnumerationCompleted` 事件处理程序将停止枚举进程。 如果设备数少于10个，我们会处理此事件。

   > [!TIP]
   > 此示例使用 lambda 表达式来定义回调。 你还可以使用函数对象 (函子) 、函数指针或 [std：： function](../../standard-library/function-class.md) 对象。 有关 lambda 表达式的详细信息，请参阅 [Lambda 表达式](../../cpp/lambda-expressions-in-cpp.md)。

8. 启动枚举过程。

   [!code-cpp[wrl-consume-event#9](../codesnippet/CPP/how-to-handle-events-using-wrl_8.cpp)]

9. 等待枚举过程完成，然后打印一条消息。 所有 `ComPtr` 和 RAII 对象都离开范围并自动释放。

   [!code-cpp[wrl-consume-event#10](../codesnippet/CPP/how-to-handle-events-using-wrl_9.cpp)]

下面是完整的示例：

[!code-cpp[wrl-consume-event#1](../codesnippet/CPP/how-to-handle-events-using-wrl_10.cpp)]

## <a name="compiling-the-code"></a>编译代码

若要编译代码，请复制代码，然后将其粘贴到 Visual Studio 项目中，或粘贴到一个名为的文件中， `wrl-consume-events.cpp` 然后在 **Visual Studio 命令提示符** 窗口中运行以下命令。

`cl.exe wrl-consume-events.cpp runtimeobject.lib`

## <a name="see-also"></a>请参阅

[Windows 运行时 C++ 模板库 (WRL)](windows-runtime-cpp-template-library-wrl.md)
