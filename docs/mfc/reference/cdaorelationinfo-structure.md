---
description: 了解详细信息： CDaoRelationInfo 结构
title: CDaoRelationInfo 结构
ms.date: 06/25/2018
f1_keywords:
- CDaoRelationInfo
helpviewer_keywords:
- DAO (Data Access Objects), Relations collection
- CDaoRelationInfo structure [MFC]
ms.assetid: 92dda090-fe72-4090-84ec-429498a48aad
ms.openlocfilehash: efcc880d30dd18108005d9c4f265238b81551532
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222237"
---
# <a name="cdaorelationinfo-structure"></a>CDaoRelationInfo 结构

该 `CDaoRelationInfo` 结构包含有关 [CDaoDatabase](../../mfc/reference/cdaodatabase-class.md) 对象中两个表的字段之间定义的关系的信息。

## <a name="syntax"></a>语法

```cpp
struct CDaoRelationInfo
{
    CDaoRelationInfo();                     // Constructor
    CString m_strName;                      // Primary
    CString m_strTable;                     // Primary
    CString m_strForeignTable;              // Primary
    long m_lAttributes;                     // Secondary
    CDaoRelationFieldInfo* m_pFieldInfos;   // Secondary
    short m_nFields;                        // Secondary
    // Below the // Implementation comment:
    // Destructor, not otherwise documented
};
```

#### <a name="parameters"></a>parameters

*m_strName*<br/>
唯一命名关系对象。 有关详细信息，请参阅 DAO 帮助中的主题 "名称属性"。

*m_strTable*<br/>
命名关系中的主表。

*m_strForeignTable*<br/>
命名关系中的外部表。 外部表是用于包含外键的表。 通常，使用外表建立或强制实施引用完整性。 外表通常位于一对多关系的多个端。 外部表的示例包括包含美国州或加拿大省份或 customer 定单的代码的表。

*m_lAttributes*<br/>
包含关系类型的相关信息。 此成员的值可以是下列任意值：

- `dbRelationUnique` 关系为一对一关系。

- `dbRelationDontEnforce` 不会强制执行关系 (不) 引用完整性。

- `dbRelationInherited` 关系存在于包含两个附加表的非当前数据库中。

- `dbRelationLeft` 关系为左联接。 左外部联接包括两个表的第一个 (左) 中的所有记录，即使在第二个 (右) 表中没有记录的匹配值。

- `dbRelationRight` 关系为右联接。 右外部联接包括两个表的第二 (右) 中的所有记录，即使对于第一个 (左手) 表中的记录没有匹配的值也是如此。

- `dbRelationUpdateCascade` 更新将级联。

- `dbRelationDeleteCascade` 删除将级联。

*m_pFieldInfos*<br/>
指向 [CDaoRelationFieldInfo](../../mfc/reference/cdaorelationfieldinfo-structure.md) 结构的数组的指针。 对于关系中的每个字段，数组包含一个对象。 `m_nFields`数据成员提供数组元素的计数。

*m_nFields*<br/>
`CDaoRelationFieldInfo`数据成员中的对象数 `m_pFieldInfos` 。

## <a name="remarks"></a>备注

上面对主要和辅助副本的引用指示了类中 [GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo) 成员函数返回信息的方式 `CDaoDatabase` 。

关系对象不由 MFC 类表示。 相反，类的 MFC 对象基础上的 DAO 对象 `CDaoDatabase` 维护关系对象的集合： `CDaoDatabase` 提供成员函数以访问关系信息的某些项，或者可以 `CDaoRelationInfo` 通过调用 `GetRelationInfo` 包含数据库对象的成员函数，同时通过对象访问所有这些项。

[CDaoDatabase：： GetRelationInfo](../../mfc/reference/cdaodatabase-class.md#getrelationinfo)成员函数检索的信息存储在 `CDaoRelationInfo` 结构中。 `CDaoRelationInfo` 还定义了 `Dump` 调试版本中的成员函数。 可以使用 `Dump` 转储对象的内容 `CDaoRelationInfo` 。

## <a name="requirements"></a>要求

**标头：** afxdao

## <a name="see-also"></a>请参阅

[CDaoRelationFieldInfo 结构](../../mfc/reference/cdaorelationfieldinfo-structure.md)
