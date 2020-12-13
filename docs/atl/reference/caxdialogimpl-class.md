---
description: 了解详细信息： CAxDialogImpl 类
title: CAxDialogImpl 类
ms.date: 11/04/2016
f1_keywords:
- CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl
- ATLWIN/ATL::CAxDialogImpl::AdviseSinkMap
- ATLWIN/ATL::CAxDialogImpl::Create
- ATLWIN/ATL::CAxDialogImpl::DestroyWindow
- ATLWIN/ATL::CAxDialogImpl::DoModal
- ATLWIN/ATL::CAxDialogImpl::EndDialog
- ATLWIN/ATL::CAxDialogImpl::GetDialogProc
- ATLWIN/ATL::CAxDialogImpl::GetIDD
- ATLWIN/ATL::CAxDialogImpl::IsDialogMessage
- ATLWIN/ATL::CAxDialogImpl::m_bModal
helpviewer_keywords:
- CAxDialogImpl class
- ATL, dialog boxes
ms.assetid: 817df483-3fa8-44e7-8487-72ba0881cd27
ms.openlocfilehash: e84ce636642ed268ec8ca0dd25e0f3c5f3bc10c0
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97152446"
---
# <a name="caxdialogimpl-class"></a>CAxDialogImpl 类

此类实现 (承载 ActiveX 控件的模式或无模式) 的对话框。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template <class T, class TBase = CWindow>
class ATL_NO_VTABLE CAxDialogImpl : public CDialogImplBaseT<TBase>
```

#### <a name="parameters"></a>parameters

*T*<br/>
派生自的类 `CAxDialogImpl` 。

*TBase*<br/>
的基窗口类 `CDialogImplBaseT` 。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CAxDialogImpl::AdviseSinkMap](#advisesinkmap)|调用此方法可建议或 unadvise 对象的接收器映射事件映射中的所有项。|
|[CAxDialogImpl：： Create](#create)|调用此方法可创建无模式对话框。|
|[CAxDialogImpl：:D estroyWindow](#destroywindow)|调用此方法以销毁无模式对话框。|
|[CAxDialogImpl：:D oModal](#domodal)|调用此方法可创建模式对话框。|
|[CAxDialogImpl：： EndDialog](#enddialog)|调用此方法可销毁模式对话框。|
|[CAxDialogImpl::GetDialogProc](#getdialogproc)|调用此方法以获取指向 `DialogProc` 回调函数的指针。|
|[CAxDialogImpl::GetIDD](#getidd)|调用此方法以获取对话框模板资源 ID|
|[CAxDialogImpl::IsDialogMessage](#isdialogmessage)|调用此方法可确定消息是否适用于此对话框，如果是，则处理消息。|

### <a name="protected-data-members"></a>受保护的数据成员

|名称|描述|
|----------|-----------------|
|[CAxDialogImpl：： m_bModal](#m_bmodal)|仅存在于调试版本中的变量，如果对话框是模式的，则设置为 true。|

## <a name="remarks"></a>备注

`CAxDialogImpl` 允许您创建模式对话框或无模式对话框。 `CAxDialogImpl` 提供对话框过程，该过程使用默认消息映射将消息定向到适当的处理程序。

`CAxDialogImpl` 派生自 `CDialogImplBaseT` ，默认情况下从 *TBase* 派生 (， `CWindow`) 和 `CMessageMap` 。

类必须定义一个指定对话框模板资源 ID 的 IDD 成员。 例如，使用 " **添加类** " 对话框添加 ATL 对话框对象会自动将以下行添加到类：

[!code-cpp[NVC_ATL_Windowing#41](../../atl/codesnippet/cpp/caxdialogimpl-class_1.h)]

其中 `MyDialog` 是在 ATL 对话框向导中输入的 **短名称** 。

有关详细信息，请参阅 [实现对话框](../../atl/implementing-a-dialog-box.md) 。

请注意，使用创建的模式对话框上的 ActiveX 控件 `CAxDialogImpl` 将不支持快捷键。 若要支持使用创建的对话框中的快捷键 `CAxDialogImpl` ，请创建无模式对话框，并使用您自己的消息循环，在从队列中获取消息后使用 [CAxDialogImpl：： IsDialogMessage](#isdialogmessage) 来处理加速键。

有关的详细信息 `CAxDialogImpl` ，请参阅 [ATL 控件包含常见问题解答](../../atl/atl-control-containment-faq.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CMessageMap](../../atl/reference/cmessagemap-class.md)

`TBase`

`CWindowImplRoot`

`CDialogImplBaseT`

`CAxDialogImpl`

## <a name="requirements"></a>要求

**标头：** atlwin。h

## <a name="caxdialogimpladvisesinkmap"></a><a name="advisesinkmap"></a> CAxDialogImpl::AdviseSinkMap

调用此方法可建议或 unadvise 对象的接收器映射事件映射中的所有项。

```
HRESULT AdviseSinkMap(bool bAdvise);
```

### <a name="parameters"></a>parameters

*bAdvise*<br/>
如果建议所有接收项，则设置为 true;如果所有接收器条目都是 unadvised，则为 false。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

## <a name="caxdialogimplcreate"></a><a name="create"></a> CAxDialogImpl：： Create

调用此方法可创建无模式对话框。

```
HWND Create(HWND hWndParent, LPARAM dwInitParam = NULL);
HWND Create(HWND hWndParent, RECT&, LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>parameters

*hWndParent*<br/>
中所有者窗口的句柄。

*dwInitParam*<br/>
中在 WM_INITDIALOG 消息的 *lParam* 参数中指定要传递到对话框的值。

*RECT&*<br/>
未使用此参数。 此参数由传入 `CComControl` 。

### <a name="return-value"></a>返回值

新创建的对话框的句柄。

### <a name="remarks"></a>备注

此对话框自动附加到 `CAxDialogImpl` 对象。 若要创建模式对话框，请调用 [DoModal](#domodal)。

仅提供第二个替代，以便可以将对话框与 [CComControl](../../atl/reference/ccomcontrol-class.md)一起使用。

## <a name="caxdialogimpldestroywindow"></a><a name="destroywindow"></a> CAxDialogImpl：:D estroyWindow

调用此方法以销毁无模式对话框。

```
BOOL DestroyWindow();
```

### <a name="return-value"></a>返回值

如果成功销毁窗口，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

不要调用 `DestroyWindow` 来销毁模式对话框。 改为调用 [EndDialog](#enddialog) 。

## <a name="caxdialogimpldomodal"></a><a name="domodal"></a> CAxDialogImpl：:D oModal

调用此方法可创建模式对话框。

```
INT_PTR DoModal(
    HWND hWndParent = ::GetActiveWindow(),
    LPARAM dwInitParam = NULL);
```

### <a name="parameters"></a>parameters

*hWndParent*<br/>
中所有者窗口的句柄。 默认值为 [GetActiveWindow](/windows/win32/api/winuser/nf-winuser-getactivewindow) Win32 函数的返回值。

*dwInitParam*<br/>
中在 WM_INITDIALOG 消息的 *lParam* 参数中指定要传递到对话框的值。

### <a name="return-value"></a>返回值

如果成功，则为对 [EndDialog](#enddialog)的调用中指定的 *nRetCode* 参数的值;否则为-1。

### <a name="remarks"></a>备注

此对话框自动附加到 `CAxDialogImpl` 对象。

若要创建无模式对话框，请调用 [create](#create)。

## <a name="caxdialogimplenddialog"></a><a name="enddialog"></a> CAxDialogImpl：： EndDialog

调用此方法可销毁模式对话框。

```
BOOL EndDialog(int nRetCode);
```

### <a name="parameters"></a>parameters

*nRetCode*<br/>
中 [DoModal](#domodal)返回的值。

### <a name="return-value"></a>返回值

如果销毁对话框，则为 TRUE;否则为 FALSE。

### <a name="remarks"></a>备注

`EndDialog` 必须通过对话框过程调用。 销毁对话框后，Windows 会将 *nRetCode* 的值用作创建对话框的的返回值 `DoModal` 。

> [!NOTE]
> 不要调用 `EndDialog` 以销毁无模式对话框。 改为调用 [DestroyWindow](#destroywindow) 。

## <a name="caxdialogimplgetdialogproc"></a><a name="getdialogproc"></a> CAxDialogImpl::GetDialogProc

调用此方法以获取指向 `DialogProc` 回调函数的指针。

```
virtual DLGPROC GetDialogProc();
```

### <a name="return-value"></a>返回值

返回一个指向 `DialogProc` 回调函数的指针。

### <a name="remarks"></a>备注

`DialogProc`函数是应用程序定义的回调函数。

## <a name="caxdialogimplgetidd"></a><a name="getidd"></a> CAxDialogImpl::GetIDD

调用此方法可获取对话框模板资源 ID。

```
int GetIDD();
```

### <a name="return-value"></a>返回值

返回对话框模板资源 ID。

## <a name="caxdialogimplisdialogmessage"></a><a name="isdialogmessage"></a> CAxDialogImpl::IsDialogMessage

调用此方法可确定消息是否适用于此对话框，如果是，则处理消息。

```
BOOL IsDialogMessage(LPMSG pMsg);
```

### <a name="parameters"></a>parameters

*pMsg*<br/>
指向包含要检查的消息的 [MSG](/windows/win32/api/winuser/ns-winuser-msg) 结构的指针。

### <a name="return-value"></a>返回值

如果消息已处理，则返回 TRUE，否则返回 FALSE。

### <a name="remarks"></a>备注

此方法旨在从消息循环中调用。

## <a name="caxdialogimplm_bmodal"></a><a name="m_bmodal"></a> CAxDialogImpl：： m_bModal

仅存在于调试版本中的变量，如果对话框是模式的，则设置为 true。

```
bool m_bModal;
```

## <a name="see-also"></a>请参阅

[CDialogImpl 类](../../atl/reference/cdialogimpl-class.md)<br/>
[类概述](../../atl/atl-class-overview.md)
