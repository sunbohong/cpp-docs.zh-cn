---
description: 了解详细信息： &lt; 摘要&gt;
title: '&lt; (c + + 文档注释> 摘要) '
ms.date: 11/04/2016
f1_keywords:
- <summary>
helpviewer_keywords:
- <summary> C++ XML tag
- summary C++ XML tag
ms.assetid: cdeeefbb-1339-45d6-9002-10042a9a2726
ms.openlocfilehash: 3003a3226a67d864be1a07a47151e7003c5514a4
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126333"
---
# <a name="ltsummarygt"></a>&lt;summary&gt;

\<summary> 标记应当用于描述类型或类型成员。 使用 [\<remarks>](remarks-visual-cpp.md) 可针对某个类型说明添加补充信息。

## <a name="syntax"></a>语法

```
<summary>description</summary>
```

#### <a name="parameters"></a>参数

description<br/>
对象的摘要。

## <a name="remarks"></a>备注

标记的文本 \<summary> 是有关 IntelliSense 中类型的唯一信息源，并且还会显示在 " [对象浏览器](/visualstudio/ide/viewing-the-structure-of-code) " 和 "代码注释 Web" 报表中。

使用 [/doc](doc-process-documentation-comments-c-cpp.md) 进行编译，将文档注释处理到文件中。

## <a name="example"></a>示例

```cpp
// xml_summary_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_summary_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary>MyMethod is a method in the MyClass class.
   /// <para>Here's how you could make a second paragraph in a description. <see cref="System::Console::WriteLine"/> for information about output statements.</para>
   /// <seealso cref="MyClass::MyMethod2"/>
   /// </summary>
   void MyMethod(int Int1) {}

   /// text
   void MyMethod2() {}
};
```

## <a name="see-also"></a>另请参阅

[XML 文档](xml-documentation-visual-cpp.md)
