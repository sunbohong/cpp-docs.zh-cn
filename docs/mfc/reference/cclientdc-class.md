---
description: 了解详细信息： CClientDC 类
title: CClientDC 类
ms.date: 11/04/2016
f1_keywords:
- CClientDC
- AFXWIN/CClientDC
- AFXWIN/CClientDC::CClientDC
- AFXWIN/CClientDC::m_hWnd
helpviewer_keywords:
- CClientDC [MFC], CClientDC
- CClientDC [MFC], m_hWnd
ms.assetid: 8a871d6b-06f8-496e-9fa3-9a5780848369
ms.openlocfilehash: 27735929734388ccb25eaf178e49d63884beed0d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97122455"
---
# <a name="cclientdc-class"></a>CClientDC 类

负责在构造时调用 Windows 函数 [GetDC](/windows/win32/api/winuser/nf-winuser-getdc) ，并在析构时调用 [ReleaseDC](/windows/win32/api/winuser/nf-winuser-releasedc) 。

## <a name="syntax"></a>语法

```
class CClientDC : public CDC
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CClientDC：： CClientDC](#cclientdc)|构造 `CClientDC` 连接到的对象 `CWnd` 。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CClientDC：： m_hWnd](#m_hwnd)|此对其有效的窗口的 HWND `CClientDC` 。|

## <a name="remarks"></a>备注

这意味着与对象关联的设备上下文 `CClientDC` 是窗口的工作区。

有关的详细信息 `CClientDC` ，请参阅 [设备上下文](../../mfc/device-contexts.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CClientDC`

## <a name="requirements"></a>要求

**标头:** afxwin.h

## <a name="cclientdccclientdc"></a><a name="cclientdc"></a> CClientDC：： CClientDC

构造一个 `CClientDC` 对象，该对象访问 *pWnd* 指向的 [CWnd](../../mfc/reference/cwnd-class.md)的工作区。

```
explicit CClientDC(CWnd* pWnd);
```

### <a name="parameters"></a>parameters

*pWnd*<br/>
设备上下文对象将访问的工作区所在的窗口。

### <a name="remarks"></a>备注

构造函数调用 Windows 函数 [GetDC](/windows/win32/api/winuser/nf-winuser-getdc)。

`CResourceException`如果 Windows 调用失败，则会引发) 类型的异常 (`GetDC` 。 如果 Windows 已分配了其所有可用设备上下文，则设备上下文可能不可用。 您的应用程序将在 Windows 下的任何给定时间为五个常见显示上下文进行竞争。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#42](../../mfc/codesnippet/cpp/cclientdc-class_1.cpp)]

## <a name="cclientdcm_hwnd"></a><a name="m_hwnd"></a> CClientDC：： m_hWnd

`HWND` `CWnd` 用于构造对象的指针的 `CClientDC` 。

```
HWND m_hWnd;
```

### <a name="remarks"></a>备注

*m_hWnd* 是受保护的变量。

### <a name="example"></a>示例

  请参阅 [CClientDC：： CClientDC](#cclientdc)的示例。

## <a name="see-also"></a>请参阅

[MFC 示例 MDI](../../overview/visual-cpp-samples.md)<br/>
[CDC 类](../../mfc/reference/cdc-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CDC 类](../../mfc/reference/cdc-class.md)
