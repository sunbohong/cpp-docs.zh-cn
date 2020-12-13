---
description: 了解详细信息： CRuntimeClass 结构
title: CRuntimeClass 结构
ms.date: 11/04/2016
f1_keywords:
- CRuntimeClass
helpviewer_keywords:
- CRuntimeClass structure [MFC]
- dynamic class information [MFC]
- runtime [MFC], class information
- run-time class [MFC], CRuntimeClass structure
ms.assetid: de62b6ef-90d4-420f-8c70-f58b36976a2b
ms.openlocfilehash: e02732ec595026f028ad4b8f9bd3d8898a40cbc0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97342912"
---
# <a name="cruntimeclass-structure"></a>CRuntimeClass 结构

派生自的每个类 `CObject` 都与一个 `CRuntimeClass` 结构关联，该结构可用于在运行时获取有关对象或其基类的信息。

## <a name="syntax"></a>语法

```
struct CRuntimeClass
```

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CRuntimeClass：： CreateObject](#createobject)|在运行时创建对象。|
|[CRuntimeClass：： FromName](#fromname)|使用熟悉的类名在运行时创建对象。|
|[CRuntimeClass：： IsDerivedFrom](#isderivedfrom)|确定类是否派生自指定的类。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CRuntimeClass：： m_lpszClassName](#m_lpszclassname)|类的名称。|
|[CRuntimeClass：： m_nObjectSize](#m_nobjectsize)|对象大小（以字节为单位）。|
|[CRuntimeClass：： m_pBaseClass](#m_pbaseclass)|指向 `CRuntimeClass` 基类的结构的指针。|
|[CRuntimeClass：： m_pfnCreateObject](#m_pfncreateobject)|指向动态创建对象的函数的指针。|
|[CRuntimeClass：： m_pfnGetBaseClass](#m_pfngetbaseclass)|返回 `CRuntimeClass` (仅当动态链接) 时才可用的结构。|
|[CRuntimeClass：： m_wSchema](#m_wschema)|类的架构号。|

## <a name="remarks"></a>备注

`CRuntimeClass` 是一个结构，因此不具有基类。

当需要对函数参数进行额外的类型检查时，或者必须基于对象的类编写特殊用途的代码时，能够在运行时确定对象的类很有用。 C++ 语言不直接支持运行时类信息。

`CRuntimeClass` 提供有关相关 c + + 对象的信息，例如指向 `CRuntimeClass` 基类的的指针和相关类的 ASCII 类名。 此结构还实现了各种函数，这些函数可用于动态创建对象、使用熟悉的名称指定对象的类型，以及确定相关类是否派生自特定的类。

有关使用的详细信息 `CRuntimeClass` ，请参阅 [访问 Run-Time 类信息](../../mfc/accessing-run-time-class-information.md)的文章。

## <a name="inheritance-hierarchy"></a>继承层次结构

`CRuntimeClass`

## <a name="requirements"></a>要求

**标头：** afx

## <a name="cruntimeclasscreateobject"></a><a name="createobject"></a> CRuntimeClass：： CreateObject

调用此函数可在运行时动态创建指定的类。

```
CObject* CreateObject();

static CObject* PASCAL CreateObject(LPCSTR lpszClassName);

static CObject* PASCAL CreateObject(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>parameters

*lpszClassName*<br/>
要创建的类的熟悉名称。

### <a name="return-value"></a>返回值

指向新创建的对象的指针; 如果找不到类名或内存不足，无法创建该对象，则为 NULL。

### <a name="remarks"></a>备注

派生自的类 `CObject` 可以支持动态创建，这是在运行时创建指定类的对象的功能。 例如，文档、视图和框架类应支持动态创建。 有关动态创建和成员的详细信息 `CreateObject` ，请参阅 [cobject 类](../../mfc/using-cobject.md) 和 [Cobject 类：指定功能级别](../../mfc/specifying-levels-of-functionality.md)。

### <a name="example"></a>示例

  请参阅 [IsDerivedFrom](#isderivedfrom)的示例。

## <a name="cruntimeclassfromname"></a><a name="fromname"></a> CRuntimeClass：： FromName

调用此函数可检索 `CRuntimeClass` 与熟悉名称关联的结构。

```
static CRuntimeClass* PASCAL FromName(LPCSTR lpszClassName);

static CRuntimeClass* PASCAL FromName(LPCWSTR lpszClassName);
```

### <a name="parameters"></a>parameters

*lpszClassName*<br/>
派生自的类的熟悉名称 `CObject` 。

### <a name="return-value"></a>返回值

指向对象的指针 `CRuntimeClass` ，该对象对应于 *lpszClassName* 中传递的名称。 如果未找到匹配的类名，则函数返回 NULL。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCCObjectSample#17](../../mfc/codesnippet/cpp/cruntimeclass-structure_1.cpp)]

## <a name="cruntimeclassisderivedfrom"></a><a name="isderivedfrom"></a> CRuntimeClass：： IsDerivedFrom

调用此函数可确定调用类是否派生自 *pBaseClass* 参数中指定的类。

```
BOOL IsDerivedFrom(const CRuntimeClass* pBaseClass) const;
```

### <a name="parameters"></a>parameters

*pBaseClass*<br/>
派生自的类的熟悉名称 `CObject` 。

### <a name="return-value"></a>返回值

如果调用的类 `IsDerivedFrom` 派生自其结构被指定为参数的基类，则为 TRUE `CRuntimeClass` ; 否则为 FALSE。

### <a name="remarks"></a>备注

关系由从成员的类 "遍历" 到从派生类的链一直到顶部。 仅当找不到基类的匹配项时，此函数才返回 FALSE。

> [!NOTE]
> 若要使用 `CRuntimeClass` 结构，必须在要为其检索运行时对象信息的类的实现中包含 IMPLEMENT_DYNAMIC、IMPLEMENT_DYNCREATE 或 IMPLEMENT_SERIAL 宏。

有关使用的详细信息 `CRuntimeClass` ，请参阅 [CObject 类：访问 Run-Time 类信息](../../mfc/accessing-run-time-class-information.md)一文。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCCObjectSample#18](../../mfc/codesnippet/cpp/cruntimeclass-structure_2.cpp)]

## <a name="cruntimeclassm_lpszclassname"></a><a name="m_lpszclassname"></a> CRuntimeClass：： m_lpszClassName

一个以 null 结尾的字符串，其中包含 ASCII 类名。

### <a name="remarks"></a>备注

此名称可用于通过成员函数创建类的实例 `FromName` 。

### <a name="example"></a>示例

  请参阅 [IsDerivedFrom](#isderivedfrom)的示例。

## <a name="cruntimeclassm_nobjectsize"></a><a name="m_nobjectsize"></a> CRuntimeClass：： m_nObjectSize

对象的大小（以字节为单位）。

### <a name="remarks"></a>备注

如果对象具有指向已分配内存的数据成员，则不包含该内存的大小。

### <a name="example"></a>示例

  请参阅 [IsDerivedFrom](#isderivedfrom)的示例。

## <a name="cruntimeclassm_pbaseclass"></a><a name="m_pbaseclass"></a> CRuntimeClass：： m_pBaseClass

如果应用程序静态链接到 MFC，则此数据成员包含指向基类的 `CRuntimeClass` 结构的指针。

### <a name="remarks"></a>备注

如果你的应用程序动态链接到 MFC 库，请参阅 [m_pfnGetBaseClass](#m_pfngetbaseclass)。

### <a name="example"></a>示例

  请参阅 [IsDerivedFrom](#isderivedfrom)的示例。

## <a name="cruntimeclassm_pfncreateobject"></a><a name="m_pfncreateobject"></a> CRuntimeClass：： m_pfnCreateObject

一个函数指针，指向用于创建类的对象的默认构造函数。

### <a name="remarks"></a>备注

仅当类支持动态创建时，此指针才有效;否则，该函数返回 NULL。

## <a name="cruntimeclassm_pfngetbaseclass"></a><a name="m_pfngetbaseclass"></a> CRuntimeClass：： m_pfnGetBaseClass

如果你的应用程序使用 MFC 库作为共享 DLL，则此数据成员指向返回 `CRuntimeClass` 基类结构的函数。

### <a name="remarks"></a>备注

如果应用程序静态链接到 MFC 库，请参阅 [m_pBaseClass](#m_pbaseclass)。

### <a name="example"></a>示例

  请参阅 [IsDerivedFrom](#isderivedfrom)的示例。

## <a name="cruntimeclassm_wschema"></a><a name="m_wschema"></a> CRuntimeClass：： m_wSchema

不可序列化类) 的架构编号 (-1。

### <a name="remarks"></a>备注

有关架构号的详细信息，请参阅 [IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial) 宏。

### <a name="example"></a>示例

  请参阅 [IsDerivedFrom](#isderivedfrom)的示例。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CObject：： GetRuntimeClass](../../mfc/reference/cobject-class.md#getruntimeclass)<br/>
[CObject：： IsKindOf](../../mfc/reference/cobject-class.md#iskindof)<br/>
[RUNTIME_CLASS](run-time-object-model-services.md#runtime_class)<br/>
[IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic)<br/>
[IMPLEMENT_DYNCREATE](run-time-object-model-services.md#implement_dyncreate)<br/>
[IMPLEMENT_SERIAL](run-time-object-model-services.md#implement_serial)
