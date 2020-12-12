---
description: '了解详细信息： CLR integration (c + +/CX) '
title: CLR 集成 (C++/CX)
ms.date: 01/22/2017
ms.assetid: 76e213cf-2f3d-4181-b35b-9fd25d5b307c
ms.openlocfilehash: ae335168ee456f0461154ab48e9d92325fdc599b
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97190232"
---
# <a name="clr-integration-ccx"></a>CLR 集成 (C++/CX)

某些 Windows 运行时类型接收 c + +/CX 中的特殊处理，以及基于公共语言运行时 (CLR) 的语言。 本文讨论一种语言中的几种类型如何映射到另一种语言。 例如，CLR 将 Windows.Foundation.IVector 映射到 System.Collections.IList，将 Windows.Foundation.IMap 映射到 System.Collections.IDictionary，等等。 同样，c + +/CX 专门映射类型，如 Platform：:D 委托和 Platform：： String。

## <a name="mapping-the-windows-runtime-to-ccx"></a>将 Windows 运行时映射到 c + +/CX

C + +/CX 读取 Windows 元数据 ( winmd) 文件时，编译器会自动将常见 Windows 运行时命名空间和类型映射到 c + +/CX 命名空间和类型。 例如，数字 Windows 运行时类型 `UInt32` 自动映射到 `default::uint32` 。

C + +/CX 将一些其他 Windows 运行时类型映射到 **平台** 命名空间。 例如， **Windows：： Foundation** HSTRING 句柄（表示只读 Unicode 文本字符串）映射到 c + +/cx `Platform::String` 类。 当 Windows 运行时操作返回错误 HRESULT 时，它将映射到 c + +/CX `Platform::Exception` 。

C + +/CX 还映射 Windows 运行时命名空间中的某些类型以增强类型的功能。 对于这些类型，c + +/CX 提供了 helper 构造函数和特定于 c + + 的方法，但在类型的标准 winmd 文件中不可用。

下表显示支持新构造函数和帮助器方法的值结构。 如果以前编写了使用结构初始化列表的代码，请将它更改为使用新添加的构造函数。

**Windows：： Foundation**

- 点

- Rect

- 大小

**Windows：： UI**

- 颜色

**Windows：： UI：： Xaml**

- CornerRadius

- 持续时间

- GridLength

- Thickness

**Windows::UI::Xaml::Interop**

- TypeName

**Windows：： UI：： Xaml：： Media**

- 矩阵

**Windows：： UI：： Xaml：： Media：：动画**

- KeyTime

- RepeatBehavior

**Windows::UI::Xaml::Media::Media3D**

- Matrix3D

## <a name="mapping-the-clr-to-ccx"></a>将 CLR 映射到 c + +/CX

当 Microsoft c + + 或 c # 编译器读取 winmd 文件时，它们会将元数据文件中的某些类型自动映射到相应的 c + +/CX 或 CLR 类型。 例如，在 CLR 中，IVector \<T> 接口映射到 IList \<T> 。 但在 c + +/CX 中，IVector \<T> 接口不会映射到另一种类型。

\<T>Windows 运行时中的 IReference 映射到 .net 中的可为 null \<T> 。

## <a name="see-also"></a>请参阅

[与其他语言互操作](../cppcx/interoperating-with-other-languages-c-cx.md)
