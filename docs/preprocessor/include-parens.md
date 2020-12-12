---
description: '了解详细信息：包括 ( # A1 import 特性'
title: '包括 ( # A1 import 特性'
ms.date: 08/29/2019
f1_keywords:
- include()
helpviewer_keywords:
- include() attribute
ms.assetid: 86c9dcb2-d9e0-4fd5-97d7-0bb3e23d6ecc
ms.openlocfilehash: e1164526f95bf1b916cd684a892fbef35027f984
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97236472"
---
# <a name="include-import-attribute"></a>包括 ( # A1 import 特性

**C++ 专用**

禁用自动排除。

## <a name="syntax"></a>语法

> **#import** *类型库***包括 ( "**_Name1_**"** [__，"__*Name2*__"__ ...]__)__

### <a name="parameters"></a>parameters

*Name1*\
要强制包含的第一项。

*Name2*\
要强行包含的第二项（如果需要）。

## <a name="remarks"></a>备注

类型库可能包含在系统标头文件或其他类型库中定义的项的定义。 `#import` 尝试通过自动排除此类项来避免多个定义错误。 如果不应自动排除某些项，则可能会看到 [编译器警告 (级别 3) C4192](../error-messages/compiler-warnings/compiler-warning-level-3-c4192.md)。 您可以使用此属性来禁用自动排除。 此特性可以采用任意数量的参数，每个参数对应于要包含的类型库项的每个名称。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
