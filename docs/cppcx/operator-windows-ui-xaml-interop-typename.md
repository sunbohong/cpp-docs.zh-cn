---
description: 了解有关以下内容的详细信息： operator Windows：： UI：： Xaml：： Interop：： TypeName
title: 运算符 Windows::UI::Xaml::Interop::TypeName
ms.date: 12/30/2016
ms.assetid: a65a105e-7e3a-452f-932f-2cdaf00fbba5
ms.openlocfilehash: 3c4c856fcf93214959f75f861b035dbdee9b94a6
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97145712"
---
# <a name="operator-windowsuixamlinteroptypename"></a>运算符 Windows::UI::Xaml::Interop::TypeName

实现从 `Platform::Type` 到 [Windows::UI::Xaml::Interop::TypeName](/uwp/api/windows.ui.xaml.interop.typename)的转换。

## <a name="syntax"></a>语法

```cpp
Operator TypeName(Platform::Type^ type);
```

### <a name="return-value"></a>返回值

给定 [时返回](/uwp/api/windows.ui.xaml.interop.typename) Windows::UI::Xaml::Interop::TypeName `Platform::Type^`。

### <a name="remarks"></a>备注

`TypeName` 是表示类型信息的中性语言 Windows 运行时结构。 [Platform::Type](../cppcx/platform-type-class.md) 特定于 C++，无法通过应用程序二进制接口 (ABI) 传递。 下面是 `TypeName`在 [Navigate](/uwp/api/windows.ui.xaml.controls.frame.navigate) 函数中的一种用法：

```cpp
rootFrame->Navigate(TypeName(MainPage::typeid), e->Arguments);
```

### <a name="example"></a>示例

下一示例演示如何在 `TypeName` 和 `Type`之间转换。

```cpp
// Convert from Type to TypeName
Windows::UI::Xaml::Interop::TypeName tn = TypeName(MainPage::typeid);

// Convert back from TypeName to Type
Type^ tx2 = (Type^)(tn);
```

## <a name="net-framework-equivalent"></a>.NET Framework 等效项

.NET Framework 程序将 `TypeName` 投影为 [System.Type](/dotnet/api/system.type)的转换。

### <a name="requirements"></a>要求

## <a name="see-also"></a>另请参阅

[运算符 Windows::UI::Xaml::Interop::TypeName](../cppcx/operator-windows-ui-xaml-interop-typename.md)<br/>
[Platform：： Type 类](../cppcx/platform-type-class.md)
