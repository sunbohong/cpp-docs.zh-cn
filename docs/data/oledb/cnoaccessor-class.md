---
description: 了解详细信息： CNoAccessor 类
title: CNoAccessor 类
ms.date: 11/04/2016
f1_keywords:
- ATL::CNoAccessor
- CNoAccessor
- ATL.CNoAccessor
helpviewer_keywords:
- CNoAccessor class
ms.assetid: eb669ae5-0a56-49a3-9646-c4ae6239da31
ms.openlocfilehash: 624c72c841280ec56bacf0edd29efeb4b1005988
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170381"
---
# <a name="cnoaccessor-class"></a>CNoAccessor 类

`TAccessor`对于 `CCommand` `CTable` 需要访问器类参数的模板类（如和），可用作模板参数 () 。

## <a name="syntax"></a>语法

```cpp
class CNoAccessor
```

## <a name="remarks"></a>备注

`CNoAccessor`当您不希望类支持参数或输出列时，请使用作为模板参数。

`CNoAccessor` 将实现以下存根方法，其中每个方法都对应于其他访问器类方法：

- `BindColumns` -将列绑定到访问器。

- `BindParameters` -将创建的参数绑定到列。

- `Bind` -创建绑定。

- `Close` -关闭访问器。

- `ReleaseAccessors` -释放由类创建的访问器。

- `FreeRecordMemory` -释放当前记录中需要释放的所有列。

- `GetColumnInfo` -从已打开的行集中获取列信息。

- `GetNumAccessors` -检索类创建的取值函数数目。

- `IsAutoAccessor` -如果移动操作期间自动为访问器检索数据，则返回 true。

- `GetHAccessor` -检索指定访问器的访问器句柄。

- `GetBuffer` -检索指向书签缓冲区的指针。

- `NoBindOnNullRowset` -阻止对空行集进行数据绑定。

## <a name="requirements"></a>要求

**标头:** atldbcli.h

## <a name="see-also"></a>请参阅

[OLE DB 使用者模板](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 使用者模板参考](../../data/oledb/ole-db-consumer-templates-reference.md)
