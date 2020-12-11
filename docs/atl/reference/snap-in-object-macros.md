---
description: 了解详细信息： Snap-In 对象宏
title: Snap-In 对象宏
ms.date: 11/04/2016
f1_keywords:
- atlsnap/ATL::BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::BEGIN_SNAPINTOOLBARID_MAP
- atlsnap/ATL::END_EXTENSION_SNAPIN_NODEINFO_MAP
- atlsnap/ATL::END_SNAPINTOOLBARID_MAP
- atlsnap/ATL::EXTENSION_SNAPIN_DATACLASS
- atlsnap/ATL::EXTENSION_SNAPIN_NODEINFO_ENTRY
- atlsnap/ATL::SNAPINMENUID
- atlsnap/ATL::SNAPINTOOLBARID_ENTRY
ms.assetid: 4e9850c0-e395-4929-86c9-584a81828053
ms.openlocfilehash: d775c1d5f66f16fb63b9a7adeda2bc8e74046acf
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157680"
---
# <a name="snap-in-object-macros"></a>Snap-In 对象宏

这些宏为管理单元扩展提供支持。

|名称|描述|
|-|-|
|[BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)|标记 Snap-In 对象的管理单元扩展插件数据类映射的开头。|
|[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)|标记 Snap-In 对象的工具栏图的开头。|
|[END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map)|标记 Snap-In 对象的管理单元扩展插件数据类映射的结尾。|
|[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)|标记 Snap-In 对象的工具栏图的结尾。|
|[EXTENSION_SNAPIN_DATACLASS](#extension_snapin_dataclass)|为管理单元扩展的数据类创建数据成员。|
|[EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry)|向 Snap-In 对象的管理单元扩展数据类映射中输入一个管理单元扩展数据类。|
|[SNAPINMENUID](#snapinmenuid)|声明 Snap-In 对象使用的上下文菜单的 ID。|
|[SNAPINTOOLBARID_ENTRY](#snapintoolbarid_entry)|将工具栏输入到 Snap-In 对象的工具栏图中。|

## <a name="requirements"></a>要求

**标头：** atlsnap

## <a name="begin_extension_snapin_nodeinfo_map"></a><a name="begin_extension_snapin_nodeinfo_map"></a> BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP

标记管理单元扩展插件数据类映射的开头。

```
BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP(classname)
```

### <a name="parameters"></a>parameters

classname<br/>
中管理单元扩展插件数据类的名称。

### <a name="remarks"></a>备注

用 BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP 宏启动管理单元扩展映射，用 [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) 宏添加每个管理单元扩展插件数据类型的条目，然后用 [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) 宏完成映射。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="begin_snapintoolbarid_map"></a><a name="begin_snapintoolbarid_map"></a> BEGIN_SNAPINTOOLBARID_MAP

声明 Snap-In 对象的工具栏 ID 映射的开头。

```
BEGIN_SNAPINTOOLBARID_MAP(_class)
```

### <a name="parameters"></a>parameters

*_class*<br/>
中指定 Snap-In 对象类。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Windowing#106](../../atl/codesnippet/cpp/snap-in-object-macros_2.h)]

## <a name="end_extension_snapin_nodeinfo_map"></a><a name="end_extension_snapin_nodeinfo_map"></a> END_EXTENSION_SNAPIN_NODEINFO_MAP

标记管理单元扩展插件数据类映射的结尾。

```
END_EXTENSION_SNAPIN_NODEINFO_MAP()
```

### <a name="remarks"></a>备注

用 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) 宏启动管理单元扩展映射，用 [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) 宏添加每个扩展插件数据类型的条目，然后用 END_EXTENSION_SNAPIN_NODEINFO_MAP 宏完成映射。

### <a name="example"></a>示例

请参阅 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)的示例。

## <a name="end_snapintoolbarid_map"></a><a name="end_snapintoolbarid_map"></a> END_SNAPINTOOLBARID_MAP

声明 Snap-In 对象的工具栏 ID 映射的结尾。

```
END_SNAPINTOOLBARID_MAP( _class )
```

### <a name="parameters"></a>parameters

*_class*<br/>
中指定 Snap-In 对象类。

### <a name="example"></a>示例

请参阅 [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)的示例。

## <a name="extension_snapin_dataclass"></a><a name="extension_snapin_dataclass"></a> EXTENSION_SNAPIN_DATACLASS

将数据成员添加到 **ISnapInItemImpl** 派生类的管理单元扩展插件数据类中。

```
EXTENSION_SNAPIN_DATACLASS(dataClass )
```

### <a name="parameters"></a>parameters

*Microsoft.visualstudio.ordesigner.dataclass.*<br/>
中管理单元扩展的数据类。

### <a name="remarks"></a>备注

还应将此类输入到管理单元扩展数据类映射。 通过 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) 宏启动管理单元扩展数据类映射，用 [EXTENSION_SNAPIN_NODEINFO_ENTRY](#extension_snapin_nodeinfo_entry) 宏添加每个管理单元扩展插件数据类型的条目，然后用 [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) 宏完成映射。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_Windowing#105](../../atl/codesnippet/cpp/snap-in-object-macros_1.h)]

## <a name="extension_snapin_nodeinfo_entry"></a><a name="extension_snapin_nodeinfo_entry"></a> EXTENSION_SNAPIN_NODEINFO_ENTRY

将管理单元扩展插件数据类添加到管理单元扩展插件数据类映射。

```
EXTENSION_SNAPIN_NODEINFO_ENTRY( dataClass )
```

### <a name="parameters"></a>parameters

*Microsoft.visualstudio.ordesigner.dataclass.*<br/>
中管理单元扩展的数据类。

### <a name="remarks"></a>备注

通过 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map) 宏启动管理单元扩展数据类映射，用 EXTENSION_SNAPIN_NODEINFO_ENTRY 宏添加每个管理单元扩展插件数据类型的条目，然后用 [END_EXTENSION_SNAPIN_NODEINFO_MAP](#end_extension_snapin_nodeinfo_map) 宏完成映射。

### <a name="example"></a>示例

请参阅 [BEGIN_EXTENSION_SNAPIN_NODEINFO_MAP](#begin_extension_snapin_nodeinfo_map)的示例。

## <a name="snapinmenuid"></a><a name="snapinmenuid"></a> SNAPINMENUID

使用此宏声明 Snap-In 对象的上下文菜单资源。

```
SNAPINMENUID( id )
```

### <a name="parameters"></a>parameters

*id*<br/>
中标识 Snap-In 对象的上下文菜单。

## <a name="snapintoolbarid_entry"></a><a name="snapintoolbarid_entry"></a> SNAPINTOOLBARID_ENTRY

使用此宏将工具栏 ID 输入到 Snap-In 对象的工具栏 ID 地图中。

```
SNAPINTOOLBARID_ENTRY( id )
```

### <a name="parameters"></a>parameters

*id*<br/>
中标识工具栏控件。

### <a name="remarks"></a>备注

[BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)宏标记工具栏 ID 映射的开头;[END_SNAPINTOOLBARID_MAP](#end_snapintoolbarid_map)宏标记结尾。

### <a name="example"></a>示例

请参阅 [BEGIN_SNAPINTOOLBARID_MAP](#begin_snapintoolbarid_map)的示例。

## <a name="see-also"></a>请参阅

[宏](../../atl/reference/atl-macros.md)
