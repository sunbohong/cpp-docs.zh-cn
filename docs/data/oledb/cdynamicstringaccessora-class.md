---
description: 了解详细信息： CDynamicStringAccessorA 类
title: CDynamicStringAccessorA 类
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorA
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
ms.openlocfilehash: 45a4d10c8a50c4009151fa90e51172405047a21a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170719"
---
# <a name="cdynamicstringaccessora-class"></a>CDynamicStringAccessorA 类

当您不知道数据库架构 (基础结构) 时，允许访问数据源。

## <a name="syntax"></a>语法

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;
```

## <a name="remarks"></a>备注

它们都请求提供程序将从数据存储区访问的所有数据作为字符串数据获取，但会 `CDynamicStringAccessor` 请求 ANSI 字符串数据。

`CDynamicStringAccessorA` 继承 `GetString` 和 `SetString` from `CDynamicStringAccessor` 。 在对象中使用这些方法时 `CDynamicStringAccessorA` ， `BaseType` 为 **CHAR**。

## <a name="requirements"></a>要求

**标头**： atldbcli。h

## <a name="see-also"></a>请参阅

[OLE DB 使用者模板](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 使用者模板参考](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor 类](../../data/oledb/caccessor-class.md)<br/>
[CDynamicParameterAccessor 类](../../data/oledb/cdynamicparameteraccessor-class.md)<br/>
[CManualAccessor 类](../../data/oledb/cmanualaccessor-class.md)<br/>
[CDynamicAccessor 类](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicStringAccessor 类](../../data/oledb/cdynamicstringaccessor-class.md)<br/>
