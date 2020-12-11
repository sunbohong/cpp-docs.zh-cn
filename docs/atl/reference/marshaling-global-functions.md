---
description: 了解详细信息：封送全局函数
title: 封送全局函数
ms.date: 11/04/2016
f1_keywords:
- atlbase/ATL::AtlFreeMarshalStream
- atlbase/ATL::AtlMarshalPtrInProc
- atlbase/ATL::AtlUnmarshalPtr
ms.assetid: 877100b5-6ad9-44c5-a2e0-09414f1720d0
ms.openlocfilehash: 5652ccf89090ba1d0f00c03472e29da9158b781e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97157940"
---
# <a name="marshaling-global-functions"></a>封送全局函数

这些函数为封送处理数据和将封送数据转换为接口指针提供支持。

> [!IMPORTANT]
> 下表中列出的函数不能用于在 Windows 运行时中执行的应用程序。

|名称|描述|
|-|-|
|[AtlFreeMarshalStream](#atlfreemarshalstream)|释放封送数据和 `IStream` 指针。|
|[AtlMarshalPtrInProc](#atlmarshalptrinproc)|创建新的流对象并封送指定的接口指针。|
|[AtlUnmarshalPtr](#atlunmarshalptr)|将流的封送数据转换为接口指针。|

## <a name="requirements"></a>要求：

**标头：** atlbase。h

## <a name="atlfreemarshalstream"></a><a name="atlfreemarshalstream"></a> AtlFreeMarshalStream

释放流中的封送数据，然后释放流指针。

```
HRESULT AtlFreeMarshalStream(IStream* pStream);
```

### <a name="parameters"></a>parameters

*pStream*<br/>
中指向 `IStream` 流上用于封送处理的接口的指针。

### <a name="example"></a>示例

请参阅 [AtlMarshalPtrInProc](#atlmarshalptrinproc)的示例。

## <a name="atlmarshalptrinproc"></a><a name="atlmarshalptrinproc"></a> AtlMarshalPtrInProc

创建新的流对象，将代理的 CLSID 写入流，并通过将初始化代理所需的数据写入流来封送指定接口指针。

```
HRESULT AtlMarshalPtrInProc(
    IUnknown* pUnk,
    const IID& iid,
    IStream** ppStream);
```

### <a name="parameters"></a>parameters

*pUnk*<br/>
中指向要封送的接口的指针。

*iid*<br/>
中正在封送的接口的 GUID。

*ppStream*<br/>
弄指向 `IStream` 用于封送处理的新流对象上的接口的指针。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="remarks"></a>备注

设置了 MSHLFLAGS_TABLESTRONG 标志，以便可以将指针封送到多个流。 指针还可以多次取消封送。

如果封送处理失败，则释放流指针。

`AtlMarshalPtrInProc` 仅可用于指向进程内对象的指针。

### <a name="example"></a>示例

[!code-cpp[NVC_ATL_COM#50](../../atl/codesnippet/cpp/marshaling-global-functions_1.cpp)]

## <a name="atlunmarshalptr"></a><a name="atlunmarshalptr"></a> AtlUnmarshalPtr

将流的封送数据转换为可由客户端使用的接口指针。

```
HRESULT AtlUnmarshalPtr(
    IStream* pStream,
    const IID& iid,
    IUnknown** ppUnk);
```

### <a name="parameters"></a>parameters

*pStream*<br/>
中指向正在取消封送的流的指针。

*iid*<br/>
中正在取消封送的接口的 GUID。

*ppUnk*<br/>
弄指向取消封送接口的指针。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

### <a name="example"></a>示例

请参阅 [AtlMarshalPtrInProc](#atlmarshalptrinproc)的示例。

## <a name="see-also"></a>请参阅

[函数](../../atl/reference/atl-functions.md)
