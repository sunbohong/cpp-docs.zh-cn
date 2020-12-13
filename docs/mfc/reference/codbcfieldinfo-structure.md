---
description: 了解详细信息： CODBCFieldInfo 结构
title: CODBCFieldInfo 结构
ms.date: 11/04/2016
f1_keywords:
- CODBCFieldInfo
helpviewer_keywords:
- ODBC [MFC], data source information
- CODBCFieldInfo structure [MFC]
ms.assetid: 92598b4f-facc-4108-b282-63a179ff79ab
ms.openlocfilehash: 7cd7072719bec46cfbfaeb02c5c86d714c4de13c
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97331414"
---
# <a name="codbcfieldinfo-structure"></a>CODBCFieldInfo 结构

`CODBCFieldInfo`结构包含有关 ODBC 数据源中的字段的信息。

## <a name="syntax"></a>语法

```
struct CODBCFieldInfo
{
    CString m_strName;
    SWORD m_nSQLType;
    UDWORD m_nPrecision;
    SWORD m_nScale;
    SWORD m_nNullability;
};
```

#### <a name="parameters"></a>parameters

*m_strName*<br/>
字段的名称。

*m_nSQLType*<br/>
字段的 SQL 数据类型。 这可以是 ODBC SQL 数据类型，也可以是特定于驱动程序的 SQL 数据类型。 有关有效 ODBC SQL 数据类型的列表，请参阅 Windows SDK 中的 "SQL 数据类型"。 有关特定于驱动程序的 SQL 数据类型的信息，请参阅驱动程序的文档。

*m_nPrecision*<br/>
字段的最大精度。 有关详细信息，请参阅 Windows SDK 中的 "精度、小数位数、长度和显示大小"。

*m_nScale*<br/>
字段的小数位数。 有关详细信息，请参阅 Windows SDK 中的 "精度、小数位数、长度和显示大小"。

*m_nNullability*<br/>
字段是否接受 Null 值。 这可以是以下两个值之一： SQL_NULLABLE 如果字段接受 Null 值，则为; 如果字段不接受 Null 值，则为 SQL_NO_NULLS。

## <a name="remarks"></a>备注

若要检索此信息，请调用 [CRecordset：： GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)。

## <a name="requirements"></a>要求

**标头：** afxdb

## <a name="see-also"></a>请参阅

[结构、样式、回调和消息映射](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CRecordset：： GetODBCFieldInfo](../../mfc/reference/crecordset-class.md#getodbcfieldinfo)<br/>
[CRecordset：： GetFieldValue](../../mfc/reference/crecordset-class.md#getfieldvalue)
