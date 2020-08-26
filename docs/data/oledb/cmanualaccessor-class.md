---
title: CManualAccessor 类
ms.date: 11/04/2016
f1_keywords:
- ATL::CManualAccessor
- ATL.CManualAccessor
- CManualAccessor
- ATL::CManualAccessor::AddBindEntry
- ATL.CManualAccessor.AddBindEntry
- CManualAccessor::AddBindEntry
- CManualAccessor.AddBindEntry
- CManualAccessor::AddParameterEntry
- ATL.CManualAccessor.AddParameterEntry
- CManualAccessor.AddParameterEntry
- AddParameterEntry
- ATL::CManualAccessor::AddParameterEntry
- ATL::CManualAccessor::CreateAccessor
- ATL.CManualAccessor.CreateAccessor
- CManualAccessor.CreateAccessor
- CManualAccessor::CreateAccessor
- ATL::CManualAccessor::CreateParameterAccessor
- ATL.CManualAccessor.CreateParameterAccessor
- CManualAccessor.CreateParameterAccessor
- CreateParameterAccessor
- CManualAccessor::CreateParameterAccessor
helpviewer_keywords:
- CManualAccessor class
- AddBindEntry method
- AddParameterEntry method
- CreateAccessor method
- CreateParameterAccessor method
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
ms.openlocfilehash: 32ab31734b8c6e3f72053e1e4f2a8a9233b73995
ms.sourcegitcommit: ec6dd97ef3d10b44e0fedaa8e53f41696f49ac7b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/25/2020
ms.locfileid: "88838095"
---
# <a name="cmanualaccessor-class"></a>CManualAccessor 类

表示旨在供高级使用的访问器类型。

## <a name="syntax"></a>语法

```cpp
class CManualAccessor : public CAccessorBase
```

## <a name="requirements"></a>要求

**标头:** atldbcli.h

## <a name="members"></a>成员

### <a name="methods"></a>方法

| 名称 | 说明 |
|-|-|
|[AddBindEntry](#addbindentry)|向输出列添加绑定项。|
|[AddParameterEntry](#addparameterentry)|向参数访问器添加参数项。|
|[CreateAccessor](#createaccessor)|为列绑定结构分配内存并初始化列数据成员。|
|[CreateParameterAccessor](#createparameteraccessor)|为参数绑定结构分配内存并初始化参数数据成员。|

## <a name="remarks"></a>注解

使用 `CManualAccessor` ，可以通过运行时函数调用指定参数和输出列绑定。

## <a name="cmanualaccessoraddbindentry"></a><a name="addbindentry"></a> CManualAccessor：： AddBindEntry

向输出列添加绑定项。

### <a name="syntax"></a>语法

```cpp
void AddBindEntry(DBORDINAL nOrdinal,
   DBTYPE wType,  DBLENGTH nColumnSize,
   void* pData,
   void* pLength = NULL,
   void* pStatus = NULL) throw ();
```

#### <a name="parameters"></a>参数

请参阅*OLE DB 程序员参考*中的[DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 。

*nOrdinal*<br/>
中列号。

wType <br/>
中数据类型。

*nColumnSize*<br/>
中列大小（字节）。

*pData*<br/>
中指向存储在缓冲区中的列数据的指针。

*pLength*<br/>
中指向字段长度的指针（如果需要）。

*pStatus*<br/>
中指向要绑定到列状态的变量的指针（如果需要）。

### <a name="remarks"></a>注解

若要使用此函数，必须先调用 [CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)。 不能添加比中指定的列数更多的项 `CreateAccessor` 。

## <a name="cmanualaccessoraddparameterentry"></a><a name="addparameterentry"></a> CManualAccessor：： AddParameterEntry

   将参数项添加到参数项结构。

### <a name="syntax"></a>语法

```cpp
void AddParameterEntry(DBORDINAL nOrdinal,
   DBTYPE wType,  DBLENGTH nColumnSize,
   void* pData,
   void* pLength = NULL,
   void* pStatus = NULL,
   DBPARAMIO eParamIO = DBPARAMIO_INPUT) throw ();
```

#### <a name="parameters"></a>参数

请参阅*OLE DB 程序员参考*中的[DBBINDING](/previous-versions/windows/desktop/ms716845(v=vs.85)) 。

*nOrdinal*<br/>
中参数编号。

wType <br/>
中数据类型。

*nColumnSize*<br/>
中列大小（字节）。

*pData*<br/>
中指向存储在缓冲区中的列数据的指针。

*pLength*<br/>
中指向字段长度的指针（如果需要）。

*pStatus*<br/>
中指向要绑定到列状态的变量的指针（如果需要）。

*eParamIO*<br/>
中指定与绑定关联的参数是否为输入、输入/输出或输出参数。

### <a name="remarks"></a>注解

若要使用此函数，必须先调用 [CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md)。

## <a name="cmanualaccessorcreateaccessor"></a><a name="createaccessor"></a> CManualAccessor：： CreateAccessor

为列绑定结构分配内存并初始化列数据成员。

### <a name="syntax"></a>语法

```cpp
HRESULT CreateAccessor(int nBindEntries,
  void* pBuffer,
   DBLENGTH nBufferSize) throw();
```

#### <a name="parameters"></a>参数

*nBindEntries*<br/>
中列数。 此数字应匹配对 [CManualAccessor：： AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md) 函数的调用数。

*pBuffer*<br/>
中指向存储输出列的缓冲区的指针。

*nBufferSize*<br/>
中缓冲区的大小（以字节为单位）。

### <a name="return-value"></a>返回值

标准的 HRESULT 值之一。

### <a name="remarks"></a>注解

在调用函数之前调用此函数 `CManualAccessor::AddBindEntry` 。

## <a name="cmanualaccessorcreateparameteraccessor"></a><a name="createparameteraccessor"></a> CManualAccessor：： CreateParameterAccessor

为参数绑定结构分配内存并初始化参数数据成员。

### <a name="syntax"></a>语法

```cpp
HRESULT CreateParameterAccessor(int nBindEntries,
   void* pBuffer,
   DBLENGTH nBufferSize) throw();
```

#### <a name="parameters"></a>参数

*nBindEntries*<br/>
中列数。

*pBuffer*<br/>
中指向存储输入列的缓冲区的指针。

*nBufferSize*<br/>
中缓冲区的大小（以字节为单位）。

### <a name="return-value"></a>返回值

标准的 HRESULT 值之一。

### <a name="remarks"></a>注解

在调用 [AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md)之前，必须调用此函数。

## <a name="see-also"></a>另请参阅

[DBViewer](../../overview/visual-cpp-samples.md)<br/>
[OLE DB 使用者模板](../../data/oledb/ole-db-consumer-templates-cpp.md)<br/>
[OLE DB 使用者模板参考](../../data/oledb/ole-db-consumer-templates-reference.md)<br/>
[CAccessor 类](../../data/oledb/caccessor-class.md)<br/>
[CDynamicAccessor 类](../../data/oledb/cdynamicaccessor-class.md)<br/>
[CDynamicParameterAccessor 类](../../data/oledb/cdynamicparameteraccessor-class.md)
