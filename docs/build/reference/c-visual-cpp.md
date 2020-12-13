---
description: 了解详细信息： &lt; c&gt;
title: '&lt;c> (c + + 文档注释) '
ms.date: 11/04/2016
f1_keywords:
- <c>
helpviewer_keywords:
- <c> C++ XML tag
- c C++ XML tag
ms.assetid: 3b23fc0f-e10d-4dd0-b197-48a46cbddd9f
ms.openlocfilehash: 35d06183136a82c602b5e4daa288fb4518962154
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97182614"
---
# <a name="ltcgt"></a>&lt;c&gt;

\<c>标记指示应将说明中的文本标记为代码。 使用 [\<code>](code-visual-cpp.md) 指示作为代码的多行文本。

## <a name="syntax"></a>语法

```
<c>text</c>
```

#### <a name="parameters"></a>parameters

*text*<br/>
要指示为代码的文本。

## <a name="remarks"></a>备注

使用 [/doc](doc-process-documentation-comments-c-cpp.md) 进行编译，将文档注释处理到文件中。

## <a name="example"></a>示例

```cpp
// xml_c_tag.cpp
// compile with: /doc /LD
// post-build command: xdcmake xml_c_tag.xdc

/// Text for class MyClass.
class MyClass {
public:
   int m_i;
   MyClass() : m_i(0) {}

   /// <summary><c>MyMethod</c> is a method in the <c>MyClass</c> class.
   /// </summary>
   int MyMethod(MyClass * a) {
      return a -> m_i;
   }
};
```

## <a name="see-also"></a>请参阅

[XML 文档](xml-documentation-visual-cpp.md)
