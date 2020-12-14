---
description: 了解详细信息： CDaoWorkspaceInfo 结构
title: CDaoWorkspaceInfo 结构
ms.date: 11/04/2016
f1_keywords:
- CDaoWorkspaceInfo
helpviewer_keywords:
- CDaoWorkspaceInfo structure [MFC]
- DAO (Data Access Objects), Workspaces collection
ms.assetid: a1f4b25e-f9c6-4196-b075-d1df99c54124
ms.openlocfilehash: b89e8787c2103244535e9458650f1f104478b748
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97222198"
---
# <a name="cdaoworkspaceinfo-structure"></a>CDaoWorkspaceInfo 结构

`CDaoWorkspaceInfo`结构包含有关为数据访问对象定义的工作区的信息 (DAO) 数据库访问。

## <a name="syntax"></a>语法

```
struct CDaoWorkspaceInfo
{
    CString m_strName;           // Primary
    CString m_strUserName;       // Secondary
    BOOL m_bIsolateODBCTrans;    // All
};
```

#### <a name="parameters"></a>parameters

*m_strName*<br/>
对工作区对象进行唯一命名。 若要直接检索此属性的值，请调用 querydef 对象的 [GetName](../../mfc/reference/cdaoquerydef-class.md#getname) 成员函数。 有关详细信息，请参阅 DAO 帮助中的主题 "名称属性"。

*m_strUserName*<br/>
一个值，该值表示工作区对象的所有者。 有关相关信息，请参阅 DAO 帮助中的主题 "UserName 属性"。

*m_bIsolateODBCTrans*<br/>
一个值，该值指示是否隔离涉及同一 ODBC 数据库的多个事务。 有关详细信息，请参阅 [CDaoWorkspace：： SetIsolateODBCTrans](../../mfc/reference/cdaoworkspace-class.md#setisolateodbctrans)。 有关相关信息，请参阅 DAO 帮助中的主题 "IsolateODBCTrans 属性"。

## <a name="remarks"></a>备注

工作区是 [CDaoWorkspace](../../mfc/reference/cdaoworkspace-class.md)类的对象。 对主要、次要和全部的引用指示类中的 [GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo) 成员函数返回信息的方式 `CDaoWorkspace` 。

[CDaoWorkspace：： GetWorkspaceInfo](../../mfc/reference/cdaoworkspace-class.md#getworkspaceinfo)成员函数检索的信息存储在 `CDaoWorkspaceInfo` 结构中。 `CDaoWorkspaceInfo` 还定义了 `Dump` 调试版本中的成员函数。 可以使用 `Dump` 转储对象的内容 `CDaoWorkspaceInfo` 。

## <a name="requirements"></a>要求

**标头：** afxdao

## <a name="see-also"></a>请参阅

[结构、样式、回调和消息映射](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)<br/>
[CDaoWorkspace 类](../../mfc/reference/cdaoworkspace-class.md)
