---
description: 了解有关 MFC 类对象的类型强制转换的详细信息
title: MFC 类对象的类型强制转换
ms.date: 11/04/2016
helpviewer_keywords:
- macros [MFC], type casting
- pointers [MFC], type casting
- type casts [MFC]
- casting types [MFC]
- macros [MFC], casting pointers
ms.assetid: e138465e-c35f-4e84-b788-bd200ccf2f0e
ms.openlocfilehash: bec49afc0050aa32c6e5436e5efca9b0dab30709
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218664"
---
# <a name="type-casting-of-mfc-class-objects"></a>MFC 类对象的类型强制转换

类型强制转换宏提供了一种方法，可将给定指针强制转换为指向特定类的对象的指针，而不会检查强制转换是否合法。

下表列出了 MFC 类型强制转换宏。

### <a name="macros-that-cast-pointers-to-mfc-class-objects"></a>强制转换到 MFC 类对象的指针的宏

|名称|描述|
|-|-|
|[DYNAMIC_DOWNCAST](#dynamic_downcast)|在检查转换是否合法时，将指针转换为指向类对象的指针。|
|[STATIC_DOWNCAST](#static_downcast)|将指向对象的指针转换为相关类型的指针。 在调试版本中，如果对象不是目标类型的 "类型"，则会导致断言。|

## <a name="dynamic_downcast"></a><a name="dynamic_downcast"></a> DYNAMIC_DOWNCAST

提供将指针转换为指向类对象的指针的便捷方法，同时检查强制转换是否合法。

```
DYNAMIC_DOWNCAST(class, pointer)
```

### <a name="parameters"></a>parameters

*class*<br/>
类的名称。

*变为*<br/>
要强制转换为指向类型 *类* 的对象的指针的指针。

### <a name="remarks"></a>备注

该宏会将 *指针* 参数强制转换为指向 *类* 参数类型的对象的指针。

如果指针引用的对象为标识类的 "类型"，则宏将返回相应的指针。 如果不是合法强制转换，则宏将返回 NULL。

## <a name="static_downcast"></a><a name="static_downcast"></a> STATIC_DOWNCAST

将 *pobject* 转换为指向 *class_name* 对象的指针。

```
STATIC_DOWNCAST(class_name, pobject)
```

### <a name="parameters"></a>parameters

*class_name*<br/>
要强制转换为的类的名称。

*pobject*<br/>
要强制转换为指向 *class_name* 对象的指针的指针。

### <a name="remarks"></a>备注

*pobject* 必须为 NULL，或指向直接从 *class_name* 派生的类的对象。 在定义了 _DEBUG 预处理器符号的应用程序的内部版本中，如果 *pobject* 不为 NULL，则该宏将断言; 或者，如果该对象指向的对象不是 *class_name* 参数中指定的类 (请参阅 [CObject：： IsKindOf](../../mfc/reference/cobject-class.md#iskindof)) 。 在非 **_DEBUG** 生成中，宏将执行强制转换，而不进行任何类型检查。

*Class_name* 参数中指定的类必须派生自， `CObject` 并且必须使用 DECLARE_DYNAMIC 和 IMPLEMENT_DYNAMIC、DECLARE_DYNCREATE 和 IMPLEMENT_DYNCREATE 或 DECLARE_SERIAL 和 IMPLEMENT_SERIAL 宏，如 [CObject 类：从 cobject 派生类](../../mfc/deriving-a-class-from-cobject.md)中所述。

例如，可以将指向的指针转换为指向 `CMyDoc` `pMyDoc` `CDocument` 使用此表达式的指针：

[!code-cpp[NVC_MFCDocView#197](../../mfc/codesnippet/cpp/type-casting-of-mfc-class-objects_1.cpp)]

如果 `pMyDoc` 未指向直接或间接从派生的对象 `CDocument` ，则该宏将断言。

## <a name="see-also"></a>请参阅

[MFC 宏和全局函数](../../mfc/reference/mfc-macros-and-globals.md)
