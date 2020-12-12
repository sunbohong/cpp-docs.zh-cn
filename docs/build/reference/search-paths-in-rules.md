---
description: 了解详细信息：规则中的搜索路径
title: 规则中的搜索路径
ms.date: 11/04/2016
helpviewer_keywords:
- search paths in NMAKE inference rules
- inference rules in NMAKE
- rules, inference
ms.assetid: 38feded6-536d-425d-bf40-fff3173a5506
ms.openlocfilehash: bf070fc57907b68eb458b8a5276698282ef30f9d
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97224876"
---
# <a name="search-paths-in-rules"></a>规则中的搜索路径

```
{frompath}.fromext{topath}.toext:
   commands
```

## <a name="remarks"></a>备注

只有在依赖项中指定的路径与推理规则路径完全匹配时，推理规则才适用于依赖项。 在 *topath* 中指定依赖项的 *frompath* 和目标的目录;不允许使用空格。 为每个扩展名仅指定一个路径。 一个扩展上的路径需要另一个上的路径。 若要指定当前目录，请使用句点 (. ) 或空大括号 ( {} ) 。 宏可以表示 *frompath* 和 *topath*;它们是在预处理过程中调用的。

## <a name="example"></a>示例

### <a name="code"></a>代码

```
{dbi\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUDBI) $<

{ilstore\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{misc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{misc\}.c{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{msf\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<

{bsc\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{mre\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{namesrvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $(YUPDB) $<

{src\cvr\}.cpp{$(ODIR)}.obj::
        $(CC) $(CFLAGS) $<
```

## <a name="see-also"></a>请参阅

[定义规则](defining-a-rule.md)
