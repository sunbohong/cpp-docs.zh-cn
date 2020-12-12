---
description: 了解详细信息： CSettingsStoreSP 类
title: CSettingsStoreSP 类
ms.date: 11/04/2016
f1_keywords:
- CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::CSettingsStoreSP
- AFXSETTINGSSTORE/CSettingsStoreSP::Create
- AFXSETTINGSSTORE/CSettingsStoreSP::SetRuntimeClass
helpviewer_keywords:
- CSettingsStoreSP [MFC], CSettingsStoreSP
- CSettingsStoreSP [MFC], Create
- CSettingsStoreSP [MFC], SetRuntimeClass
ms.assetid: bcd37f40-cfd4-4d17-a5ce-3bfabe995dcc
ms.openlocfilehash: 67e9f881fc43722ab568aa7f149fc7a2b44cc764
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97264682"
---
# <a name="csettingsstoresp-class"></a>CSettingsStoreSP 类

`CSettingsStoreSP`类是一个帮助器类，可用于创建[CSettingsStore 类](../../mfc/reference/csettingsstore-class.md)的实例。

## <a name="syntax"></a>语法

```
class CSettingsStoreSP
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CSettingsStoreSP::CSettingsStoreSP](#csettingsstoresp)|构造 `CSettingsStoreSP` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CSettingsStoreSP：： Create](#create)|创建派生自的类的实例 `CSettingsStore` 。|
|[CSettingsStoreSP::SetRuntimeClass](#setruntimeclass)|设置运行时类。 `Create`方法使用运行时类来确定要创建的对象的类。|

### <a name="data-members"></a>数据成员

|名称|描述|
|----------|-----------------|
|`m_dwUserData`|存储在对象中的自定义用户数据 `CSettingsStoreSP` 。 在对象的构造函数中提供此数据 `CSettingsStoreSP` 。|
|`m_pRegistry`|`CSettingsStore`方法创建的派生对象 `Create` 。|

## <a name="remarks"></a>备注

您可以使用 `CSettingsStoreSP` 类将所有 MFC 注册表操作重定向到其他位置，如 XML 文件或数据库。 为此，请执行以下步骤：

1. 创建类 (例如 `CMyStore`) 并从中派生 `CSettingsStore` 。

1. 将 [DECLARE_DYNCREATE](run-time-object-model-services.md#declare_dyncreate) 和 [IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate) 宏与自定义类结合使用， `CSettingsStore` 以启用动态创建。

1. 重写虚拟函数并 `Read` `Write` 在自定义类中实现和函数。 实现任何其他功能，将数据读写到所需的位置。

1. 在应用程序中，调用 `CSettingsStoreSP::SetRuntimeClass` 并传入指向从类中获取的 [CRuntimeClass 结构](../../mfc/reference/cruntimeclass-structure.md) 的指针。

只要框架通常会访问注册表，它就会动态地实例化您的自定义类，并使用它来读取或写入数据。

`CSettingsStoreSP::SetRuntimeClass` 使用全局静态变量。 因此，一次只能有一个自定义存储。

## <a name="requirements"></a>要求

**标头：** afxsettingsstore

## <a name="csettingsstorespcreate"></a><a name="create"></a> CSettingsStoreSP：： Create

创建从 [CSettingsStore 类](../../mfc/reference/csettingsstore-class.md)派生的对象的新实例。

```
CSettingsStore& CSettingsStoreSP Create(
    BOOL bAdmin,
    BOOL bReadOnly);
```

### <a name="parameters"></a>parameters

*bAdmin*<br/>
中确定 `CSettingsStore` 对象是否在管理员模式下创建的布尔型参数。

*bReadOnly*<br/>
中确定是否为 `CSettingsStore` 只读访问创建对象的布尔型参数。

### <a name="return-value"></a>返回值

对新创建的对象的引用 `CSettingsStore` 。

### <a name="remarks"></a>备注

可以使用方法 [CSettingsStoreSP：： SetRuntimeClass](#setruntimeclass) 来确定要创建的对象的类型 `CSettingsStoreSP::Create` 。 默认情况下，此方法将创建一个 `CSettingsStore` 对象。

如果 `CSettingsStore` 在管理员模式下创建对象，则将 HKEY_LOCAL_MACHINE 所有注册表访问的默认位置。 否则，将 HKEY_CURRENT_USER 所有注册表访问的默认位置。

如果 *bAdmin* 为 TRUE，则应用程序必须具有管理权限。 否则，在尝试访问注册表时，它会失败。

### <a name="example"></a>示例

下面的示例演示如何使用类的 `Create` 方法 `CSettingsStoreSP` 。

[!code-cpp[NVC_MFC_RibbonApp#33](../../mfc/reference/codesnippet/cpp/csettingsstoresp-class_1.cpp)]

## <a name="csettingsstorespcsettingsstoresp"></a><a name="csettingsstoresp"></a> CSettingsStoreSP::CSettingsStoreSP

构造 [CSettingsStoreSP 类](../../mfc/reference/csettingsstoresp-class.md) 对象。

```
CSettingsStoreSP::CSettingsStoreSP(DWORD dwUserData = 0);
```

### <a name="parameters"></a>parameters

*dwUserData*<br/>
中对象存储的用户定义数据 `CSettingsStoreSP` 。

### <a name="remarks"></a>备注

`CSettingsStoreSP`对象将 *dwUserData* 中的数据存储在受保护的成员变量中 `m_dwUserData` 。

## <a name="csettingsstorespsetruntimeclass"></a><a name="setruntimeclass"></a> CSettingsStoreSP::SetRuntimeClass

设置运行时类。 方法 [CSettingsStoreSP：： Create](#create) 使用运行时类来确定要创建的对象的类型。

```
static BOOL __stdcall CSettingsStoreSP::SetRuntimeClass(CRuntimeClass* pRTI);
```

### <a name="parameters"></a>parameters

*pRTI*<br/>
中一个指针，指向从 [CSettingsStore 类](../../mfc/reference/csettingsstore-class.md)派生的类的运行时类信息。

### <a name="return-value"></a>返回值

如果成功，则为 TRUE;如果由 *pRTI* 标识的类不是从派生的，则为 FALSE `CSettingsStore` 。

### <a name="remarks"></a>备注

可以使用 [CSettingsStoreSP 类](../../mfc/reference/csettingsstoresp-class.md) 从派生类 `CSettingsStore` 。 `SetRuntimeClass`如果要创建派生自的自定义类的对象，请使用方法 `CSettingsStore` 。

## <a name="see-also"></a>请参阅

[类](../../mfc/reference/mfc-classes.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CSettingsStore 类](../../mfc/reference/csettingsstore-class.md)
