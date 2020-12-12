---
description: 了解详细信息： UICheckState 枚举
title: UICheckState 枚举
ms.date: 04/03/2017
f1_keywords:
- afxwinforms/uicheckstate
helpviewer_keywords:
- uicheckstate enumeration [MFC]
ms.assetid: 2ac0098c-20e7-410c-9685-5ead5cb02b63
ms.openlocfilehash: 8c6f250dd6f6646d22aac0fa819b73537ee0f443
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97218636"
---
# <a name="uicheckstate-enumeration"></a>UICheckState 枚举

描述命令的用户界面项的检查状态。

### <a name="syntax"></a>语法

```
public enum class
{
   [DefaultValue(typeid<Microsoft::VisualC::MFC::UICheckState>, "Checked")]
   Unchecked,
   Checked,
   Indeterminate
};
```

### <a name="remarks"></a>备注

[ICommandUI：： Check](icommandui-interface.md#check) 使用这些值来描述用户界面项的状态。
有关使用 Windows 窗体的详细信息，请参阅 [在 MFC 中使用 Windows 窗体用户控件](../../dotnet/using-a-windows-form-user-control-in-mfc.md)。

### <a name="requirements"></a>要求

**标头：** 在程序集 atlmfc\lib\mfcmifc80.dll 中定义的 afxwinforms () 
