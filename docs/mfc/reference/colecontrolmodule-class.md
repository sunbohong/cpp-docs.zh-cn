---
description: 了解详细信息： COleControlModule 类
title: COleControlModule 类
ms.date: 11/04/2016
f1_keywords:
- OleControlModule
helpviewer_keywords:
- OLE control modules [MFC]
- MFC ActiveX controls [MFC], OLE control modules
- COleControlModule class [MFC]
- control modules [MFC]
ms.assetid: 0721724d-d4af-4eda-ad34-5a2b27810dd4
ms.openlocfilehash: f88296b7c0e897f82227343b31ca2f639902256e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97227476"
---
# <a name="colecontrolmodule-class"></a>COleControlModule 类

可以派生出 OLE 控件模块对象的基类。

## <a name="syntax"></a>语法

```
class COleControlModule : public CWinApp
```

## <a name="remarks"></a>备注

此类提供用于初始化控制模块的成员函数。 使用 Microsoft 基础类的每个 OLE 控件模块只能包含一个派生自的对象 `COleControlModule` 。 构造其他 c + + 全局对象时，将构造此对象。 `COleControlModule`在全局级别声明派生的对象。

有关使用类的详细信息 `COleControlModule` ，请参阅 [CWinApp](../../mfc/reference/cwinapp-class.md) 类和 [ActiveX 控件](../../mfc/mfc-activex-controls.md)文章。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CCmdTarget](../../mfc/reference/ccmdtarget-class.md)

[CWinThread](../../mfc/reference/cwinthread-class.md)

[CWinApp](../../mfc/reference/cwinapp-class.md)

`COleControlModule`

## <a name="requirements"></a>要求

**标头：** afxctl。h

## <a name="see-also"></a>请参阅

[MFC 示例 TESTHELP](../../overview/visual-cpp-samples.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)
