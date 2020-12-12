---
description: 了解详细信息： CDynamicStringAccessorW 类
title: CDynamicStringAccessorW 类
ms.date: 11/04/2016
f1_keywords:
- CDynamicStringAccessorW
helpviewer_keywords:
- CDynamicStringAccessorW class
ms.assetid: 9b7fd5cc-3a9b-4b57-b907-f1e35de2c98f
ms.openlocfilehash: 360a9592cdce3a1046eecb360a8691b1d8480caf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170667"
---
# <a name="cdynamicstringaccessorw-class"></a>CDynamicStringAccessorW 类

当您不知道数据库架构 (基础结构) 时，允许访问数据源。

## <a name="syntax"></a>语法

```cpp
typedef CDynamicStringAccessorT<WCHAR, DBTYPE_WSTR> CDynamicStringAccessorW;
```

## <a name="remarks"></a>备注

它们都请求提供程序将从数据存储区访问的所有数据作为字符串数据获取，但会 `CDynamicStringAccessor` 请求 Unicode 字符串数据。

`CDynamicStringAccessorW` 继承 `GetString` 和 `SetString` from `CDynamicStringAccessor` 。 在对象中使用这些方法时 `CDynamicStringAccessorW` ， `BaseType` 为 **WCHAR**。

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
