---
description: 了解有关以下方面的详细信息： &lt; 权限&gt;
title: '&lt; (c + + 文档注释> 权限) '
ms.date: 11/04/2016
f1_keywords:
- permission
- <permission>
helpviewer_keywords:
- <permission> C++ XML tag
- permission C++ XML tag
ms.assetid: 537ee2bc-95bd-48e4-9ce6-3420c3da87f4
ms.openlocfilehash: cd815b5df831632afd399e752e4525082f20b063
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97226020"
---
# <a name="ltpermissiongt"></a>permission&lt;&gt;

使用 \<permission> 标记可以记录成员访问权限。 借助 <xref:System.Security.PermissionSet>，可以指定对成员的访问权限。

## <a name="syntax"></a>语法

```
<permission cref="member">description</permission>
```

#### <a name="parameters"></a>parameters

*职员*<br/>
对可从当前编译环境调用的成员或字段的引用。 编译器检查是否存在给定的代码元素，并将 `member` 转换为输出 XML 中规范的元素名称。  将名称括在单引号或双引号中。

如果编译器没有找到 `member`，它会发出警告。

有关如何创建对泛型类型的 cref 引用的信息，请参阅 [\<see>](see-visual-cpp.md) 。

description<br/>
对成员访问权限的说明。

## <a name="remarks"></a>备注

使用 [/doc](doc-process-documentation-comments-c-cpp.md) 进行编译，将文档注释处理到文件中。

MSVC 编译器将尝试通过文档注释来解析一次中的 cref 引用。  因此，如果使用 C++ 查找规则，编译器找不到符号，引用将被标记为未解析。 [\<seealso>](seealso-visual-cpp.md)有关详细信息，请参阅。

## <a name="example"></a>示例

```cpp
// xml_permission_tag.cpp
// compile with: /clr /doc /LD
// post-build command: xdcmake xml_permission_tag.dll
using namespace System;
/// Text for class TestClass.
public ref class TestClass {
   /// <permission cref="System::Security::PermissionSet">Everyone can access this method.</permission>
   void Test() {}
};
```

## <a name="see-also"></a>请参阅

[XML 文档](xml-documentation-visual-cpp.md)
