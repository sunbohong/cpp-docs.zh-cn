---
description: '了解详细信息： c + +/CLI (序列化) '
title: 序列化 (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- serialization [C++]
- SerializableAttribute class, managed applications
- NonSerializedAttribute class, managed applications
- managed code [C++], serializing
- .NET Framework [C++], serialization
- serialization [C++], about serialization
ms.assetid: 869010ca-74e1-4989-b409-4643cdb94084
ms.openlocfilehash: 1524ed5d4a000d2006f6f830b1d82119d170c3b2
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97164596"
---
# <a name="serialization-ccli"></a>序列化 (C++/CLI)

序列化 (将对象或成员的状态存储到托管类的永久性介质) 的过程， (包括和类支持的单个字段或属性) <xref:System.SerializableAttribute> <xref:System.NonSerializedAttribute> 。

## <a name="remarks"></a>备注

将 **SerializableAttribute** 自定义特性应用于托管类，以便序列化整个类，或仅应用于特定字段或属性以序列化托管类的各个部分。 使用 **system.nonserializedattribute** 自定义特性来免除要序列化的托管类的字段或属性。

## <a name="example"></a>示例

### <a name="description"></a>描述

在下面的示例中，类 `MyClass` (，) 的属性 `m_nCount` 被标记为可序列化。 但是，该 `m_nData` 属性不会按非 **系列化** 自定义特性的指示进行序列化：

### <a name="code"></a>代码

```cpp
// serialization_and_mcpp.cpp
// compile with: /LD /clr
using namespace System;

[ Serializable ]
public ref class MyClass {
public:
   int m_nCount;
private:
   [ NonSerialized ]
   int m_nData;
};
```

### <a name="comments"></a>注释

请注意，这两个属性都可以使用其 "short name" (**可序列化** 和非 **系列化**) 来引用。 这将在 [应用属性](/dotnet/standard/attributes/applying-attributes)中进一步说明。

## <a name="see-also"></a>请参阅

[用 c + +/CLI (Visual C++ 的 .NET 编程) ](../dotnet/dotnet-programming-with-cpp-cli-visual-cpp.md)
