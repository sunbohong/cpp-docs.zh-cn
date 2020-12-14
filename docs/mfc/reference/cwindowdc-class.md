---
description: 了解详细信息： CWindowDC 类
title: CWindowDC 类
ms.date: 11/04/2016
f1_keywords:
- CWindowDC
- AFXWIN/CWindowDC
- AFXWIN/CWindowDC::CWindowDC
- AFXWIN/CWindowDC::m_hWnd
helpviewer_keywords:
- CWindowDC [MFC], CWindowDC
- CWindowDC [MFC], m_hWnd
ms.assetid: 876a3641-4cde-471c-b0d1-fe58b32af79c
ms.openlocfilehash: 1fc36614f5e6ded32a47146771991c3ab06998eb
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97344921"
---
# <a name="cwindowdc-class"></a>CWindowDC 类

派生自 `CDC`。

## <a name="syntax"></a>语法

```
class CWindowDC : public CDC
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CWindowDC::CWindowDC](#cwindowdc)|构造 `CWindowDC` 对象。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CWindowDC：： m_hWnd](#m_hwnd)|此附加到的 HWND `CWindowDC` 。|

## <a name="remarks"></a>备注

在构造时调用 Windows 函数 [GetWindowDC](/windows/win32/api/winuser/nf-winuser-getwindowdc)，并在析构时调用 [ReleaseDC](/windows/win32/api/winuser/nf-winuser-releasedc) 。 这意味着 `CWindowDC` 对象) 的客户端和非工作区都访问 [CWnd](../../mfc/reference/cwnd-class.md) (的整个屏幕区域。

有关使用的详细信息 `CWindowDC` ，请参阅 [设备上下文](../../mfc/device-contexts.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

[CDC](../../mfc/reference/cdc-class.md)

`CWindowDC`

## <a name="requirements"></a>要求

标头: afxwin.h

## <a name="cwindowdccwindowdc"></a><a name="cwindowdc"></a> CWindowDC::CWindowDC

构造一个 `CWindowDC` 对象，该对象访问整个屏幕区域 (pWnd 所指向对象的客户端和非工作) `CWnd` 。 

```
explicit CWindowDC(CWnd* pWnd);
```

### <a name="parameters"></a>parameters

*pWnd*<br/>
设备上下文对象将访问的工作区所在的窗口。

### <a name="remarks"></a>备注

构造函数调用 Windows 函数 [GetWindowDC](/windows/win32/api/winuser/nf-winuser-getwindowdc)。

`CResourceException`如果 Windows 调用失败，则会引发) 类型的异常 (`GetWindowDC` 。 如果 Windows 已分配了其所有可用设备上下文，则设备上下文可能不可用。 您的应用程序将在 Windows 下的任何给定时间为五个常见显示上下文进行竞争。

### <a name="example"></a>示例

[!code-cpp[NVC_MFCDocView#188](../../mfc/codesnippet/cpp/cwindowdc-class_1.cpp)]

## <a name="cwindowdcm_hwnd"></a><a name="m_hwnd"></a> CWindowDC：： m_hWnd

指针的 HWND `CWnd` 用于构造 `CWindowDC` 对象。

```
HWND m_hWnd;
```

### <a name="remarks"></a>备注

`m_hWnd` 是 HWND 类型的受保护变量。

### <a name="example"></a>示例

  请参阅 [CWindowDC：： CWindowDC](#cwindowdc)的示例。

## <a name="see-also"></a>请参阅

[CDC 类](../../mfc/reference/cdc-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CDC 类](../../mfc/reference/cdc-class.md)
