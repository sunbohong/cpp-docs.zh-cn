---
description: 了解详细信息： IAxWinAmbientDispatchEx 接口
title: IAxWinAmbientDispatchEx 接口
ms.date: 11/04/2016
f1_keywords:
- IAxWinAmbientDispatchEx
- ATLIFACE/ATL::IAxWinAmbientDispatchEx
- ATLIFACE/ATL::SetAmbientDispatch
helpviewer_keywords:
- IAxWinAmbientDispatchEx interface
ms.assetid: 2c25e079-6128-4278-bc72-b2c6195ba7ef
ms.openlocfilehash: c26ce7fb4f41273a498e3b28e9d6e15d4c89f9ea
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97139719"
---
# <a name="iaxwinambientdispatchex-interface"></a>IAxWinAmbientDispatchEx 接口

此接口实现寄宿控件的补充环境属性。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
MIDL_INTERFACE("B2D0778B - AC99 - 4c58 - A5C8 - E7724E5316B5") IAxWinAmbientDispatchEx : public IAxWinAmbientDispatch
```

## <a name="members"></a>成员

### <a name="methods"></a>方法

|名称|描述|
|-|-|
|[SetAmbientDispatch](#setambientdispatch)|调用此方法以使用用户定义的接口来补充默认环境属性接口。|

## <a name="remarks"></a>备注

将此接口包含在静态链接到 ATL 和宿主 ActiveX 控件的 ATL 应用程序中，尤其是具有环境属性的 ActiveX 控件。 不包含此接口将生成此断言： "您是否忘记将 LIBID 传递到 CComModule：： Init"

此接口由 ATL 的 ActiveX 控件宿主对象公开。 派生自 [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)， `IAxWinAmbientDispatchEx` 它添加了一个方法，该方法允许你使用自己的方法来补充 ATL 提供的环境属性接口。

<xref:System.Windows.Forms.AxHost> 将尝试 `IAxWinAmbientDispatch` `IAxWinAmbientDispatchEx` 从包含代码的类型库中加载和类型信息。

如果要链接到 ATL90.dll， **AXHost** 将从 DLL 中的类型库加载类型信息。

有关更多详细信息，请参阅 [使用 ATL AXHost 托管 ActiveX 控件](../../atl/atl-control-containment-faq.md#hosting-activex-controls-using-atl-axhost) 。

## <a name="requirements"></a>要求

此接口的定义以多种形式提供，如下表所示。

|定义类型|文件|
|---------------------|----------|
|.IDL|atliface .idl|
|类型库|ATL.dll|
|C++|atliface 也包含在 Atlbase.h 中 () |

## <a name="iaxwinambientdispatchexsetambientdispatch"></a><a name="setambientdispatch"></a> IAxWinAmbientDispatchEx::SetAmbientDispatch

调用此方法以使用用户定义的接口来补充默认环境属性接口。

```
virtual HRESULT STDMETHODCALLTYPE SetAmbientDispatch(IDispatch* pDispatch) = 0;
```

### <a name="parameters"></a>parameters

*pDispatch*<br/>
指向新接口的指针。

### <a name="return-value"></a>返回值

如果成功，则返回 S_OK; 否则返回错误 HRESULT。

### <a name="remarks"></a>备注

当 `SetAmbientDispatch` 使用指向新接口的指针调用时，如果 [IAxWinAmbientDispatch](../../atl/reference/iaxwinambientdispatch-interface.md)未提供这些属性，则此新接口将用于调用寄宿控件要求的任何属性或方法。

## <a name="see-also"></a>请参阅

[IAxWinAmbientDispatch 接口](../../atl/reference/iaxwinambientdispatch-interface.md)
