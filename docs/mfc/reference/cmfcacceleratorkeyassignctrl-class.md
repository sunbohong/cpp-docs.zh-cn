---
description: 了解详细信息： CMFCAcceleratorKeyAssignCtrl 类
title: CMFCAcceleratorKeyAssignCtrl 类
ms.date: 10/18/2018
f1_keywords:
- CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::GetAccel
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsFocused
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::IsKeyDefined
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage
- AFXACCELERATORKEYASSIGNCTRL/CMFCAcceleratorKeyAssignCtrl::ResetKey
helpviewer_keywords:
- CMFCAcceleratorKeyAssignCtrl [MFC], CMFCAcceleratorKeyAssignCtrl
- CMFCAcceleratorKeyAssignCtrl [MFC], GetAccel
- CMFCAcceleratorKeyAssignCtrl [MFC], IsFocused
- CMFCAcceleratorKeyAssignCtrl [MFC], IsKeyDefined
- CMFCAcceleratorKeyAssignCtrl [MFC], PreTranslateMessage
- CMFCAcceleratorKeyAssignCtrl [MFC], ResetKey
ms.assetid: 89fb8e62-596e-4e71-8c9a-32740347aaab
ms.openlocfilehash: 0f5584dfa521f45841691bff3775d9cd98808b9a
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336590"
---
# <a name="cmfcacceleratorkeyassignctrl-class"></a>CMFCAcceleratorKeyAssignCtrl 类

`CMFCAcceleratorKeyAssignCtrl`类扩展[CEdit 类](../../mfc/reference/cedit-class.md)以支持额外的系统按钮，如 ALT、CONTROL 和 SHIFT。

## <a name="syntax"></a>语法

```
class CMFCAcceleratorKeyAssignCtrl : public CEdit
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CMFCAcceleratorKeyAssignCtrl::CMFCAcceleratorKeyAssignCtrl](#cmfcacceleratorkeyassignctrl)|构造 `CMFCAcceleratorKeyAssignCtrl` 对象。|

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CMFCAcceleratorKeyAssignCtrl：： GetAccel](#getaccel)|检索 `CMFCAcceleratorKeyAssignCtrl` 对象中按下的快捷键的 `ACCEL` 结构。|
|[CMFCAcceleratorKeyAssignCtrl::IsFocused](#isfocused)||
|[CMFCAcceleratorKeyAssignCtrl::IsKeyDefined](#iskeydefined)|确定是否已定义快捷键。|
|[CMFCAcceleratorKeyAssignCtrl::PreTranslateMessage](#pretranslatemessage)|在将窗口消息调度到[TranslateMessage](/windows/win32/api/winuser/nf-winuser-translatemessage)和[DispatchMessage](/windows/win32/api/winuser/nf-winuser-dispatchmessage) Windows 函数之前，由[CWinApp](../../mfc/reference/cwinapp-class.md)类用于转换窗口消息。 （重写 [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage)。）|
|[CMFCAcceleratorKeyAssignCtrl::ResetKey](#resetkey)|重置快捷键。|

## <a name="remarks"></a>备注

此类通过支持快捷键（也称为加速键）来扩展 `CEdit` 类的功能。 `CMFCAcceleratorKeyAssignCtrl`类充当[CEdit 类](../../mfc/reference/cedit-class.md)，还可以识别系统按钮。

此类会将物理快捷键组合映射到字符串值。 例如，假定键组合 ALT + B 映射到字符串“Alt + B”。 当用户按下 `CMFCAcceleratorKeyAssignCtrl` 对象中的此键组合时，会向用户显示“Alt + B”。 有关快捷键和字符串格式之间映射的详细信息，请参阅 [CMFCAcceleratorKey 类](../../mfc/reference/cmfcacceleratorkey-class.md)。

## <a name="example"></a>示例

下列示例演示如何构造 `CMFCAcceleratorKeyAssignCtrl` 对象并使用其 `ResetKey` 方法来重置快捷键。

[!code-cpp[NVC_MFC_RibbonApp#31](../../mfc/reference/codesnippet/cpp/cmfcacceleratorkeyassignctrl-class_1.cpp)]

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWnd](../../mfc/reference/cwnd-class.md)

[CEdit](../../mfc/reference/cedit-class.md)

`CMFCAcceleratorKeyAssignCtrl`

## <a name="requirements"></a>要求

**标头：** afxacceleratorkeyassignctrl

## <a name="cmfcacceleratorkeyassignctrlcmfcacceleratorkeyassignctrl"></a><a name="cmfcacceleratorkeyassignctrl"></a> CMFCAcceleratorKeyAssignCtrl：： CMFCAcceleratorKeyAssignCtrl

构造 [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) 对象。

```
CMFCAcceleratorKeyAssignCtrl();
```

## <a name="cmfcacceleratorkeyassignctrlgetaccel"></a><a name="getaccel"></a> CMFCAcceleratorKeyAssignCtrl：： GetAccel

检索 `ACCEL` 在 [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) 对象中按下的快捷键的结构。

```
ACCEL const* GetAccel() const;
```

### <a name="return-value"></a>返回值

`ACCEL`描述快捷键的结构。

### <a name="remarks"></a>备注

使用此函数可检索 `ACCEL` 用户输入到对象中的快捷键的结构 `CMFCAcceleratorKeyAssignCtrl` 。

## <a name="cmfcacceleratorkeyassignctrlisfocused"></a><a name="isfocused"></a> CMFCAcceleratorKeyAssignCtrl：： IsFocused

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
BOOL IsFocused() const;
```

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcacceleratorkeyassignctrliskeydefined"></a><a name="iskeydefined"></a> CMFCAcceleratorKeyAssignCtrl：： IsKeyDefined

确定是否已在 [CMFCAcceleratorKeyAssignCtrl](../../mfc/reference/cmfcacceleratorkeyassignctrl-class.md) 对象中定义快捷键。

```
BOOL IsKeyDefined() const;
```

### <a name="return-value"></a>返回值

如果用户已经按了定义快捷键的有效键组合，则为非零值;否则为0。

### <a name="remarks"></a>备注

使用此函数可确定用户是否在对象中输入了有效的快捷键 `CMFCAcceleratorKeyAssignCtrl` 。 如果快捷键存在，可以使用 [CMFCAcceleratorKeyAssignCtrl：： GetAccel](#getaccel) 方法获取 `ACCEL` 与此快捷键关联的结构。

## <a name="cmfcacceleratorkeyassignctrlpretranslatemessage"></a><a name="pretranslatemessage"></a> CMFCAcceleratorKeyAssignCtrl：:P reTranslateMessage

有关更多详细信息，请参阅位于 Visual Studio 安装的 **VC \\ atlmfc \\ src \\ mfc** 文件夹中的源代码。

```
virtual BOOL PreTranslateMessage(MSG* pMsg);
```

### <a name="parameters"></a>parameters

中 *pMsg*<br/>

### <a name="return-value"></a>返回值

### <a name="remarks"></a>备注

## <a name="cmfcacceleratorkeyassignctrlresetkey"></a><a name="resetkey"></a> CMFCAcceleratorKeyAssignCtrl：： ResetKey

重置快捷键。

```cpp
void ResetKey();
```

### <a name="remarks"></a>备注

函数清除编辑控件文本。 这包括用户按下的任何快捷键。

## <a name="see-also"></a>请参阅

[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[Classes](../../mfc/reference/mfc-classes.md)<br/>
[CMFCAcceleratorKey 类](../../mfc/reference/cmfcacceleratorkey-class.md)
