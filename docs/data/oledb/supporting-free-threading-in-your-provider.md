---
description: 了解详细信息：在提供程序中支持自由线程处理
title: 在提供程序中支持自由线程处理
ms.date: 11/04/2016
helpviewer_keywords:
- OLE DB providers, multithreaded
- threading [C++], providers
ms.assetid: a91270dc-cdf9-4855-88e7-88a54be7cbe8
ms.openlocfilehash: 4f6785dd85ae043ce0ee74c1dda4fa365c566729
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97286470"
---
# <a name="supporting-free-threading-in-your-provider"></a>在提供程序中支持自由线程处理

所有 OLE DB 提供程序类都是线程安全的，并且会相应地设置注册表项。 最好是支持自由线程处理，以帮助在多用户情况下提供较高的性能级别。 若要帮助保持提供程序的线程安全，必须验证代码是否已正确阻止。 每当写入或存储数据时，都必须使用关键部分来阻止访问。

每个 OLE DB 提供程序模板对象都有其自己的关键部分。 为了更轻松地进行阻止，你创建的每个新类应该是一个模板类，它将父类名称作为参数。

下面的示例演示如何阻止你的代码：

```cpp
template <class T>
class CMyObject<T> : public...

HRESULT MyObject::MyMethod(void)
{
   T* pT = (T*)this;      // this gets the parent class

// You don't need to do anything if you are only reading information

// If you want to write information, do the following:
   pT->Lock();         // engages critical section in the object
   ...;                // write whatever information you wish
   pT->Unlock();       // disengages the critical section
}
```

有关如何使用和保护关键部分的详细信息 `Lock` `Unlock` ，请参阅 [多线程处理：如何使用同步类](../../parallel/multithreading-how-to-use-the-synchronization-classes.md)。

验证你重写的任何方法 (例如 `Execute`) 是否是线程安全的。

## <a name="see-also"></a>请参阅

[使用 OLE DB 提供程序模板](../../data/oledb/working-with-ole-db-provider-templates.md)
