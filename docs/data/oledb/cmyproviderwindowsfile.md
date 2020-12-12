---
description: 了解详细信息： CCustomWindowsFile
title: CCustomWindowsFile
ms.date: 10/22/2018
f1_keywords:
- cmyproviderwindowsfile
- ccustomwindowsfile
helpviewer_keywords:
- CMyProviderWindowsFile class
- OLE DB providers, wizard-generated files
- CCustomWindowsFile class
ms.assetid: 0e9e72ac-1e1e-445f-a7ac-690c20031f9d
ms.openlocfilehash: c0df2840b68a350f9d65102fdf0a962681edefd9
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97170394"
---
# <a name="ccustomwindowsfile"></a>CCustomWindowsFile

向导将创建一个具有一行数据的类;在这种情况下，将调用此方法 `CCustomWindowsFile` 。 以下针对 `CCustomWindowsFile` is 向导生成的代码，并使用结构列出目录中的所有文件 `WIN32_FIND_DATA` 。 `CCustomWindowsFile` 继承自 `WIN32_FIND_DATA` 结构：

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H

class CCustomWindowsFile:
   public WIN32_FIND_DATA
{
public:
BEGIN_PROVIDER_COLUMN_MAP(CCustomWindowsFile)
   PROVIDER_COLUMN_ENTRY("FileAttributes", 1, dwFileAttributes)
   PROVIDER_COLUMN_ENTRY("FileSizeHigh", 2, nFileSizeHigh)
   PROVIDER_COLUMN_ENTRY("FileSizeLow", 3, nFileSizeLow)
   PROVIDER_COLUMN_ENTRY_STR("FileName", 4, cFileName)
   PROVIDER_COLUMN_ENTRY_STR("AltFileName", 5, cAlternateFileName)
END_PROVIDER_COLUMN_MAP()
};
```

`CCustomWindowsFile` 称为 [用户记录类](../../data/oledb/user-record.md) ，因为它还具有描述提供程序的行集中的列的映射。 对于使用 PROVIDER_COLUMN_ENTRY 宏的行集中的每个字段，提供程序列映射包含一个条目。 宏指定结构条目的列名称、序号和偏移量。 以上代码中的 provider 列项包含结构中的偏移量 `WIN32_FIND_DATA` 。 当使用者调用时 `IRowset::GetData` ，数据将在一个连续的缓冲区中传输。 您可以使用地图来指定数据成员，而不是让您执行指针算法。

`CCustomRowset`类还包含 `Execute` 方法。 `Execute` 是指从本机源中读取数据的实际内容。 下面的代码显示向导生成的 `Execute` 方法。 函数使用 Win32 `FindFirstFile` 和 `FindNextFile` api 检索有关目录中的文件的信息，并将这些文件放在类的实例中 `CCustomWindowsFile` 。

```cpp
/////////////////////////////////////////////////////////////////////
// CustomRS.H

HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)
{
   USES_CONVERSION;
   BOOL bFound = FALSE;
   HANDLE hFile;
   LPTSTR  szDir = (m_strCommandText == _T("")) ? _T("*.*") :
       OLE2T(m_strCommandText);
   CCustomWindowsFile wf;
   hFile = FindFirstFile(szDir, &wf);
   if (hFile == INVALID_HANDLE_VALUE)
      return DB_E_ERRORSINCOMMAND;
   LONG cFiles = 1;
   BOOL bMoreFiles = TRUE;
   while (bMoreFiles)
   {
      if (!m_rgRowData.Add(wf))
         return E_OUTOFMEMORY;
      bMoreFiles = FindNextFile(hFile, &wf);
      cFiles++;
   }
   FindClose(hFile);
   if (pcRowsAffected != NULL)
      *pcRowsAffected = cFiles;
   return S_OK;
}
```

要搜索的目录由显示， `m_strCommandText` 其中包含 `ICommandText` 命令对象中的接口表示的文本。 如果未指定目录，则使用当前目录。

方法为对应于行) 的每个 (文件创建一个条目，并将其放在 `m_rgRowData` 数据成员中。 `CRowsetImpl`类定义 `m_rgRowData` 数据成员。 此数组中的数据显示整个表，并在整个模板中使用。

## <a name="see-also"></a>请参阅

[提供程序 Wizard-Generated 文件](../../data/oledb/provider-wizard-generated-files.md)<br/>
