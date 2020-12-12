---
description: 了解详细信息： CAccessor 类
title: CAccessor 类
ms.date: 11/04/2016
f1_keywords:
- ATL.CAccessor<T>
- ATL::CAccessor
- CAccessor
- ATL::CAccessor<T>
- ATL.CAccessor
helpviewer_keywords:
- CAccessor class
ms.assetid: b2ba959f-a686-46f3-8837-176248aef748
ms.openlocfilehash: 26b03bc3f464ce606194d6835953c39969bde5de
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97319165"
---
# <a name="caccessor-class"></a>CAccessor 类

表示取值函数类型之一。

## <a name="syntax"></a>语法

```cpp
template <class T>
class CAccessor : public CAccessorBase, public T
```

### <a name="parameters"></a>parameters

*T*<br/>
用户记录类。

## <a name="remarks"></a>备注

它在记录静态绑定到数据源时使用。 记录包含缓冲区。 此类对行集支持多个访问器。

当您知道数据库的结构和类型时，请使用此访问器类型。

如果访问器包含指向内存 (（例如 `BSTR` 必须释放的或接口) ）的字段，则在读取下一条记录之前调用成员函数 [CAccessorRowset：： FreeRecordMemory](./caccessorrowset-class.md#freerecordmemory) 。

## <a name="requirements"></a>要求

**标头:** atldbcli.h

## <a name="see-also"></a>请参阅

[OLE DB 使用者模板](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 使用者模板参考](../../data/oledb/ole-db-consumer-templates-reference.md)
