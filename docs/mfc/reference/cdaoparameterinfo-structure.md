---
description: 了解详细信息： CDaoParameterInfo 结构
title: CDaoParameterInfo 结构
ms.date: 09/17/2019
f1_keywords:
- CDaoParameterInfo
helpviewer_keywords:
- CDaoParameterInfo structure [MFC]
- DAO (Data Access Objects), Parameters collection
ms.assetid: 45fd53cd-cb84-4e12-b48d-7f2979f898ad
ms.openlocfilehash: b4cd1916bb30c3b646e9b0892e2bdcdf5ade30b4
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97250709"
---
# <a name="cdaoparameterinfo-structure"></a>CDaoParameterInfo 结构

该 `CDaoParameterInfo` 结构包含有关为 (DAO) 的数据访问对象定义的参数对象的信息。 DAO 3.6 是最终版本，被视为已过时。

## <a name="syntax"></a>语法

```
struct CDaoParameterInfo
{
    CString m_strName;       // Primary
    short m_nType;           // Primary
    ColeVariant m_varValue;  // Secondary
};
```

#### <a name="parameters"></a>parameters

*m_strName*<br/>
对参数对象进行唯一命名。 有关详细信息，请参阅 DAO 帮助中的主题 "名称属性"。

*m_nType*<br/>
指示参数对象的数据类型的值。 有关可能值的列表，请参阅 [CDaoFieldInfo](../../mfc/reference/cdaofieldinfo-structure.md)结构的 *m_nType* 成员。 有关详细信息，请参阅 DAO 帮助中的 "类型属性" 主题。

*m_varValue*<br/>
参数的值，存储在 [COleVariant](../../mfc/reference/colevariant-class.md) 对象中。

## <a name="remarks"></a>备注

上面对主要和辅助副本的引用指示了类中 [GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo) 成员函数返回信息的方式 `CDaoQueryDef` 。

MFC 不会将 DAO 参数对象封装在类中。 DAO querydef 对象基础 MFC `CDaoQueryDef` 对象将参数存储在其参数集合中。 若要访问 [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) 对象中的参数对象，请 `GetParameterInfo` 为参数集合中的特定参数名或索引调用 querydef 对象的成员函数。 可以结合使用 [CDaoQueryDef：： GetParameterCount](../../mfc/reference/cdaoquerydef-class.md#getparametercount) 成员函数和 `GetParameterInfo` 来循环遍历 Parameters 集合。

[CDaoQueryDef：： GetParameterInfo](../../mfc/reference/cdaoquerydef-class.md#getparameterinfo)成员函数检索的信息存储在 `CDaoParameterInfo` 结构中。 调用 `GetParameterInfo` 其参数集合中存储了参数对象的 querydef 对象。

> [!NOTE]
> 如果只想获取或设置参数的值，请使用类的 [GetParamValue](../../mfc/reference/cdaorecordset-class.md#getparamvalue) 和 [SetParamValue](../../mfc/reference/cdaorecordset-class.md#setparamvalue) 成员函数 `CDaoRecordset` 。

`CDaoParameterInfo` 还定义了 `Dump` 调试版本中的成员函数。 可以使用 `Dump` 转储对象的内容 `CDaoParameterInfo` 。

## <a name="requirements"></a>要求

**标头：** afxdao

## <a name="see-also"></a>请参阅

[结构、样式、回调和消息映射](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoQueryDef 类](../../mfc/reference/cdaoquerydef-class.md)
