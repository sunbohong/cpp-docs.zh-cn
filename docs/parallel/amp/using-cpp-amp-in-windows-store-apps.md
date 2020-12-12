---
description: 了解详细信息：在 UWP 应用中使用 C++ AMP
title: 在 UWP 应用中使用 C++ AMP
ms.date: 11/04/2016
ms.assetid: 85577298-2c28-4209-9470-eb21048615db
ms.openlocfilehash: 91c7b147ff89a1fe19ebe1b18e465533053542d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97314472"
---
# <a name="using-c-amp-in-uwp-apps"></a>在 UWP 应用中使用 C++ AMP

你可以使用通用 Windows 平台 (UWP) 应用中的 C++ AMP (C++ Accelerated Massive Parallelism) 在 GPU (图形处理单元) 或其他计算加速器上执行计算。 但是，C++ AMP 不提供用于直接处理 Windows 运行时类型的 API，并且 Windows 运行时不提供 C++ AMP 包装器。 当你在代码（包括你自己创建的代码）中使用Windows 运行时类型时，必须将它们转换为与 C++ AMP 兼容的类型。

## <a name="performance-considerations"></a>性能注意事项

如果你使用 Visual C++ 组件扩展 c + +/CX 来创建通用 Windows 平台 (UWP) 应用程序，我们建议你为将与 (一起使用的数据使用纯旧数据) POD C++ AMP 类型和连续存储（例如 `std::vector` 或 C 样式数组）。 这可以帮助你获得比使用非 POD 类型或 Windows RT 容器更高的性能，因为不需要进行封送处理。

在 C++ AMP 内核中，若要访问以这种方式存储的数据，只需将 `std::vector` 或数组存储包装在中， `concurrency::array_view` 然后在循环中使用数组视图 `concurrency::parallel_for_each` ：

```cpp
// simple vector addition example
std::vector<int> data0(1024, 1);
std::vector<int> data1(1024, 2);
std::vector<int> data_out(data0.size(), 0);

concurrency::array_view<int, 1> av0(data0.size(), data0);
concurrency::array_view<int, 1> av1(data1.size(), data1);
concurrency::array_view<int, 1> av2(data_out.size(), data2);

av2.discard_data();

concurrency::parallel_for_each(av0.extent, [=](concurrency::index<1> idx) restrict(amp)
    {
        av2[idx] = av0[idx] + av1[idx];
    });
```

## <a name="marshaling-windows-runtime-types"></a>排列 Windows 运行时类型

使用 Windows 运行时 Api 时，你可能想要对存储在 Windows 运行时容器中的数据（例如） `Platform::Array<T>^` 或复杂数据类型（如使用 **ref** 关键字或 **value** 关键字声明的类或结构）使用 C++ AMP。 在这些情况下，您必须执行一些额外的工作以使数据可用于 C++ AMP。

### <a name="platformarrayt-where-t-is-a-pod-type"></a>Platform：： Array \<T> ^，其中 T 为 POD 类型

如果遇到， `Platform::Array<T>^` 而 T 是 POD 类型，只需使用成员函数即可访问其基础存储 `get` ：

```cpp
Platform::Array<float>^ arr; // Assume that this was returned by a Windows Runtime API
concurrency::array_view<float, 1> av(arr->Length, &arr->get(0));
```

如果 T 不是 POD 类型，请使用以下部分中所述的方法将数据与 C++ AMP 一起使用。

### <a name="windows-runtime-types-ref-classes-and-value-classes"></a>Windows 运行时类型: 引用类和值类

C++ AMP 不支持复杂数据类型。 这包括非 POD 类型以及使用 **ref** 关键字或 **value** 关键字声明的任何类型。 如果上下文中使用了不受支持的类型 `restrict(amp)` ，则会生成编译时错误。

遇到不支持的类型时，可以将其数据的相关部分复制到 `concurrency::array` 对象中。 除了使数据可供 C++ AMP 使用以外，此手动复制方法还可通过最大限度地提高数据位置，并确保不会使用的数据不会复制到加速器，从而提高性能。 您可以通过使用过渡阵列进一步提高性能，该 *过渡数组* 是一种特殊形式的，它 `concurrency::array` 提供对 AMP 运行时的提示，应对数组进行优化，以便在其与指定加速器上的其他数组之间频繁传输。

```cpp
// pixel_color.h
ref class pixel_color sealed
{
public:
    pixel_color(Platform::String^ color_name, int red, int green, int blue)
    {
        name = color_name;
        r = red;
        g = green;
        b = blue;
    }

    property Platform::String^ name;
    property int r;
    property int g;
    property int b;
};

// Some other file

std::vector<pixel_color^> pixels (256);

for (pixel_color ^pixel : pixels)
{
    pixels.push_back(ref new pixel_color("blue", 0, 0, 255));
}

// Create the accelerators
auto cpuAccelerator = concurrency::accelerator(concurrency::accelerator::cpu_accelerator);
auto devAccelerator = concurrency::accelerator(concurrency::accelerator::default_accelerator);

// Create the staging arrays
concurrency::array<float, 1> red_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);
concurrency::array<float, 1>  blue_vec(256, cpuAccelerator.default_view, devAccelerator.default_view);

// Extract data from the complex array of structs into staging arrays.
concurrency::parallel_for(0, 256, [&](int i)
    {
        red_vec[i] = pixels[i]->r;
        blue_vec[i] = pixels[i]->b;
    });

// Array views are still used to copy data to the accelerator
concurrency::array_view<float, 1> av_red(red_vec);
concurrency::array_view<float, 1> av_blue(blue_vec);

// Change all pixels from blue to red.
concurrency::parallel_for_each(av_red.extent, [=](index<1> idx) restrict(amp)
    {
        av_red[idx] = 255;
        av_blue[idx] = 0;
    });
```

## <a name="see-also"></a>请参阅

[使用 c + + 创建第一个 UWP 应用](/windows/uwp/get-started/create-a-basic-windows-10-app-in-cpp)<br/>
[用 C++ 创建 Windows 运行时组件](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp)
