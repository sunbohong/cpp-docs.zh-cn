---
description: 了解详细信息： CLongBinary 类
title: CLongBinary 类
ms.date: 11/04/2016
f1_keywords:
- CLongBinary
- AFXDB_/CLongBinary
- AFXDB_/CLongBinary::CLongBinary
- AFXDB_/CLongBinary::m_dwDataLength
- AFXDB_/CLongBinary::m_hData
helpviewer_keywords:
- CLongBinary class [MFC]
ms.assetid: f4320059-aeb4-4ee5-bc2b-25f19d898ef5
ms.openlocfilehash: ad6836ce6ee7e95929f69d226dcab61fc5482277
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97336715"
---
# <a name="clongbinary-class"></a>CLongBinary 类

简化对数据库中超大二进制数据对象（经常称作 BLOB，即“二进制大对象”）的使用。

## <a name="syntax"></a>语法

```
class CLongBinary : public CObject
```

## <a name="members"></a>成员

### <a name="public-constructors"></a>公共构造函数

|“属性”|描述|
|----------|-----------------|
|[CLongBinary：： CLongBinary](#clongbinary)|构造 `CLongBinary` 对象。|

### <a name="public-data-members"></a>公共数据成员

|名称|描述|
|----------|-----------------|
|[CLongBinary：： m_dwDataLength](#m_dwdatalength)|包含存储其句柄的数据对象的实际大小（以字节为单位） `m_hData` 。|
|[CLongBinary：： m_hData](#m_hdata)|包含实际 image 对象的 Windows HGLOBAL 句柄。|

## <a name="remarks"></a>备注

例如，SQL 表中的记录字段可能包含表示图片的位图。 `CLongBinary`对象存储此类对象，并跟踪其大小。

> [!NOTE]
> 一般而言，现在更好的做法是将 [CByteArray](../../mfc/reference/cbytearray-class.md) 与 [DFX_Binary](record-field-exchange-functions.md#dfx_binary) 函数结合使用。 你仍可使用 `CLongBinary` ，但在 Win32 中，通常会 `CByteArray` 提供更多功能，因为16位的大小限制不再出现 `CByteArray` 。 此建议适用于使用数据访问对象编程 (DAO) 以及开放式数据库连接 (ODBC) 。

若要使用 `CLongBinary` 对象，请 `CLongBinary` 在记录集类中声明类型的字段数据成员。 此成员将是记录集类的嵌入成员，并且将在构造记录集时构造。 `CLongBinary`构造对象之后，记录字段交换 (RFX) 机制从数据源的当前记录中的字段加载数据对象，并在记录更新时将数据对象存储回记录。 RFX 查询数据源的二进制大型对象的大小，通过 `CLongBinary` 对象的数据成员) 为其分配存储 (， `m_hData` 并将 `HGLOBAL` 句柄存储在中 `m_hData` 。 RFX 还将数据对象的实际大小存储在 `m_dwDataLength` 数据成员中。 `m_hData`使用与处理 Windows 句柄中存储的数据相同的技术，使用对象中的数据 `HGLOBAL` 。

销毁记录集时，嵌入 `CLongBinary` 对象也会被销毁，析构函数会释放 `HGLOBAL` 数据句柄。

有关大型对象和使用的详细信息 `CLongBinary` ，请参阅文章 [记录集 (odbc) ](../../data/odbc/recordset-odbc.md) 和 [记录集：在 Odbc)  (处理大型数据项 ](../../data/odbc/recordset-working-with-large-data-items-odbc.md)。

## <a name="inheritance-hierarchy"></a>继承层次结构

[CObject](../../mfc/reference/cobject-class.md)

`CLongBinary`

## <a name="requirements"></a>要求

**标头：** afxdb_。h

## <a name="clongbinaryclongbinary"></a><a name="clongbinary"></a> CLongBinary：： CLongBinary

构造 `CLongBinary` 对象。

```
CLongBinary();
```

## <a name="clongbinarym_dwdatalength"></a><a name="m_dwdatalength"></a> CLongBinary：： m_dwDataLength

以字节为单位存储中存储的数据的实际大小（以字节为单位） `m_hData` 。

```
SQLULEN m_dwDataLength;
```

### <a name="remarks"></a>备注

此大小可能小于为数据分配的内存块的大小。 调用 Win32 [GLobalSize](/windows/win32/api/winbase/nf-winbase-globalsize) 函数以获取分配的大小。

## <a name="clongbinarym_hdata"></a><a name="m_hdata"></a> CLongBinary：： m_hData

将 Windows HGLOBAL 句柄存储到实际的二进制大型对象数据。

```
HGLOBAL m_hData;
```

## <a name="see-also"></a>请参阅

[CObject 类](../../mfc/reference/cobject-class.md)<br/>
[层次结构图](../../mfc/hierarchy-chart.md)<br/>
[CRecordset 类](../../mfc/reference/crecordset-class.md)
