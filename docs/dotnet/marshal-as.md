---
description: 了解详细信息： marshal_as
title: marshal_as
ms.date: 07/12/2019
ms.topic: reference
f1_keywords:
- marshal_as
- msclr.interop.marshal_as
- msclr::interop::marshal_as
helpviewer_keywords:
- marshal_as template [C++]
ms.assetid: 2ed717da-2b11-41e5-981d-47d251771989
ms.openlocfilehash: 0b0738b8778b287e2e97f074345a10841c70a7b1
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97253619"
---
# <a name="marshal_as"></a>marshal_as

此方法在本机和托管环境之间转换数据。

## <a name="syntax"></a>语法

```
To_Type marshal_as<To_Type>(
   From_Type input
);
```

#### <a name="parameters"></a>parameters

*input*<br/>
中要封送到变量的值 `To_Type` 。

## <a name="return-value"></a>返回值

类型为的变量 `To_Type` ，它是的转换后的值 `input` 。

## <a name="remarks"></a>备注

此方法是在本机类型和托管类型之间转换数据的一种简单方法。 若要确定支持的数据类型，请参阅 [c + + 中的封送处理概述](../dotnet/overview-of-marshaling-in-cpp.md)。 某些数据转换需要上下文。 您可以使用 [Marshal_context 类](../dotnet/marshal-context-class.md)来转换这些数据类型。

如果尝试封送一对不受支持的数据类型， `marshal_as` 将在编译时生成错误 [C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md) 。 有关详细信息，请阅读随此错误提供的消息。 `C4996`对于超出不推荐使用的函数，可能会生成错误。 这种情况的一个示例就是尝试封送一对不受支持的数据类型。

封送处理库包含多个标头文件。 任何转换只需要一个文件，但如果您需要进行其他转换，则可以包含其他文件。 若要查看哪些转换与哪些文件相关联，请查看中的表 `Marshaling Overview` 。 无论你要执行何种转换，命名空间要求始终有效。

在 `System::ArgumentNullException(_EXCEPTION_NULLPTR)` 输入参数为 null 时引发。

## <a name="example"></a>示例

此示例将从封送 `const char*` 到 `System::String` 变量类型。

```cpp
// marshal_as_test.cpp
// compile with: /clr
#include <stdlib.h>
#include <string.h>
#include <msclr\marshal.h>

using namespace System;
using namespace msclr::interop;

int main() {
   const char* message = "Test String to Marshal";
   String^ result;
   result = marshal_as<String^>( message );
   return 0;
}
```

## <a name="requirements"></a>要求

**头文件：** \<msclr\marshal.h> 、 \<msclr\marshal_windows.h> 、 \<msclr\marshal_cppstd.h> 或 \<msclr\marshal_atl.h>

**命名空间：** msclr：：互操作

## <a name="see-also"></a>请参阅

[C + + 中的封送处理概述](../dotnet/overview-of-marshaling-in-cpp.md)<br/>
[marshal_context 类](../dotnet/marshal-context-class.md)
