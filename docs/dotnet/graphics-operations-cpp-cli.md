---
description: '了解详细信息：图形操作 (c + +/CLI) '
title: 图形操作 (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- GDI+ [C++]
- .NET Framework [C++], graphics
- images [C++], .NET Framework and
- GDI+ [C++], about graphics operations
- graphics [C++], .NET Framework and
- GDI+ [C++], displaying images
- graphics [C++], displaying images
- GDI+, drawing shapes
- drawing, shapes
- shapes
- shapes, drawing
- GDI+ [C++], rotating images
- graphics [C++], rotating images
- GDI+ [C++], converting image file formats
- graphics [C++], converting image file formats
ms.assetid: bba27228-b9b3-4c9c-b31c-a04b76702a95
ms.openlocfilehash: 84dbc75aa306219b8733848ece5c594ca40a0489
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97223537"
---
# <a name="graphics-operations-ccli"></a>图形操作 (C++/CLI)

演示如何使用 Windows SDK 进行图像操作。

以下主题演示了 <xref:System.Drawing.Image?displayProperty=fullName> 如何使用类来执行图像操作。

## <a name="display-images-with-the-net-framework"></a><a name="display"></a> 显示具有 .NET Framework 的图像

下面的代码示例修改了 OnPaint 事件处理程序，以检索指向 <xref:System.Drawing.Graphics> 主窗体的对象的指针。 <xref:System.Windows.Forms.Form.OnPaint%2A>函数适用于 Windows 窗体应用程序，很可能是使用 Visual Studio 应用程序向导创建的。

图像由 <xref:System.Drawing.Image> 类表示。 使用方法将图像数据从 .jpg 文件加载 <xref:System.Drawing.Image.FromFile%2A?displayProperty=fullName> 。 在将图像绘制到窗体之前，将调整窗体的大小以容纳图像。 图像的绘制是通过方法来执行的 <xref:System.Drawing.Graphics.DrawImage%2A?displayProperty=fullName> 。

<xref:System.Drawing.Graphics>和 <xref:System.Drawing.Image> 类都位于 <xref:System.Drawing?displayProperty=fullName> 命名空间中。

### <a name="example"></a>示例

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;

protected:
virtual Void Form1::OnPaint(PaintEventArgs^ pe) override
{
    Graphics^ g = pe->Graphics;
    Image^ image = Image::FromFile("SampleImage.jpg");
    Form::ClientSize = image->Size;
    g->DrawImage( image, 0, 0, image->Size.Width, image->Size.Height );
}
```

## <a name="draw-shapes-with-the-net-framework"></a><a name="draw"></a> 绘制具有 .NET Framework 的形状

下面的代码示例使用 <xref:System.Drawing.Graphics> 类来修改 <xref:System.Windows.Forms.Form.OnPaint%2A> 事件处理程序，以检索指向 <xref:System.Drawing.Graphics> 主窗体的对象的指针。 然后，将使用此指针设置窗体的背景色，并使用和方法绘制线条和弧线 <xref:System.Drawing.Graphics.DrawLine%2A?displayProperty=fullName> <xref:System.Drawing.Graphics.DrawArc%2A> 。

### <a name="example"></a>示例

```cpp
#using <system.drawing.dll>
using namespace System;
using namespace System::Drawing;
// ...
protected:
virtual Void Form1::OnPaint(PaintEventArgs^ pe ) override
{
   Graphics^ g = pe->Graphics;
   g->Clear(Color::AntiqueWhite);

   Rectangle rect = Form::ClientRectangle;
   Rectangle smallRect;
   smallRect.X = rect.X + rect.Width / 4;
   smallRect.Y = rect.Y + rect.Height / 4;
   smallRect.Width = rect.Width / 2;
   smallRect.Height = rect.Height / 2;

   Pen^ redPen = gcnew Pen(Color::Red);
   redPen->Width = 4;
   g->DrawLine(redPen, 0, 0, rect.Width, rect.Height);

   Pen^ bluePen = gcnew Pen(Color::Blue);
   bluePen->Width = 10;
   g->DrawArc( bluePen, smallRect, 90, 270 );
}
```

## <a name="rotate-images-with-the-net-framework"></a><a name="rotate"></a> 旋转带有 .NET Framework 的图像

下面的代码示例演示如何使用 <xref:System.Drawing.Image?displayProperty=fullName> 类从磁盘加载图像，并将其旋转90度，并将其另存为新的 .jpg 文件。

### <a name="example"></a>示例

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;

int main()
{
   Image^ image = Image::FromFile("SampleImage.jpg");
   image->RotateFlip( RotateFlipType::Rotate90FlipNone );
   image->Save("SampleImage_rotated.jpg");
   return 0;
}
```

## <a name="convert-image-file-formats-with-the-net-framework"></a><a name="convert"></a> 转换图像文件格式和 .NET Framework

下面的代码示例演示 <xref:System.Drawing.Image?displayProperty=fullName> <xref:System.Drawing.Imaging.ImageFormat?displayProperty=fullName> 用于转换和保存图像文件的类和枚举。 下面的代码从 .jpg 文件加载图像，然后将其保存为 .gif 和 .bmp 文件格式。

### <a name="example"></a>示例

```cpp
#using <system.drawing.dll>

using namespace System;
using namespace System::Drawing;
using namespace System::Drawing::Imaging;

int main()
{
   Image^ image = Image::FromFile("SampleImage.jpg");
   image->Save("SampleImage.png", ImageFormat::Png);
   image->Save("SampleImage.bmp", ImageFormat::Bmp);

   return 0;
}
```

## <a name="related-sections"></a>相关章节

[图形编程入门](/dotnet/framework/winforms/advanced/getting-started-with-graphics-programming)

[关于 GDI+ 托管代码](/dotnet/framework/winforms/advanced/about-gdi-managed-code)

## <a name="see-also"></a>请参阅

[用 c + +/CLI (Visual C++ 的 .NET 编程) ](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)

<xref:System.Drawing>
