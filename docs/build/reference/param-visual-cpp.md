---
description: 了解详细信息： &lt; param&gt;
title: '&lt;参数> (c + + 文档注释) '
ms.date: 11/04/2016
f1_keywords:
- param
- <param>
helpviewer_keywords:
- param C++ XML tag
- <param> C++ XML tag
ms.assetid: 66c1a1c3-4f98-4bcf-8c7d-9a40308982fb
ms.openlocfilehash: 7c3baabc6aef9a4cabdd7c7a9023fb628bd53793
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226137"
---
# <a name="ltparamgt"></a>&lt;param&gt;

在方法声明的注释中，应使用 \<param> 标记来描述方法参数之一。

## <a name="syntax"></a>语法

```
<param name='name'>description</param>
```

#### <a name="parameters"></a>参数

*name*<br/>
方法参数的名称。  将名称括在单引号或双引号中。  如果编译器没有找到 `name`，它会发出警告。

description<br/>
参数的说明。

## <a name="remarks"></a>备注

标记的文本 \<param> 将显示在 IntelliSense、 [对象浏览器](/visualstudio/ide/viewing-the-structure-of-code)和代码注释 Web 报表中。

使用 [/doc](doc-process-documentation-comments-c-cpp.md) 进行编译，将文档注释处理到文件中。

## <a name="example"></a>示例

```cpp
// xml_param_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_param_tag.dll
/// Text for class MyClass.
public ref class MyClass {
   /// <param name="Int1">Used to indicate status.</param>
   void MyMethod(int Int1) {
   }
};
```

## <a name="see-also"></a>请参阅

[XML 文档](xml-documentation-visual-cpp.md)
