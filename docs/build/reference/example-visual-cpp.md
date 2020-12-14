---
description: 了解详细信息： &lt; 示例&gt;
title: '&lt;c + + 文档注释> 示例 () '
ms.date: 11/04/2016
f1_keywords:
- <example>
- example
helpviewer_keywords:
- <example> C++ XML tag
- example C++ XML tag
ms.assetid: c821aaa7-7ea7-4bee-9922-6705ad57f877
ms.openlocfilehash: 8ffa51be888fb631db6ec1ecd145177ea346084f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97200827"
---
# <a name="ltexamplegt"></a>&lt;example&gt;

借助 \<example> 标记，可以指定如何使用方法或其他库成员的示例。 通常，这也会涉及到使用 [\<code>](code-visual-cpp.md) 标记。

## <a name="syntax"></a>语法

```
<example>description</example>
```

#### <a name="parameters"></a>parameters

description<br/>
代码示例的说明。

## <a name="remarks"></a>备注

使用 [/doc](doc-process-documentation-comments-c-cpp.md) 进行编译，将文档注释处理到文件中。

## <a name="example"></a>示例

```cpp
// xml_example_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_example_tag.dll

/// Text for class MyClass.
public ref class MyClass {
public:
   /// <summary>
   /// GetZero method
   /// </summary>
   /// <example> This sample shows how to call the GetZero method.
   /// <code>
   /// int main()
   /// {
   ///    return GetZero();
   /// }
   /// </code>
   /// </example>
   static int GetZero() {
      return 0;
   }
};
```

## <a name="see-also"></a>请参阅

[XML 文档](xml-documentation-visual-cpp.md)
