---
description: 了解详细信息：将字符串读入 OLE DB 提供程序
title: 将字符串读入 OLE DB 提供程序
ms.date: 10/13/2018
helpviewer_keywords:
- OLE DB providers, reading strings into
ms.assetid: 517f322c-f37e-4eed-bf5e-dd9a412c2f98
ms.openlocfilehash: 5df8812d5589dd457684bf5e36a8a49f798f99aa
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286626"
---
# <a name="reading-strings-into-the-ole-db-provider"></a>将字符串读入 OLE DB 提供程序

`CCustomRowset::Execute`函数将打开文件并读取字符串。 使用者通过调用 [ICommandText：： SetCommandText](/previous-versions/windows/desktop/ms709757(v=vs.85))将文件名传递给提供程序。 提供程序接收文件名，并将其存储在成员变量中 `m_strCommandText` 。 `Execute` 从中读取文件名 `m_strCommandText` 。 如果文件名无效或该文件不可用，将 `Execute` 返回错误。 否则，它将打开文件并调用 `fgets` 来检索字符串。 对于它所读取的每个字符串集，将 `Execute` 创建用户记录 (从在 `CCustomWindowsFile` [OLE DB 提供程序中存储字符串](../../data/oledb/storing-strings-in-the-ole-db-provider.md) 而修改的实例) 并将其放入数组中。

如果文件无法打开，则 `Execute` 必须返回 DB_E_NOTABLE。 如果它返回 E_FAIL，则提供程序将不能与许多使用者一起使用，并且不会传递 OLE DB 的 [一致性测试](../../data/oledb/testing-your-provider.md)。

## <a name="example"></a>示例

```cpp
/////////////////////////////////////////////////////////////////////////
// CustomRS.h
class CCustomRowset : public CRowsetImpl< CCustomRowset, CCustomWindowsFile, CCustomCommand>
{
public:
    HRESULT Execute(DBPARAMS * pParams, LONG* pcRowsAffected)
    {
        enum {
            sizeOfBuffer = 256,
            sizeOfFile = MAX_PATH
        };
        USES_CONVERSION;
        FILE* pFile = NULL;
        TCHAR szString[sizeOfBuffer];
        TCHAR szFile[sizeOfFile];
        size_t nLength;

        ObjectLock lock(this);

        // From a filename, passed in as a command text, scan the file
        // placing data in the data array.
        if (!m_strCommandText)
        {
            ATLTRACE("No filename specified");
            return E_FAIL;
        }

        // Open the file
        _tcscpy_s(szFile, sizeOfFile, m_strCommandText);
        if (szFile[0] == _T('\0') ||
            (fopen_s(&pFile, (char*)&szFile[0], "r") == 0))
        {
            ATLTRACE("Could not open file");
            return DB_E_NOTABLE;
        }

        // Scan and parse the file.
        // The file should contain two strings per record
        LONG cFiles = 0;
        while (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
        {
            nLength = strnlen((char*)szString, sizeOfBuffer);
            szString[nLength-1] = '\0';   // Strip off trailing CR/LF
            CCustomWindowsFile am;
            _tcscpy_s(am.szCommand, am.iSize, szString);
            _tcscpy_s(am.szCommand2, am.iSize, szString);

            if (fgets((char*)szString, sizeOfBuffer, pFile) != NULL)
            {
                nLength = strnlen((char*)szString, sizeOfBuffer);
                szString[nLength-1] = '\0'; // Strip off trailing CR/LF
                _tcscpy_s(am.szText, am.iSize, szString);
                _tcscpy_s(am.szText2, am.iSize, szString);
            }

            am.dwBookmark = ++cFiles;
            if (!m_rgRowData.Add(am))
            {
                ATLTRACE("Couldn't add data to array");
                fclose(pFile);
                return E_FAIL;
            }
        }

        if (pcRowsAffected != NULL)
            *pcRowsAffected = cFiles;
        return S_OK;
    }
};
```

完成此操作后，提供程序应已准备好进行编译和运行。 若要测试提供程序，需要具有匹配功能的使用者。 [实现简单使用者](../../data/oledb/implementing-a-simple-consumer.md) 演示如何创建此类测试使用者。 使用提供程序运行测试使用者，并验证测试使用者是否从提供程序中检索正确的字符串。

成功测试了提供程序后，可能需要通过实现其他接口来增强其功能。 [增强简单的 Read-Only 提供程序](../../data/oledb/enhancing-the-simple-read-only-provider.md)中显示了一个示例。

## <a name="see-also"></a>请参阅

[实现简单的 Read-Only 提供程序](../../data/oledb/implementing-the-simple-read-only-provider.md)<br/>
