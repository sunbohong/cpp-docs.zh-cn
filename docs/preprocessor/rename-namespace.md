---
description: 了解详细信息： rename_namespace import 特性
title: rename_namespace 导入属性
ms.date: 08/29/2019
f1_keywords:
- rename_namespace
helpviewer_keywords:
- rename_namespace attribute
ms.assetid: 45006d2b-36cd-4bec-98b9-3b8ec45299e3
ms.openlocfilehash: 402d9c9cd8dee5979dd71e16fec1a606d8b4b996
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97167378"
---
# <a name="rename_namespace-import-attribute"></a>rename_namespace 导入属性

**C++ 专用**

重命名包含类型库内容的命名空间。

## <a name="syntax"></a>语法

> **#import** *类型库* **rename_namespace (** "*NewName*" **)**

### <a name="parameters"></a>parameters

*NewName*\
命名空间的新名称。

## <a name="remarks"></a>备注

**Rename_namespace** 属性采用单个自 *变量，它* 指定命名空间的新名称。

若要删除命名空间，请改用 [no_namespace](../preprocessor/no-namespace.md) 特性。

**结束 C++ 专用**

## <a name="see-also"></a>请参阅

[#import 特性](../preprocessor/hash-import-attributes-cpp.md)\
[#import 指令](../preprocessor/hash-import-directive-cpp.md)
