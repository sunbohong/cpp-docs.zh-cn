---
title: 对象映射宏
ms.date: 11/04/2016
f1_keywords:
- atlcom/ATL::DECLARE_OBJECT_DESCRIPTION
- atlcom/ATL::OBJECT_ENTRY_AUTO
- atlcom/ATL::OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO
ms.assetid: 680087f4-9894-41dd-a79c-6f337e1f13c1
ms.openlocfilehash: 2eb24914561a958a6d6d79dab6779e0ba0a70201
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88835280"
---
# <a name="object-map-macros"></a>对象映射宏

这些宏定义对象映射和条目。

|名称|说明|
|-|-|
|[DECLARE_OBJECT_DESCRIPTION](#declare_object_description)|允许指定类对象的文本说明，该说明将被输入到对象映射中。|
|[OBJECT_ENTRY_AUTO](#object_entry_auto)|向对象映射中输入 ATL 对象，更新注册表，并创建对象的实例。|
|[OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO](#object_entry_non_createable_ex_auto)|允许你指定应该注册和初始化对象，但不应可经由 `CoCreateInstance` 在外部创建对象。|

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="declare_object_description"></a><a name="declare_object_description"></a> DECLARE_OBJECT_DESCRIPTION

允许你为类对象指定文本说明。

```
DECLARE_OBJECT_DESCRIPTION( x )
```

### <a name="parameters"></a>参数

*x*<br/>
中类对象的说明。

### <a name="remarks"></a>注解

ATL 通过 [OBJECT_ENTRY_AUTO](#object_entry_auto) 宏将此说明输入到对象映射。

DECLARE_OBJECT_DESCRIPTION 实现一个 `GetObjectDescription` 函数，该函数可用于重写 [CComCoClass：： GetObjectDescription](ccomcoclass-class.md#getobjectdescription) 方法。

`GetObjectDescription`函数由调用 `IComponentRegistrar::GetComponents` 。 `IComponentRegistrar` 是一个自动化接口，可用于注册和取消注册 DLL 中的单个组件。 使用 ATL 项目向导创建组件注册器对象时，向导将自动实现 `IComponentRegistrar` 接口。 `IComponentRegistrar` 通常由 Microsoft 事务服务器使用。

有关 ATL 项目向导的详细信息，请参阅文章 [创建 Atl 项目](../../atl/reference/creating-an-atl-project.md)。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Windowing#123](../../atl/codesnippet/cpp/object-map-macros_1.h)]

## <a name="object_entry_auto"></a><a name="object_entry_auto"></a> OBJECT_ENTRY_AUTO

向对象映射中输入 ATL 对象，更新注册表，并创建对象的实例。

```
OBJECT_ENTRY_AUTO( clsid, class )
```

### <a name="parameters"></a>参数

*clsid*<br/>
中由 c + + 类实现的名为 *class*的 COM 类的 CLSID。

*class*<br/>
中实现 *clsid*所表示的 COM 类的 c + + 类的名称。

### <a name="remarks"></a>注解

对象项宏置于项目中的全局范围内，以提供对类的注册、初始化和创建的支持。

OBJECT_ENTRY_AUTO 将此对象的 creator 类和类工厂创建者类函数的函数指针输入 `CreateInstance` 到自动生成的 ATL 对象映射。 调用 [CAtlComModule：： RegisterServer](catlcommodule-class.md#registerserver) 时，它将更新对象映射中每个对象的系统注册表。

下表介绍了如何从给定作为此宏的第二个参数的类中获取添加到对象映射的信息。

|信息|获取自|
|---------------------|-------------------|
|COM 注册|[注册表宏](../../atl/reference/registry-macros.md)|
|类工厂创建|[类工厂宏](../../atl/reference/aggregation-and-class-factory-macros.md)|
|实例创建|[聚合宏](../../atl/reference/aggregation-and-class-factory-macros.md)|
|组件类别注册|[类别宏](../../atl/reference/category-macros.md)|
|类级别的初始化和清理|[ObjectMain](ccomobjectrootex-class.md#objectmain)|

## <a name="object_entry_non_createable_ex_auto"></a><a name="object_entry_non_createable_ex_auto"></a> OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO

允许你指定应该注册和初始化对象，但不应可经由 `CoCreateInstance` 在外部创建对象。

```
OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO( clsid, class )
```

### <a name="parameters"></a>参数

*clsid*<br/>
中由 c + + 类实现的名为 *class*的 COM 类的 CLSID。

*class*<br/>
中实现 *clsid*所表示的 COM 类的 c + + 类的名称。

### <a name="remarks"></a>注解

对象项宏置于项目中的全局范围内，以提供对类的注册、初始化和创建的支持。

OBJECT_ENTRY_NON_CREATEABLE_EX_AUTO 允许你指定应注册和初始化对象 (请参阅 [OBJECT_ENTRY_AUTO](#object_entry_auto) 了解) 的详细信息，但它不能通过进行创建 `CoCreateInstance` 。

## <a name="see-also"></a>另请参阅

[宏](../../atl/reference/atl-macros.md)
