---
title: '&lt;paramref> (c + + 文档注释) '
description: 了解有关 paramref c + + XML 文档标记的更多信息。
ms.date: 11/04/2016
f1_keywords:
- <paramref>
helpviewer_keywords:
- paramref C++ XML tag
- <paramref> C++ XML tag
ms.assetid: c5730dc2-7159-421f-b2d5-bb971e307122
ms.openlocfilehash: 393703e7816368fb80f71d962dc190a0db1cea03
ms.sourcegitcommit: 118e4ad82c0f1c9ac120f105d84224e5fe4cef28
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "98126151"
---
# <a name="ltparamrefgt"></a>&lt;paramref&gt;

\<paramref>标记提供了一种方法，用于指示某个字是参数。 可处理 .xml 文件，以某种不同的方式设置此参数格式。

## <a name="syntax"></a>语法

```
<paramref name="name"/>
```

#### <a name="parameters"></a>参数

*name*<br/>
要引用的参数的名称。  将名称括在单引号或双引号中。  如果编译器没有找到 `name`，它会发出警告。

## <a name="remarks"></a>备注

使用 [/doc](doc-process-documentation-comments-c-cpp.md) 进行编译，将文档注释处理到文件中。

## <a name="example"></a>示例

```cpp
// xml_paramref_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_paramref_tag.dll
/// Text for class MyClass.
public ref class MyClass {
   /// <summary>MyMethod is a method in the MyClass class.
   /// The <paramref name="Int1"/> parameter takes a number.
   /// </summary>
   void MyMethod(int Int1) {}
};
```

## <a name="see-also"></a>另请参阅

[XML 文档](xml-documentation-visual-cpp.md)
