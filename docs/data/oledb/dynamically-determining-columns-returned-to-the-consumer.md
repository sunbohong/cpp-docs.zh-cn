---
description: 了解详细信息：动态确定返回给使用者的列
title: 动态确定返回给使用者的列
ms.date: 10/26/2018
helpviewer_keywords:
- bookmarks [C++], dynamically determining columns
- dynamically determining columns [C++]
ms.assetid: 58522b7a-894e-4b7d-a605-f80e900a7f5f
ms.openlocfilehash: fd70164edff5b9267e01a891a143920ac4e60a35
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97287562"
---
# <a name="dynamically-determining-columns-returned-to-the-consumer"></a>动态确定返回给使用者的列

PROVIDER_COLUMN_ENTRY 宏通常会处理 `IColumnsInfo::GetColumnsInfo` 调用。 但是，因为使用者可能选择使用书签，所以提供程序必须能够根据使用者是否请求书签来更改返回的列。

若要处理 `IColumnsInfo::GetColumnsInfo` 调用，请 `GetColumnInfo` 从 `CCustomWindowsFile` *自定义* 的 RS 中的用户记录中删除定义函数的 PROVIDER_COLUMN_MAP，并将其替换为你自己的函数的定义 `GetColumnInfo` ：

```cpp
////////////////////////////////////////////////////////////////////////
// CustomRS.H
class CCustomWindowsFile
{
public:
   DWORD dwBookmark;
   static const int iSize = 256;
   TCHAR szCommand[iSize];
   TCHAR szText[iSize];
   TCHAR szCommand2[iSize];
   TCHAR szText2[iSize];
  
   static ATLCOLUMNINFO* GetColumnInfo(void* pThis, ULONG* pcCols);
   bool operator==(const CCustomWindowsFile& am)
   {
      return (lstrcmpi(szCommand, am.szCommand) == 0);
   }
};
```

接下来， `GetColumnInfo` 在 *自定义* RS .cpp 中实现该函数，如下面的代码所示。

`GetColumnInfo` 首先检查是否设置了 OLE DB 属性 `DBPROP_BOOKMARKS` 。 若要获取属性，请 `GetColumnInfo` 使用指向 `pRowset` 行集对象)  (的指针。 `pThis`指针表示创建行集的类，它是存储属性映射的类。 `GetColumnInfo` typecasts 指向 `pThis` 指针的指针 `RCustomRowset` 。

若要检查 `DBPROP_BOOKMARKS` 属性，请 `GetColumnInfo` 使用 `IRowsetInfo` 接口，该接口可通过调用接口上的来获取 `QueryInterface` `pRowset` 。 作为替代方法，可以改为使用 ATL [CComQIPtr](../../atl/reference/ccomqiptr-class.md) 方法。

```cpp
////////////////////////////////////////////////////////////////////
// CustomRS.cpp
ATLCOLUMNINFO* CCustomWindowsFile::GetColumnInfo(void* pThis, ULONG* pcCols)
{
   static ATLCOLUMNINFO _rgColumns[5];
   ULONG ulCols = 0;
  
   // Check the property flag for bookmarks; if it is set, set the zero
   // ordinal entry in the column map with the bookmark information.
   CCustomRowset* pRowset = (CCustomRowset*) pThis;
   CComQIPtr<IRowsetInfo, &IID_IRowsetInfo> spRowsetProps = pRowset;
  
   CDBPropIDSet set(DBPROPSET_ROWSET);
   set.AddPropertyID(DBPROP_BOOKMARKS);
   DBPROPSET* pPropSet = NULL;
   ULONG ulPropSet = 0;
   HRESULT hr;
  
   if (spRowsetProps)
      hr = spRowsetProps->GetProperties(1, &set, &ulPropSet, &pPropSet);
  
   if (pPropSet)
   {
      CComVariant var = pPropSet->rgProperties[0].vValue;
      CoTaskMemFree(pPropSet->rgProperties);
      CoTaskMemFree(pPropSet);
  
      if (SUCCEEDED(hr) && (var.boolVal == VARIANT_TRUE))
      {
         ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),
         DBTYPE_BYTES, 0, 0, GUID_NULL, CCustomWindowsFile, dwBookmark,
         DBCOLUMNFLAGS_ISBOOKMARK)
         ulCols++;
      }
   }
  
   // Next, set the other columns up.
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command"), 1, 256, DBTYPE_STR, 0xFF, 0xFF,
      GUID_NULL, CCustomWindowsFile, szCommand)
   ulCols++;
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text"), 2, 256, DBTYPE_STR, 0xFF, 0xFF,
      GUID_NULL, CCustomWindowsFile, szText)
   ulCols++;
  
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Command2"), 3, 256, DBTYPE_STR, 0xFF, 0xFF,
      GUID_NULL, CCustomWindowsFile, szCommand2)
   ulCols++;
   ADD_COLUMN_ENTRY(ulCols, OLESTR("Text2"), 4, 256, DBTYPE_STR, 0xFF, 0xFF,
      GUID_NULL, CCustomWindowsFile, szText2)
   ulCols++;
  
   if (pcCols != NULL)
      *pcCols = ulCols;
  
   return _rgColumns;
}
```

此示例使用静态数组来保存列信息。 如果使用者不希望使用 "书签" 列，则不会使用数组中的一个条目。 若要处理该信息，需要创建两个数组宏： ADD_COLUMN_ENTRY 和 ADD_COLUMN_ENTRY_EX。 ADD_COLUMN_ENTRY_EX 需要额外的参数 *标志*，如果指定书签列，则需要此参数。

```cpp
////////////////////////////////////////////////////////////////////////  
// CustomRS.h  
  
#define ADD_COLUMN_ENTRY(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = 0; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member);  
  
#define ADD_COLUMN_ENTRY_EX(ulCols, name, ordinal, colSize, type, precision, scale, guid, dataClass, member, flags) \  
   _rgColumns[ulCols].pwszName = (LPOLESTR)name; \  
   _rgColumns[ulCols].pTypeInfo = (ITypeInfo*)NULL; \  
   _rgColumns[ulCols].iOrdinal = (ULONG)ordinal; \  
   _rgColumns[ulCols].dwFlags = flags; \  
   _rgColumns[ulCols].ulColumnSize = (ULONG)colSize; \  
   _rgColumns[ulCols].wType = (DBTYPE)type; \  
   _rgColumns[ulCols].bPrecision = (BYTE)precision; \  
   _rgColumns[ulCols].bScale = (BYTE)scale; \  
   _rgColumns[ulCols].cbOffset = offsetof(dataClass, member); \  
   memset(&(_rgColumns[ulCols].columnid), 0, sizeof(DBID)); \  
   _rgColumns[ulCols].columnid.uName.pwszName = (LPOLESTR)name;  
```

在 `GetColumnInfo` 函数中，使用书签宏，如下所示：

```cpp
ADD_COLUMN_ENTRY_EX(ulCols, OLESTR("Bookmark"), 0, sizeof(DWORD),
   DBTYPE_BYTES, 0, 0, GUID_NULL, CAgentMan, dwBookmark,
   DBCOLUMNFLAGS_ISBOOKMARK)
```

你现在可以编译和运行增强的提供程序。 若要测试提供程序，请根据 [实现简单使用者](../../data/oledb/implementing-a-simple-consumer.md)中所述修改测试使用者。 使用提供程序运行测试使用者，并验证测试使用者是否从提供程序中检索正确的字符串。

## <a name="see-also"></a>请参阅

[增强简单的 Read-Only 提供程序](../../data/oledb/enhancing-the-simple-read-only-provider.md)<br/>
