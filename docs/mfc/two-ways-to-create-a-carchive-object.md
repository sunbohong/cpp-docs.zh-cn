---
description: 了解更多相关信息：创建 CArchive 对象的两种方法
title: 创建 CArchive 对象的两种方法
ms.date: 11/04/2016
helpviewer_keywords:
- CArchive class [MFC], closing CArchive objects
- CArchive objects [MFC], closing
- I/O [MFC], creating CArchive objects
- serialization [MFC], CArchive class
- CArchive objects [MFC]
- storage [MFC], CArchive class [MFC]
- data storage [MFC], CArchive class
- CArchive class [MFC], constructor
ms.assetid: aefa28ce-b55c-40dc-9e42-5f038030985d
ms.openlocfilehash: 21a4321eef2d93cf0b37d157f57e12fa1ba940c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97263850"
---
# <a name="two-ways-to-create-a-carchive-object"></a>创建 CArchive 对象的两种方法

可通过两种方法创建 `CArchive` 对象：

- [通过框架隐式创建 CArchive 对象](#_core_implicit_creation_of_a_carchive_object_via_the_framework)

- [显示 CArchive 对象的显式创建](#_core_explicit_creation_of_a_carchive_object)

## <a name="implicit-creation-of-a-carchive-object-via-the-framework"></a><a name="_core_implicit_creation_of_a_carchive_object_via_the_framework"></a> 通过框架隐式创建 CArchive 对象

最常见、最简单的方法是让框架 `CArchive` 代表 "文件" 菜单上的 "保存"、"另存为" 和 "打开" 命令创建一个文档对象。

下面是当应用程序的用户从 "文件" 菜单发出 "另存为" 命令时，框架的作用：

1. 显示 " **另存为** " 对话框，并从用户获取文件名。

1. 以对象的形式打开用户指定的文件 `CFile` 。

1. 创建一个 `CArchive` 指向此对象的对象 `CFile` 。 在创建 `CArchive` 对象时，框架会将模式设置为 "存储" (写入、序列化) ，而不是 "加载" (读取、反序列化) 。

1. 调用 `Serialize` 派生类中定义的函数 `CDocument` ，并向其传递对对象的引用 `CArchive` 。

文档的 `Serialize` 函数会将数据写入 `CArchive` 对象，如稍后所述。 从函数返回后 `Serialize` ，框架会销毁 `CArchive` 对象，然后销毁 `CFile` 对象。

因此，如果您让框架 `CArchive` 为您的文档创建对象，您只需实现在存档中写入和读取数据的文档 `Serialize` 函数。 您还必须为 `Serialize` 任何派生的 `CObject` 对象实现，文档的 `Serialize` 函数反过来直接或间接地进行序列化。

## <a name="explicit-creation-of-a-carchive-object"></a><a name="_core_explicit_creation_of_a_carchive_object"></a> 显示 CArchive 对象的显式创建

除了通过框架序列化文档外，还可以在其他情况下使用 `CArchive` 对象。 例如，你可能想要将数据序列化到剪贴板，并从剪贴板中序列化，由 `CSharedFile` 对象表示。 或者，您可能想要使用用户界面保存与框架提供的文件不同的文件。 在这种情况下，可以显式创建 `CArchive` 对象。 您可以使用以下过程通过与框架相同的方式来执行此操作。

#### <a name="to-explicitly-create-a-carchive-object"></a>显式创建 CArchive 对象

1. 构造一个 `CFile` 对象或从派生的对象 `CFile` 。

1. 将 `CFile` 对象传递到的构造函数 `CArchive` ，如以下示例中所示：

   [!code-cpp[NVC_MFCSerialization#5](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_1.cpp)]

   构造函数的第二个参数 `CArchive` 是一个枚举值，该值指定是否将存档用于在文件中存储数据或从文件中加载数据。 `Serialize`对象的函数通过 `IsStoring` 为 archive 对象调用函数来检查此状态。

完成将数据存储到对象或从对象加载数据后 `CArchive` ，请将其关闭。 尽管 `CArchive` (和 `CFile`) 对象将自动关闭存档 (和文件) ，但最好显式这样做，因为这样可以更轻松地从错误中恢复。 有关错误处理的详细信息，请参阅文章 [异常：捕获和删除异常](../mfc/exceptions-catching-and-deleting-exceptions.md)。

#### <a name="to-close-the-carchive-object"></a>关闭 CArchive 对象

1. 下面的示例演示如何关闭 `CArchive` 对象：

   [!code-cpp[NVC_MFCSerialization#6](../mfc/codesnippet/cpp/two-ways-to-create-a-carchive-object_2.cpp)]

## <a name="see-also"></a>请参阅

[序列化：序列化对象](../mfc/serialization-serializing-an-object.md)
