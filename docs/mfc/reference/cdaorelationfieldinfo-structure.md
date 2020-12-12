---
description: 了解详细信息： CDaoRelationFieldInfo 结构
title: CDaoRelationFieldInfo 结构
ms.date: 11/04/2016
f1_keywords:
- CDaoRelationFieldInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationFieldInfo structure [MFC]
ms.assetid: 47cb89ca-dc80-47ce-96fd-cc4b88512558
ms.openlocfilehash: eb470752a9e9da5f610dd59976f2716fa1c4e18a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97248159"
---
# <a name="cdaorelationfieldinfo-structure"></a>CDaoRelationFieldInfo 结构

该 `CDaoRelationFieldInfo` 结构包含有关为 (DAO) 的数据访问对象定义的关系中的字段的信息。

## <a name="syntax"></a>语法

```
struct CDaoRelationFieldInfo
{
    CString m_strName;           // Primary
    CString m_strForeignName;    // Primary
};
```

#### <a name="parameters"></a>parameters

*m_strName*<br/>
关系的主表中的字段的名称。

*m_strForeignName*<br/>
关系外表中的字段的名称。

## <a name="remarks"></a>备注

DAO 关系对象指定主表中的字段以及定义该关系的外表中的字段。 上述结构定义中的 Primary 引用指示了如何在 `m_pFieldInfos` 通过调用类的[GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)成员函数获得的[CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md)对象的成员中返回信息 `CDaoDatabase` 。

关系对象和关系字段对象不由 MFC 类表示。 相反，DAO 对象 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 类的基础 MFC 对象包含关系对象的集合，称为关系集合。 每个关系对象又包含关系字段对象的集合。 每个关系字段对象将主表中的字段与外表中的一个字段相关联。 结合使用关系字段对象，可在每个表中定义一组字段，一起定义关系。 `CDaoDatabase` 允许您 `CDaoRelationInfo` 通过调用成员函数访问与对象的关系对象 `GetRelationInfo` 。 `CDaoRelationInfo`然后，对象具有一个 `m_pFieldInfos` 指向对象数组的数据成员 `CDaoRelationFieldInfo` 。

调用[](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) `CDaoDatabase` 其关系集合存储所需的关系对象的包含对象的 GetRelationInfo 成员函数。 然后访问 `m_pFieldInfos` [CDaoRelationInfo](../../mfc/reference/cdaorelationinfo-structure.md) 对象的成员。 `CDaoRelationFieldInfo` 还定义了 `Dump` 调试版本中的成员函数。 可以使用 `Dump` 转储对象的内容 `CDaoRelationFieldInfo` 。

## <a name="requirements"></a>要求

**标头：** afxdao

## <a name="see-also"></a>请参阅

[结构、样式、回调和消息映射](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoRelationInfo 结构](../../mfc/reference/cdaorelationinfo-structure.md)
