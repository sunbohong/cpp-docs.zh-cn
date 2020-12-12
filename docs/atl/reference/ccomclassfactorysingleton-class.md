---
description: 了解详细信息： CComClassFactorySingleton 类
title: CComClassFactorySingleton 类
ms.date: 11/04/2016
f1_keywords:
- CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton
- ATLCOM/ATL::CComClassFactorySingleton::CreateInstance
- ATLCOM/ATL::CComClassFactorySingleton::m_spObj
helpviewer_keywords:
- CComClassFactorySingleton class
ms.assetid: debb983c-382b-487b-8d42-7ea26dc158b8
ms.openlocfilehash: eaf09f823a6d8d62f102e6e36116b56270248f9e
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97146856"
---
# <a name="ccomclassfactorysingleton-class"></a>CComClassFactorySingleton 类

此类派生自 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) ，并使用 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 构造单个对象。

> [!IMPORTANT]
> 此类及其成员不能用于在 Windows 运行时中执行的应用程序。

## <a name="syntax"></a>语法

```
template<class T>
class CComClassFactorySingleton : public CComClassFactory
```

#### <a name="parameters"></a>parameters

*T*<br/>
你的类。

`CComClassFactorySingleton` 派生自 [CComClassFactory](../../atl/reference/ccomclassfactory-class.md) ，并使用 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 构造单个对象。 每次调用该 `CreateInstance` 方法时，都只会查询此对象的接口指针。

## <a name="members"></a>成员

### <a name="public-methods"></a>公共方法

|“属性”|描述|
|----------|-----------------|
|[CComClassFactorySingleton：： CreateInstance](#createinstance)|查询 `m_spObj` 接口指针。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CComClassFactorySingleton：： m_spObj](#m_spobj)|构造的 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 对象 `CComClassFactorySingleton` 。|

## <a name="remarks"></a>备注

ATL 对象通过从 [CComCoClass](../../atl/reference/ccomcoclass-class.md)派生来通常获取类工厂。 此类包含宏 [DECLARE_CLASSFACTORY](aggregation-and-class-factory-macros.md#declare_classfactory)，该宏声明 `CComClassFactory` 为默认类工厂。 若要使用 `CComClassFactorySingleton` ，请在对象的类定义中指定 [DECLARE_CLASSFACTORY_SINGLETON](aggregation-and-class-factory-macros.md#declare_classfactory_singleton) 宏。 例如：

[!code-cpp[NVC_ATL_COM#10](../../atl/codesnippet/cpp/ccomclassfactorysingleton-class_1.h)]

## <a name="inheritance-hierarchy"></a>继承层次结构

`CComObjectRootBase`

[CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)

`IClassFactory`

[CComClassFactory](../../atl/reference/ccomclassfactory-class.md)

`CComClassFactorySingleton`

## <a name="requirements"></a>要求

**标头：** atlcom。h

## <a name="ccomclassfactorysingletoncreateinstance"></a><a name="createinstance"></a> CComClassFactorySingleton：： CreateInstance

`QueryInterface`通过[m_spObj](#m_spobj)调用检索接口指针。

```
STDMETHOD(CreateInstance)(LPUNKNOWN pUnkOuter, REFIID riid, void** ppvObj);
```

### <a name="parameters"></a>parameters

*pUnkOuter*<br/>
中如果该对象是作为聚合的一部分创建的，则 *pUnkOuter* 必须是外部未知的。 否则， *pUnkOuter* 必须为 NULL。

*riid*<br/>
中所请求的接口的 IID。 如果 *pUnkOuter* 为非 NULL，则 *riid* 必须是 `IID_IUnknown` 。

*ppvObj*<br/>
弄指向由 *riid* 标识的接口指针的指针。 如果对象不支持此接口，则将 *ppvObj* 设置为 NULL。

### <a name="return-value"></a>返回值

标准的 HRESULT 值。

## <a name="ccomclassfactorysingletonm_spobj"></a><a name="m_spobj"></a> CComClassFactorySingleton：： m_spObj

构造的 [CComObjectGlobal](../../atl/reference/ccomobjectglobal-class.md) 对象 `CComClassFactorySingleton` 。

```
CComPtr<IUnknown> m_spObj;
```

### <a name="remarks"></a>备注

每次调用 [CreateInstance](#createinstance) 方法只会查询此对象的接口指针。

请注意，当前的形式会 `m_spObj` 提供与 `CComClassFactorySingleton` 在以前版本的 ATL 中工作方式的重大更改。 在以前的版本中 `CComClassFactorySingleton` ，对象是在服务器初始化期间与类工厂同时创建的。 在 Visual C++ .NET 2003 及更高版本中，在第一个请求上按延迟创建对象。 此更改可能导致依赖于早期初始化的程序出错。

## <a name="see-also"></a>请参阅

[IClassFactory](/windows/win32/api/unknwnbase/nn-unknwnbase-iclassfactory)<br/>
[CComClassFactory2 类](../../atl/reference/ccomclassfactory2-class.md)<br/>
[CComClassFactoryAutoThread 类](../../atl/reference/ccomclassfactoryautothread-class.md)<br/>
[CComObjectRootEx 类](../../atl/reference/ccomobjectrootex-class.md)<br/>
[CComGlobalsThreadModel](atl-typedefs.md#ccomglobalsthreadmodel)<br/>
[类概述](../../atl/atl-class-overview.md)
