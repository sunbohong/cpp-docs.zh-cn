---
description: 了解详细信息： CMFCAcceleratorKey 类
title: CMFCAcceleratorKey 类
ms.date: 11/04/2016
f1_keywords:
- CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::CMFCAcceleratorKey
- AFXACCELERATORKEY/CMFCAcceleratorKey::Format
- AFXACCELERATORKEY/CMFCAcceleratorKey::SetAccelerator
helpviewer_keywords:
- CMFCAcceleratorKey [MFC], CMFCAcceleratorKey
- CMFCAcceleratorKey [MFC], Format
- CMFCAcceleratorKey [MFC], SetAccelerator
ms.assetid: d140fbf7-23db-45ea-a63e-414a5ec7b3d5
ms.openlocfilehash: cb7fc24c4cb4d092c5f109ad892b3778d74a906f
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336615"
---
# <a name="cmfcacceleratorkey-class"></a>CMFCAcceleratorKey 类

实现虚拟键映射和格式设置的帮助器类。

## <a name="syntax"></a>语法

```
class CMFCAcceleratorKey : public CObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCAcceleratorKey：： CMFCAcceleratorKey](#cmfcacceleratorkey)|构造 `CMFCAcceleratorKey` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCAcceleratorKey：： Format](#format)|将加速结构转换为其视觉表示形式。|
|[CMFCAcceleratorKey：： SetAccelerator](#setaccelerator)|设置对象的快捷键 `CMFCAcceleratorKey` 。|

## <a name="remarks"></a>备注

快捷键也称为快捷键。 如果要显示用户输入的键盘快捷方式， [CMFCAcceleratorKeyAssignCtrl 类](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) 会将键盘快捷方式（如 Alt + Shift + s）映射到自定义文本格式，如 "Alt + Shift + s"。 每个对象都将一个 `CMFCAcceleratorKey` 快捷键映射到一个文本格式。

有关如何使用快捷键和快捷键对应表的详细信息，请参阅 [CKeyboardManager 类](../../mfc/reference/ckeyboardmanager-class.md)。

## <a name="example"></a>示例

下面的示例演示如何构造 `CMFCAcceleratorKey` 对象以及如何使用其 `Format` 方法。

[!code-cpp[NVC_MFC_RibbonApp#30](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkey-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CMFCAcceleratorKey`

## <a name="requirements"></a>要求

**标头：** afxacceleratorkey

## <a name="cmfcacceleratorkeycmfcacceleratorkey"></a><a name="cmfcacceleratorkey"></a> CMFCAcceleratorKey：： CMFCAcceleratorKey

构造 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) 对象。

```
CMFCAcceleratorKey();
CMFCAcceleratorKey(LPACCEL lpAccel);
```

### <a name="parameters"></a>parameters

*lpAccel*<br/>
中指向快捷键的指针。

### <a name="remarks"></a>备注

如果在创建时未提供快捷键 `CMFCAccleratorKey` ，请使用 [CMFCAcceleratorKey：： SetAccelerator](#setaccelerator) 方法将快捷键与对象相关联 `CMFCAcceleratorKey` 。

## <a name="cmfcacceleratorkeyformat"></a><a name="format"></a> CMFCAcceleratorKey：： Format

将加速结构转换为其关联的字符串值。

```cpp
void Format(CString& str) const;
```

### <a name="parameters"></a>parameters

*str*<br/>
弄对对象的引用， `CString` 其中方法会写入已翻译的快捷键。

### <a name="remarks"></a>备注

此方法检索关联的快捷键的字符串格式。 可以使用构造函数或方法[CMFCAcceleratorKey：： SetAccelerator](#setaccelerator)设置[CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md)对象的字符串格式。

## <a name="cmfcacceleratorkeysetaccelerator"></a><a name="setaccelerator"></a> CMFCAcceleratorKey：： SetAccelerator

设置 [CMFCAcceleratorKey](../../mfc/reference/cmfcacceleratorkey-class.md) 对象的快捷键。

```cpp
void SetAccelerator(LPACCEL lpAccel);
```

### <a name="parameters"></a>parameters

*lpAccel*<br/>
中指向快捷键的指针。

### <a name="remarks"></a>备注

`CMFCAcceleratorKey`如果在创建时未提供快捷键，请使用此方法设置的快捷键 `CMFCAcceleratorKey` 。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CKeyboardManager 类](../../mfc/reference/ckeyboardmanager-class.md)
