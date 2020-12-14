---
description: '了解有关以下内容的详细信息：文件处理和 i/o (c + +/CLI) '
title: 文件处理和 I-O (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- .NET Framework [C++], file handling
- files [C++], .NET Framework and
- I/O [C++], .NET Framework applications
- .NET Framework [C++], I/O
- files [C++], listing files
- directories [C++], listing files
- monitoring file system events
- FileSystemWatcher class, examples
- examples [C++], monitoring file system changes
- events [C++], monitoring
- file system events [C++]
- files [C++], binary
- binary files, reading in C++
- reading text files
- text files, reading
- files [C++], retrieving information about
- FileInfo class
- binary files, writing in C++
- files [C++], binary
- files [C++], text
- text files, writing in C++
ms.assetid: 3296fd59-a83a-40d4-bd4a-6096cc13101b
ms.openlocfilehash: 30bcec27cf3bc625554ad55bd7657c156e5409d0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97252163"
---
# <a name="file-handling-and-io-ccli"></a>文件处理和 I/O (C++/CLI)

演示使用 .NET Framework 的各种文件操作。

以下主题演示如何使用命名空间中定义的类 <xref:System.IO> 来执行各种文件操作。

## <a name="enumerate-files-in-a-directory"></a><a name="enumerate"></a> 枚举目录中的文件

下面的代码示例演示如何检索目录中文件的列表。 此外，还会枚举子目录。 下面的代码示例使用 <xref:System.IO.Directory.GetFiles%2A> <xref:System.IO.Directory.GetFiles%2A> 和 <xref:System.IO.Directory.GetDirectories%2A> 方法来显示 C：\Windows 目录的内容。

### <a name="example"></a>示例

```cpp
// enum_files.cpp
// compile with: /clr
using namespace System;
using namespace System::IO;

int main()
{
   String^ folder = "C:\\";
   array<String^>^ dir = Directory::GetDirectories( folder );
   Console::WriteLine("--== Directories inside '{0}' ==--", folder);
   for (int i=0; i<dir->Length; i++)
      Console::WriteLine(dir[i]);

   array<String^>^ file = Directory::GetFiles( folder );
   Console::WriteLine("--== Files inside '{0}' ==--", folder);
   for (int i=0; i<file->Length; i++)
      Console::WriteLine(file[i]);

   return 0;
}
```

## <a name="monitor-file-system-changes"></a><a name="monitor"></a> 监视文件系统更改

下面的代码示例使用 <xref:System.IO.FileSystemWatcher> 注册与正在创建、更改、删除或重命名的文件对应的事件。 您可以使用 <xref:System.IO.FileSystemWatcher> 类在检测到更改时触发事件，而不是定期轮询目录以对文件进行更改。

### <a name="example"></a>示例

```cpp
// monitor_fs.cpp
// compile with: /clr
#using <system.dll>

using namespace System;
using namespace System::IO;

ref class FSEventHandler
{
public:
    void OnChanged (Object^ source, FileSystemEventArgs^ e)
    {
        Console::WriteLine("File: {0} {1}",
               e->FullPath, e->ChangeType);
    }
    void OnRenamed(Object^ source, RenamedEventArgs^ e)
    {
        Console::WriteLine("File: {0} renamed to {1}",
                e->OldFullPath, e->FullPath);
    }
};

int main()
{
   array<String^>^ args = Environment::GetCommandLineArgs();

   if(args->Length < 2)
   {
      Console::WriteLine("Usage: Watcher.exe <directory>");
      return -1;
   }

   FileSystemWatcher^ fsWatcher = gcnew FileSystemWatcher( );
   fsWatcher->Path = args[1];
   fsWatcher->NotifyFilter = static_cast<NotifyFilters>
              (NotifyFilters::FileName |
               NotifyFilters::Attributes |
               NotifyFilters::LastAccess |
               NotifyFilters::LastWrite |
               NotifyFilters::Security |
               NotifyFilters::Size );

    FSEventHandler^ handler = gcnew FSEventHandler();
    fsWatcher->Changed += gcnew FileSystemEventHandler(
            handler, &FSEventHandler::OnChanged);
    fsWatcher->Created += gcnew FileSystemEventHandler(
            handler, &FSEventHandler::OnChanged);
    fsWatcher->Deleted += gcnew FileSystemEventHandler(
            handler, &FSEventHandler::OnChanged);
    fsWatcher->Renamed += gcnew RenamedEventHandler(
            handler, &FSEventHandler::OnRenamed);

    fsWatcher->EnableRaisingEvents = true;

    Console::WriteLine("Press Enter to quit the sample.");
    Console::ReadLine( );
}
```

## <a name="read-a-binary-file"></a><a name="read_binary"></a> 读取二进制文件

下面的代码示例演示如何使用命名空间中的两个类从文件读取二进制数据 <xref:System.IO?displayProperty=fullName> ： <xref:System.IO.FileStream> 和 <xref:System.IO.BinaryReader> 。 <xref:System.IO.FileStream> 表示实际文件。 <xref:System.IO.BinaryReader> 为允许二进制访问的流提供一个接口。

此代码示例读取一个名为 "data bin" 的文件，并包含二进制格式的整数。 有关此类文件的信息，请参阅 [如何：编写二进制文件 (c + +/cli) ](#write_binary)。

### <a name="example"></a>示例

```cpp
// binary_read.cpp
// compile with: /clr
#using<system.dll>
using namespace System;
using namespace System::IO;

int main()
{
   String^ fileName = "data.bin";
   try
   {
      FileStream^ fs = gcnew FileStream(fileName, FileMode::Open);
      BinaryReader^ br = gcnew BinaryReader(fs);

      Console::WriteLine("contents of {0}:", fileName);
      while (br->BaseStream->Position < br->BaseStream->Length)
         Console::WriteLine(br->ReadInt32().ToString());

      fs->Close( );
   }
   catch (Exception^ e)
   {
      if (dynamic_cast<FileNotFoundException^>(e))
         Console::WriteLine("File '{0}' not found", fileName);
      else
         Console::WriteLine("Exception: ({0})", e);
      return -1;
   }
   return 0;
}
```

## <a name="read-a-text-file"></a><a name="read_text"></a> 读取文本文件

下面的代码示例演示如何使用 <xref:System.IO.StreamReader> 命名空间中定义的类，一次打开并读取一个文本文件 <xref:System.IO?displayProperty=fullName> 。 此类的实例用于打开文本文件，然后 <xref:System.IO.StreamReader.ReadLine%2A?displayProperty=fullName> 使用方法来检索每行。

此代码示例读取名为 textfile.txt 的文件，其中包含文本。 有关此类文件的信息，请参阅 [如何：使用 c + +/cli) 编写文本文件 (](#write_text)。

### <a name="example"></a>示例

```cpp
// text_read.cpp
// compile with: /clr
#using<system.dll>
using namespace System;
using namespace System::IO;

int main()
{
   String^ fileName = "textfile.txt";
   try
   {
      Console::WriteLine("trying to open file {0}...", fileName);
      StreamReader^ din = File::OpenText(fileName);

      String^ str;
      int count = 0;
      while ((str = din->ReadLine()) != nullptr)
      {
         count++;
         Console::WriteLine("line {0}: {1}", count, str );
      }
   }
   catch (Exception^ e)
   {
      if (dynamic_cast<FileNotFoundException^>(e))
         Console::WriteLine("file '{0}' not found", fileName);
      else
         Console::WriteLine("problem reading file '{0}'", fileName);
   }

   return 0;
}
```

## <a name="retrieve-file-information"></a><a name="retrieve"></a> 检索文件信息

下面的代码示例演示 <xref:System.IO.FileInfo> 类。 如果有文件的名称，则可以使用此类来检索有关文件的信息，例如文件大小、目录、全名以及创建日期和上次修改的日期和时间。

此代码检索 Notepad.exe 的文件信息。

### <a name="example"></a>示例

```cpp
// file_info.cpp
// compile with: /clr
using namespace System;
using namespace System::IO;

int main()
{
   array<String^>^ args = Environment::GetCommandLineArgs();
   if (args->Length < 2)
   {
      Console::WriteLine("\nUSAGE : file_info <filename>\n\n");
      return -1;
   }

   FileInfo^ fi = gcnew FileInfo( args[1] );

   Console::WriteLine("file size: {0}", fi->Length );

   Console::Write("File creation date:  ");
   Console::Write(fi->CreationTime.Month.ToString());
   Console::Write(".{0}", fi->CreationTime.Day.ToString());
   Console::WriteLine(".{0}", fi->CreationTime.Year.ToString());

   Console::Write("Last access date:  ");
   Console::Write(fi->LastAccessTime.Month.ToString());
   Console::Write(".{0}", fi->LastAccessTime.Day.ToString());
   Console::WriteLine(".{0}", fi->LastAccessTime.Year.ToString());

   return 0;
}
```

## <a name="write-a-binary-file"></a><a name="write_binary"></a> 写入二进制文件

下面的代码示例演示如何将二进制数据写入文件。 使用命名空间中的两个类 <xref:System.IO> ： <xref:System.IO.FileStream> 和 <xref:System.IO.BinaryWriter> 。 <xref:System.IO.FileStream> 表示实际文件，而 <xref:System.IO.BinaryWriter> 为允许二进制访问的流提供一个接口。

下面的代码示例以二进制格式写入包含整数的文件。 可使用 [如何：读取二进制文件 (c + +/cli) ](#read_binary)中的代码读取此文件。

### <a name="example"></a>示例

```cpp
// binary_write.cpp
// compile with: /clr
#using<system.dll>
using namespace System;
using namespace System::IO;

int main()
{
   array<Int32>^ data = {1, 2, 3, 10000};

   FileStream^ fs = gcnew FileStream("data.bin", FileMode::Create);
   BinaryWriter^ w = gcnew BinaryWriter(fs);

   try
   {
      Console::WriteLine("writing data to file:");
      for (int i=0; i<data->Length; i++)
      {
         Console::WriteLine(data[i]);
         w->Write(data[i]);
      }
   }
   catch (Exception^)
   {
     Console::WriteLine("data could not be written");
     fs->Close();
     return -1;
   }

   fs->Close();
   return 0;
}
```

## <a name="write-a-text-file"></a><a name="write_text"></a> 写入文本文件

下面的代码示例演示如何使用 <xref:System.IO.StreamWriter> 在命名空间中定义的类创建文本文件并向其写入文本 <xref:System.IO> 。 <xref:System.IO.StreamWriter>构造函数采用要创建的文件的名称。 如果该文件存在，除非将 True 传递给第二个 <xref:System.IO.StringWriter> 构造函数参数) ，否则将覆盖 (。

然后，使用和函数对文件进行归档 <xref:System.IO.StreamWriter.Write%2A> <xref:System.IO.TextWriter.WriteLine%2A> 。

### <a name="example"></a>示例

```cpp
// text_write.cpp
// compile with: /clr
using namespace System;
using namespace System::IO;

int main()
{
   String^ fileName = "textfile.txt";

   StreamWriter^ sw = gcnew StreamWriter(fileName);
   sw->WriteLine("A text file is born!");
   sw->Write("You can use WriteLine");
   sw->WriteLine("...or just Write");
   sw->WriteLine("and do {0} output too.", "formatted");
   sw->WriteLine("You can also send non-text objects:");
   sw->WriteLine(DateTime::Now);
   sw->Close();
   Console::WriteLine("a new file ('{0}') has been written", fileName);

   return 0;
}
```

## <a name="see-also"></a>请参阅

[用 c + +/CLI (Visual C++ 的 .NET 编程) ](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)<br/>
[文件和流 I/O](/dotnet/standard/io/index)<br/>
[System.IO 命名空间](/dotnet/api/system.io)
