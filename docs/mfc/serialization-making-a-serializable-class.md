---
description: 了解详细信息：序列化：生成可序列化的类
title: 序列化：定义可序列化的类
ms.date: 11/04/2016
helpviewer_keywords:
- serializable class [MFC]
- DECLARE_SERIAL macro [MFC]
- default constructor [MFC]
- VERSIONABLE_SCHEMA macro [MFC]
- classes [MFC], derived
- IMPLEMENT_SERIAL macro [MFC]
- no-arguments constructor [MFC]
- Serialize method, overriding
- defaults [MFC], constructor
- CObject class [MFC], deriving serializable classes
- constructors [MFC], defining with no arguments
- serialization [MFC], serializable classes
- no default constructor
ms.assetid: 59a14d32-1cc8-4275-9829-99639beee27c
ms.openlocfilehash: 21c45887199768094953066818acfe1b87d8d45d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97217531"
---
# <a name="serialization-making-a-serializable-class"></a>序列化：定义可序列化的类

使类可序列化所需的五个主要步骤。 下面列出了这些步骤，后续章节中对它们进行了说明：

1. [从 CObject](#_core_deriving_your_class_from_cobject) (或从) 派生的某个类派生类 `CObject` 。

1. [重写序列化成员函数](#_core_overriding_the_serialize_member_function)。

1. 在类声明中[使用 DECLARE_SERIAL 宏](#_core_using_the_declare_serial_macro)。

1. [定义不带参数的构造函数](#_core_defining_a_constructor_with_no_arguments)。

1. [在类的实现文件中使用 IMPLEMENT_SERIAL 宏](#_core_using_the_implement_serial_macro_in_the_implementation_file) 。

如果直接调用 `Serialize` 而不是通过 [CArchive](../mfc/reference/carchive-class.md)的 >> 和 << 运算符，则不需要执行最后三个步骤来进行序列化。

## <a name="deriving-your-class-from-cobject"></a><a name="_core_deriving_your_class_from_cobject"></a> 从 CObject 派生类

基本序列化协议和功能在 `CObject` 类中定义。 通过从 `CObject` 或派生自 `CObject` 的类派生您的类（如类 `CPerson` 的以下声明中所示），您将能够访问 `CObject` 的序列化协议和功能。

## <a name="overriding-the-serialize-member-function"></a><a name="_core_overriding_the_serialize_member_function"></a> 重写序列化成员函数

在 `Serialize` 类中定义的 `CObject` 成员函数负责实际上序列化捕获对象的当前状态所需的数据。 `Serialize` 函数具有一个 `CArchive` 参数，供它读取和写入对象数据。 [CArchive](../mfc/reference/carchive-class.md)对象具有成员函数， `IsStoring` 用于指示 `Serialize` 是存储 (写入数据) 还是加载 (读取数据) 。 使用的结果 `IsStoring` 作为指南，你可以使用插入运算符将对象的数据插入到 `CArchive` 对象中， (**<\<**) or extract data with the extraction operator (**>>**) 。

请考虑从派生的类，它 `CObject` 具有两个新的成员变量，类型为 `CString` 和 **WORD**。 以下类声明片段显示了新成员变量以及重写的 `Serialize` 成员函数的声明：

[!code-cpp[NVC_MFCSerialization#1](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_1.h)]

#### <a name="to-override-the-serialize-member-function"></a>重写 Serialize 成员函数

1. 调用基类版本的 `Serialize` 以确保对象的继承部分已序列化。

1. 插入或提取特定于您的类的成员变量。

   插入和提取运算符与存档类交互以读取和写入数据。 以下代码示例演示如何为前面声明的 `Serialize` 类实现 `CPerson`：

   [!code-cpp[NVC_MFCSerialization#2](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_2.cpp)]

你还可以使用 [CArchive：： Read](../mfc/reference/carchive-class.md#read) 和 [Carchive：： Write](../mfc/reference/carchive-class.md#write) 成员函数来读取和写入大量非类型化数据。

## <a name="using-the-declare_serial-macro"></a><a name="_core_using_the_declare_serial_macro"></a> 使用 DECLARE_SERIAL 宏

要支持序列化的类的声明中需要 DECLARE_SERIAL 宏，如下所示：

[!code-cpp[NVC_MFCSerialization#3](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_3.h)]

## <a name="defining-a-constructor-with-no-arguments"></a><a name="_core_defining_a_constructor_with_no_arguments"></a> 定义不带参数的构造函数

当 MFC 因为对象被反序列化（从磁盘加载）而重新创建对象时，MFC 需要一个默认构造函数。 反序列化过程将使用重新创建对象所需的值填写所有成员变量。

此构造函数可声明为公共、受保护或私有。 如果您使它成为受保护或私有构造函数，您就帮助确保了它只会由序列化函数使用。 构造函数必须将对象设为允许它在必要时删除的状态。

> [!NOTE]
> 如果忘记在使用 DECLARE_SERIAL 和 IMPLEMENT_SERIAL 宏的类中定义没有自变量的构造函数，则将在使用 IMPLEMENT_SERIAL 宏的行上收到 "没有默认构造函数可用" 编译器警告。

## <a name="using-the-implement_serial-macro-in-the-implementation-file"></a><a name="_core_using_the_implement_serial_macro_in_the_implementation_file"></a> 在实现文件中使用 IMPLEMENT_SERIAL 宏

IMPLEMENT_SERIAL 宏用于定义从派生可序列化类时所需的各种功能 `CObject` 。 您为您的类在实现文件 (.cpp) 中使用此宏。 此宏的前两个参数是类的名称和其直接基类的名称。

该宏的第三个参数是一个架构数字。 架构数字本质上是类的对象的版本号。 请对架构数字使用大于或等于 0 的整数值。 （不要将此架构数字与数据库术语混淆。）

MFC 序列化代码在将对象读入内存时检查架构数字。 如果磁盘上的对象的架构数字与内存中的架构数字不匹配，库将引发 `CArchiveException`，这会阻止您的程序读取不正确的版本的对象。

如果希望 `Serialize` 成员函数能够读取多个版本（即，用不同版本的应用程序编写的文件），则可以使用 *VERSIONABLE_SCHEMA* 作为 IMPLEMENT_SERIAL 宏的参数的值。 有关用法信息和示例，请参阅类 `GetObjectSchema` 的 `CArchive` 成员函数。

下面的示例演示如何使用派生自的类的 IMPLEMENT_SERIAL `CPerson` `CObject` ：

[!code-cpp[NVC_MFCSerialization#4](../mfc/codesnippet/cpp/serialization-making-a-serializable-class_4.cpp)]

如果有可序列化的类，则可以序列化类的对象，如 [序列化：](../mfc/serialization-serializing-an-object.md)序列化对象一文中所述。

## <a name="see-also"></a>请参阅

[序列化](../mfc/serialization-in-mfc.md)
