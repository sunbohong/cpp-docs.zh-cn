---
description: 了解详细信息： CDaoIndexFieldInfo 结构
title: CDaoIndexFieldInfo 结构
ms.date: 09/17/2019
f1_keywords:
- CDaoIndexFieldInfo
helpviewer_keywords:
- CDaoIndexFieldInfo structure [MFC]
- DAO (Data Access Objects), Index Fields collection
ms.assetid: 097ee8a6-83b1-4db7-8f05-d62a2deefe19
ms.openlocfilehash: fe2d6bef3ce44e7418474b7f2c004942935968c8
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250785"
---
# <a name="cdaoindexfieldinfo-structure"></a>CDaoIndexFieldInfo 结构

该 `CDaoIndexFieldInfo` 结构包含有关为 (DAO) 的数据访问对象定义的索引字段对象的信息。

DAO 受 Office 2013 的支持。 DAO 3.6 是最终版本，被视为已过时。

## <a name="syntax"></a>语法

```
struct CDaoIndexFieldInfo
{
    CString m_strName;          // Primary
    BOOL m_bDescending;         // Primary
};
```

#### <a name="parameters"></a>parameters

*m_strName*<br/>
为索引字段对象唯一命名。 有关详细信息，请参阅 DAO 帮助中的主题 "名称属性"。

*m_bDescending*<br/>
指示索引对象定义的索引顺序。 如果订单为降序，则为 TRUE。

## <a name="remarks"></a>备注

索引对象可以具有多个字段，这些字段指示 tabledef (或基于) 的表编制索引的记录集。 上面引用的主要内容指示如何在 `m_pFieldInfos` 通过调用[](../../mfc/reference/cdaoindexinfo-structure.md) `GetIndexInfo` [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md#getindexinfo)或[CDaoRecordset](../../mfc/reference/cdaorecordset-class.md#getindexinfo)类的成员函数获得的 CDaoIndexInfo 对象的成员中返回信息。

索引对象和索引字段对象不由 MFC 类表示。 相反，DAO 对象类 [CDaoTableDef](../../mfc/reference/cdaotabledef-class.md) 或 [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md) 类的基础 MFC 对象包含索引对象（称为索引集合）的集合。 反过来，每个索引对象都包含一个字段对象的集合。 这些类提供成员函数以访问索引信息的各个项，或者可以 `CDaoIndexInfo` 通过调用 `GetIndexInfo` 包含对象的成员函数，同时通过对象访问所有这些项。 `CDaoIndexInfo`然后，对象具有一个 `m_pFieldInfos` 指向对象数组的数据成员 `CDaoIndexFieldInfo` 。

调用 `GetIndexInfo` 包含 tabledef 或 recordset 对象的成员函数，该对象的索引集合存储有你感兴趣的索引对象。 然后访问 `m_pFieldInfos` [CDaoIndexInfo](../../mfc/reference/cdaoindexinfo-structure.md) 对象的成员。 数组的长度 `m_pFieldInfos` 存储在中 `m_nFields` 。 `CDaoIndexFieldInfo` 还定义了 `Dump` 调试版本中的成员函数。 可以使用 `Dump` 转储对象的内容 `CDaoIndexFieldInfo` 。

## <a name="requirements"></a>要求

**标头：** afxdao

## <a name="see-also"></a>请参阅

[结构、样式、回调和消息映射](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoTableDef：： GetIndexInfo](../../mfc/reference/cdaotabledef-class.md#getindexinfo)<br/>
[CDaoRecordset：： GetIndexInfo](../../mfc/reference/cdaorecordset-class.md#getindexinfo)
