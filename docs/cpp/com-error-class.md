---
description: 了解详细信息： _com_error 类
title: _com_error 类
ms.date: 11/04/2016
f1_keywords:
- _com_error
helpviewer_keywords:
- _com_error class
ms.assetid: 70dafa69-b1fb-4a5c-9249-e857e0793d42
ms.openlocfilehash: 2d297da005feba39838679ed2b7062ce54ad9c38
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97318203"
---
# <a name="_com_error-class"></a>_com_error 类

**Microsoft 专用**

**_Com_error** 对象表示由类型库或某个 com 支持类生成的标头文件中的错误处理包装函数检测到的异常条件。 **_Com_error** 类封装 HRESULT 错误代码和任何关联的 `IErrorInfo Interface` 对象。

### <a name="construction"></a>建筑

| 名称 | 描述 |
|-|-|
|[_com_error](../cpp/com-error-com-error.md)|构造一个 **_com_error** 对象。|

### <a name="operators"></a>运算符

| 名称 | 描述 |
|-|-|
|[operator =](../cpp/com-error-operator-equal.md)|将现有 **_com_error** 对象分配给另一个对象。|

### <a name="extractor-functions"></a>提取程序函数

| 名称 | 描述 |
|-|-|
|[错误](../cpp/com-error-error.md)|检索传递给构造函数的 HRESULT。|
|[ErrorInfo](../cpp/com-error-errorinfo.md)|检索 `IErrorInfo` 传递给构造函数的对象。|
|[WCode](../cpp/com-error-wcode.md)|检索映射到封装的 HRESULT 中的16位错误代码。|

### <a name="ierrorinfo-functions"></a>IErrorInfo 函数

| 名称 | 描述 |
|-|-|
|[说明](../cpp/com-error-description.md)|调用 `IErrorInfo::GetDescription` 函数。|
|[HelpContext](../cpp/com-error-helpcontext.md)|调用 `IErrorInfo::GetHelpContext` 函数。|
|[帮助](../cpp/com-error-helpfile.md)|调用 `IErrorInfo::GetHelpFile` 函数|
|[源](../cpp/com-error-source.md)|调用 `IErrorInfo::GetSource` 函数。|
|[GUID](../cpp/com-error-guid.md)|调用 `IErrorInfo::GetGUID` 函数。|

### <a name="format-message-extractor"></a>格式消息提取程序

| 名称 | 描述 |
|-|-|
|[ErrorMessage](../cpp/com-error-errormessage.md)|检索 **_com_error** 对象中存储的 HRESULT 的字符串消息。|

### <a name="exepinfowcode-to-hresult-mappers"></a>ExepInfo wCode 到 HRESULT 映射器

| 名称 | 描述 |
|-|-|
|[HRESULTToWCode](../cpp/com-error-hresulttowcode.md)|将32位 HRESULT 映射到16位 `wCode` 。|
|[WCodeToHRESULT](../cpp/com-error-wcodetohresult.md)|将16位映射 `wCode` 到32位 HRESULT。|

**结束 Microsoft 专用**

## <a name="requirements"></a>要求

**标头：**\<comdef.h>

`Lib:`有关详细信息，请参阅 comsuppw.lib 或 comsuppwd.lib (参阅[/zc： wchar_t (Wchar_t 是本机类型) ](../build/reference/zc-wchar-t-wchar-t-is-native-type.md)

## <a name="see-also"></a>请参阅

[编译器 COM 支持类](../cpp/compiler-com-support-classes.md)<br/>
[IErrorInfo 接口](/windows/win32/api/oaidl/nn-oaidl-ierrorinfo)
