---
description: 了解详细信息：如何：直接实例化 WRL 组件
title: 如何：直接实例化 WRL 组件
ms.date: 11/04/2016
ms.topic: reference
ms.assetid: 1a9fa011-0cee-4abf-bf83-49adf53ff906
ms.openlocfilehash: 424b3ec70921de9558fd8c5035e96b2fe4d58f7b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97249888"
---
# <a name="how-to-instantiate-wrl-components-directly"></a>如何：直接实例化 WRL 组件

了解如何使用 Windows 运行时 c + + 模板库 (WRL) [Microsoft：： WRL：： Make](make-function.md) 和 [MICROSOFT：： WRL：:D Etails：： MakeAndInitialize](makeandinitialize-function.md) 函数从定义组件的模块实例化组件。

通过直接实例化组件，可以在不需要类工厂或其他机制时降低开销。 可以直接在通用 Windows 平台应用和桌面应用中实例化组件。

若要了解如何使用 Windows 运行时 c + + 模板库来创建经典 COM 组件并从外部桌面应用对其进行实例化，请参阅 [如何：创建经典 Com 组件](how-to-create-a-classic-com-component-using-wrl.md)。

本文档显示了两个示例。 第一个示例使用 `Make` 函数来实例化组件。 第二个示例使用 `MakeAndInitialize` 函数来实例化可能在构造过程中失败的组件。  (因为 COM 通常使用 HRESULT 值而不是异常来指示错误，COM 类型通常不会从其构造函数引发。 `MakeAndInitialize` 允许组件通过方法验证其构造参数 `RuntimeClassInitialize` 。 ) 两个示例都定义了一个基本的记录器接口，并通过定义将消息写入控制台的类来实现该接口。

> [!IMPORTANT]
> 不能使用 `new` 运算符实例化 Windows 运行时 c + + 模板库组件。 因此，建议你始终使用 `Make` 或 `MakeAndInitialize` 直接实例化组件。

### <a name="to-create-and-instantiate-a-basic-logger-component"></a>创建并实例化基本记录器组件

1. 在 Visual Studio 中，创建一个 **Win32 控制台应用程序** 项目。 为该项目命名，例如， *WRLLogger*。

2. 将 **Midl 文件 ( .idl)** 文件添加到项目中，将该文件命名为 `ILogger.idl` ，然后添加以下代码：

   [!code-cpp[wrl-logger-make#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_1.idl)]

3. 使用以下代码替换的内容 `WRLLogger.cpp` 。

   [!code-cpp[wrl-logger-make#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_2.cpp)]

### <a name="to-handle-construction-failure-for-the-basic-logger-component"></a>处理基本记录器组件的构造失败

1. 使用以下代码替换类的定义 `CConsoleWriter` 。 此版本包含私有字符串成员变量，并重写 `RuntimeClass::RuntimeClassInitialize` 方法。 `RuntimeClassInitialize` 如果调用失败，则将失败 `SHStrDup` 。

   [!code-cpp[wrl-logger-makeandinitialize#1](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_3.cpp)]

2. 使用以下代码替换的定义 `wmain` 。 此版本使用 `MakeAndInitialize` 实例化 `CConsoleWriter` 对象并检查 HRESULT 结果。

   [!code-cpp[wrl-logger-makeandinitialize#2](../codesnippet/CPP/how-to-instantiate-wrl-components-directly_4.cpp)]

## <a name="see-also"></a>请参阅

[Windows 运行时 C++ 模板库 (WRL)](windows-runtime-cpp-template-library-wrl.md)<br/>
[Microsoft：： WRL：： Make](make-function.md)<br/>
[Microsoft：： WRL：:D etails：： MakeAndInitialize](makeandinitialize-function.md)
