---
description: 了解详细信息：如何：定义和安装全局异常处理程序
title: 如何：定义和安装全局异常处理程序
ms.date: 11/04/2016
helpviewer_keywords:
- handlers, global
ms.assetid: dd88a812-3bc7-4ce8-8283-4b674c246534
ms.openlocfilehash: 6747e0bdf95ae4d87ed667576852c282e05a7d6d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97258325"
---
# <a name="how-to-define-and-install-a-global-exception-handler"></a>如何：定义和安装全局异常处理程序

下面的代码示例演示如何捕获未经处理的异常。 示例窗体包含一个按钮，在按下该按钮时，将执行空引用，从而引发异常。 此功能表示典型的代码失败。 产生的异常由 main 函数所安装的应用程序范围的异常处理程序捕获。

这是通过将委托绑定到事件来完成的 <xref:System.Windows.Forms.Application.ThreadException> 。 在这种情况下，随后的异常将发送到 `App::OnUnhandled` 方法。

## <a name="example"></a>示例

```cpp
// global_exception_handler.cpp
// compile with: /clr
#using <system.dll>
#using <system.drawing.dll>
#using <system.windows.forms.dll>

using namespace System;
using namespace System::Threading;
using namespace System::Drawing;
using namespace System::Windows::Forms;

ref class MyForm : public Form
{
   Button^ b;
public:
   MyForm( )
   {
      b = gcnew Button( );
      b->Text = "Do Null Access";
      b->Size = Drawing::Size(150, 30);
      b->Click += gcnew EventHandler(this, &MyForm::OnClick);
      Controls->Add(b);
   }
   void OnClick(Object^ sender, EventArgs^ args)
   {
      // do something illegal, like call through a null pointer...
      Object^ o = nullptr;
      o->ToString( );
   }
};

ref class App
{
public:
   static void OnUnhandled(Object^ sender, ThreadExceptionEventArgs^ e)
   {
      MessageBox::Show(e->Exception->Message, "Global Exeception");
      Application::ExitThread( );
   }
};

int main()
{
   Application::ThreadException += gcnew
      ThreadExceptionEventHandler(App::OnUnhandled);

   MyForm^ form = gcnew MyForm( );
   Application::Run(form);
}
```

## <a name="see-also"></a>请参阅

[异常处理](../extensions/exception-handling-cpp-component-extensions.md)
