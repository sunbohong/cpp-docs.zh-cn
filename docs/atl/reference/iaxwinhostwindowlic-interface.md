---
description: 了解详细信息： IAxWinHostWindowLic 接口
title: IAxWinHostWindowLic 接口
ms.date: 11/04/2016
f1_keywords:
- IAxWinHostWindowLic
- ATLIFACE/ATL::IAxWinHostWindowLic
- ATLIFACE/ATL::CreateControlLic
- ATLIFACE/ATL::CreateControlLicEx
helpviewer_keywords:
- IAxWinHostWindowLic interface
ms.assetid: 750f1520-6bce-428c-aca0-fccbe3f063c7
ms.openlocfilehash: bf13d6f0209b982955fdf015ef47643c83b27eee
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139641"
---
# <a name="iaxwinhostwindowlic-interface"></a>IAxWinHostWindowLic 接口

此接口提供用于操作授权控件及其宿主对象的方法。

## <a name="syntax"></a>语法

```
interface IAxWinHostWindowLic : IAxWinHostWindow
```

## <a name="members"></a>成员

### <a name="methods"></a>方法

|名称|描述|
|-|-|
|[CreateControlLic](#createcontrollic)|创建授权控件，并将其附加到主机对象。|
|[CreateControlLicEx](#createcontrollicex)|创建授权控件，将其附加到主机对象，并选择性地设置事件处理程序。|

## <a name="remarks"></a>备注

`IAxWinHostWindowLic` 继承自 [IAxWinHostWindow](../../atl/reference/iaxwinhostwindow-interface.md) 并添加支持创建授权控件的方法。

有关使用此接口的成员的示例，请参阅 [使用 ATL AXHost 托管 ActiveX 控件](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) 。

## <a name="requirements"></a>要求

此接口的定义以 IDL 或 c + + 形式提供，如下所示。

|定义类型|文件|
|---------------------|----------|
|.IDL|ATLIFace .idl|
|C++|ATLIFace 也包含在 Atlbase.h 中 () |

## <a name="iaxwinhostwindowliccreatecontrollic"></a><a name="createcontrollic"></a> IAxWinHostWindowLic::CreateControlLic

创建授权控件，对其进行初始化，并将其托管在由标识的窗口中 `hWnd` 。

```
STDMETHOD(CreateControlLic)(
    LPCOLESTR lpTricsData,
    HWND hWnd,
    IStream* pStream,
    BSTR bstrLic);
```

### <a name="parameters"></a>parameters

*bstrLic*<br/>
中包含控件的许可证密钥的 BSTR。

### <a name="remarks"></a>备注

有关剩余参数和返回值的说明，请参阅 [IAxWinHostWindow：： CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol) 。

调用此方法等效于调用 [IAxWinHostWindowLic：： CreateControlLicEx](#createcontrollicex)

### <a name="example"></a>示例

有关使用的示例，请参阅 [使用 ATL AXHost 托管 ActiveX 控件](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) `IAxWinHostWindowLic::CreateControlLic` 。

## <a name="iaxwinhostwindowliccreatecontrollicex"></a><a name="createcontrollicex"></a> IAxWinHostWindowLic::CreateControlLicEx

创建许可的 ActiveX 控件，对其进行初始化，并将其托管在指定窗口中，类似于 [IAxWinHostWindow：： CreateControl](../../atl/reference/iaxwinhostwindow-interface.md#createcontrol)。

```
STDMETHOD(CreateControlLicEx)(
    LPCOLESTR lpszTricsData,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnk,
    REFIID riidAdvise,
    IUnknown* punkAdvise,
    BSTR bstrLic);
```

### <a name="parameters"></a>parameters

*bstrLic*<br/>
中包含控件的许可证密钥的 BSTR。

### <a name="remarks"></a>备注

有关剩余参数和返回值的说明，请参阅 [IAxWinHostWindow：： CreateControlEx](../../atl/reference/iaxwinhostwindow-interface.md#createcontrolex) 。

### <a name="example"></a>示例

有关使用的示例，请参阅 [使用 ATL AXHost 托管 ActiveX 控件](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) `IAxWinHostWindowLic::CreateControlLicEx` 。
