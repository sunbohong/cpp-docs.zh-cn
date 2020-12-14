---
description: 了解详细信息： &lt; 注释&gt;
title: '&lt; (c + + 文档注释> 说明) '
ms.date: 11/04/2016
f1_keywords:
- remarks
- <remarks>
helpviewer_keywords:
- <remarks> C++ XML tag
- remarks C++ XML tag
ms.assetid: c820083b-3192-40ab-9ec8-1472c55b4247
ms.openlocfilehash: 0c919ba3101282fd755450489eacc6c0800fb437
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97225214"
---
# <a name="ltremarksgt"></a>&lt;remarks&gt;

\<remarks> 标记用于添加有关某个类型的信息，从而补充由 [\<summary>](summary-visual-cpp.md) 指定的信息。 此信息显示在[对象浏览器](/visualstudio/ide/viewing-the-structure-of-code)和代码注释 Web 报表中。

## <a name="syntax"></a>语法

```
<remarks>description</remarks>
```

#### <a name="parameters"></a>parameters

description<br/>
对成员的说明。

## <a name="remarks"></a>备注

使用 [/doc](doc-process-documentation-comments-c-cpp.md) 进行编译，将文档注释处理到文件中。

## <a name="example"></a>示例

```cpp
// xml_remarks_tag.cpp
// compile with: /LD /clr /doc
// post-build command: xdcmake xml_remarks_tag.dll

using namespace System;

/// <summary>
/// You may have some primary information about this class.
/// </summary>
/// <remarks>
/// You may have some additional information about this class.
/// </remarks>
public ref class MyClass {};
```

## <a name="see-also"></a>请参阅

[XML 文档](xml-documentation-visual-cpp.md)
