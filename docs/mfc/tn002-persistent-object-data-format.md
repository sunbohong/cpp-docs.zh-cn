---
description: 了解详细信息： TN002：持久性对象数据格式
title: TN002：持久性对象数据格式
ms.date: 11/04/2016
helpviewer_keywords:
- VERSIONABLE_SCHEMA macro [MFC]
- persistent object data
- CArchive class [MFC], support for persistent data
- persistent C++ objects [MFC]
- TN002
ms.assetid: 553fe01d-c587-4c8d-a181-3244a15c2be9
ms.openlocfilehash: e99d54bd2624bffac4f5fea37c72bb7719e1e408
ms.sourcegitcommit: d6af41e42699628c3e2e6063ec7b03931a49a098
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "97216075"
---
# <a name="tn002-persistent-object-data-format"></a>TN002：持久性对象数据格式

此注释描述了在文件中存储对象数据时支持持久 c + + 对象和对象数据格式的 MFC 例程。 这仅适用于具有 [DECLARE_SERIAL](../mfc/reference/run-time-object-model-services.md#declare_serial) 和 [IMPLEMENT_SERIAL](../mfc/reference/run-time-object-model-services.md#implement_serial) 宏的类。

## <a name="the-problem"></a>问题

持久性数据的 MFC 实现将多个对象的数据存储在文件的单个连续部分。 对象的 `Serialize` 方法将对象的数据转换为简洁的二进制格式。

实现使用 [CArchive 类](../mfc/reference/carchive-class.md)确保所有数据都以相同格式保存。 它使用 `CArchive` 对象作为转换器。 在调用 [CArchive：： Close](../mfc/reference/carchive-class.md#close)之前，此对象会一直保留在创建它的时间。 此方法可由程序员显式调用，或在程序退出包含的作用域时由析构函数隐式调用 `CArchive` 。

此注释介绍 `CArchive` 成员 [CArchive：： ReadObject](../mfc/reference/carchive-class.md#readobject) 和 [CArchive：： WriteObject](../mfc/reference/carchive-class.md#writeobject)的实现。 你将在 Arcobj 中找到这些函数的代码，并在 Arccore 中找到的主要实现 `CArchive` 。 用户代码不会 `ReadObject` 直接调用和 `WriteObject` 。 相反，这些对象由 DECLARE_SERIAL 和 IMPLEMENT_SERIAL 宏自动生成的类特定类型安全的插入和提取运算符使用。 下面的代码演示如何 `WriteObject` `ReadObject` 隐式调用和：

```
class CMyObject : public CObject
{
    DECLARE_SERIAL(CMyObject)
};

IMPLEMENT_SERIAL(CMyObj, CObject, 1)

// example usage (ar is a CArchive&)
CMyObject* pObj;
CArchive& ar;
ar <<pObj;        // calls ar.WriteObject(pObj)
ar>> pObj;        // calls ar.ReadObject(RUNTIME_CLASS(CObj))
```

## <a name="saving-objects-to-the-store-carchivewriteobject"></a>将对象保存到存储区 (CArchive：： WriteObject) 

方法 `CArchive::WriteObject` 写入用于重新构造对象的标头数据。 此数据由两部分组成：对象的类型和对象的状态。 此方法还负责维护要写出的对象的标识，以便仅保存单个副本，而不考虑指向该对象的指针的数目 (包括) 循环指针。

保存 (插入) 和还原 (提取) 对象的情况取决于多个 "清单常量"。 这些值存储在二进制文件中，并为存档提供重要信息 (请注意，"w" 前缀表示16位) ：

|标记|描述|
|---------|-----------------|
|wNullTag|用于 NULL 对象指针 (0) 。|
|wNewClassTag|指示后面的类说明是此存档上下文 (-1) 的新内容。|
|wOldClassTag|指示已在此上下文中查看所读取对象的类 (0x8000) 。|

在存储对象时，存档维护 [CMapPtrToPtr](../mfc/reference/cmapptrtoptr-class.md) (*m_pStoreMap*) 是从存储对象到32位永久性标识符的映射 (PID) 。 PID 分配给每个唯一对象，以及保存在存档上下文中的每个唯一类名称。 这些 Pid 按顺序从1开始。 这些 Pid 在存档范围之外没有任何意义，特别是不会与记录号或其他标识项混淆。

在 `CArchive` 类中，pid 为32位，但它们写出为16位，除非它们大于0x7FFE。 大 Pid 编写为0x7FFF 后跟32位 PID。 这可保持与在早期版本中创建的项目的兼容性。

当请求将对象保存到存档 (通常使用全局插入运算符) 时，会对 NULL [CObject](../mfc/reference/cobject-class.md) 指针进行检查。 如果指针为 NULL，则会将 *wNullTag* 插入到存档流中。

如果指针不为 NULL，并且可以进行序列化 (类是 `DECLARE_SERIAL`) 类，则代码将检查 *m_pStoreMap* 以查看是否已保存对象。 如果已存在，则代码会将与该对象关联的32位 PID 插入到存档流中。

如果尚未保存对象，则可以考虑以下两种情况：无论对象和确切的类型 (都是，对象的类) 是此存档上下文的新的，或对象的类型已经存在。 若要确定是否已检测到该类型，代码将查询与[](../mfc/reference/cruntimeclass-structure.md) `CRuntimeClass` 要保存的对象关联的对象的 m_pStoreMap CRuntimeClass 对象。 如果存在匹配项，则 `WriteObject` 插入一个标记，该标记是 `OR` *wOldClassTag* 和此索引的比特率。 如果 `CRuntimeClass` 是此存档上下文的新的，则 `WriteObject` 向该类分配新的 PID，并将其插入到存档中，并在其前面加上 *wNewClassTag* 值。

然后，使用方法将此类的描述符插入到存档中 `CRuntimeClass::Store` 。 `CRuntimeClass::Store` 插入类的架构编号 (如下所示) 和类的 ASCII 文本名称。 请注意，使用 ASCII 文本名称并不保证跨应用程序进行存档的唯一性。 因此，您应该标记数据文件以防止损坏。 在插入类信息之后，存档会将对象放入 *m_pStoreMap* 中，然后调用 `Serialize` 方法来插入特定于类的数据。 在调用之前将对象置于 *m_pStoreMap* `Serialize` 会阻止将对象的多个副本保存到存储区。

如果返回初始调用方 (通常是对象) 的网络的根，则必须调用 [CArchive：： Close](../mfc/reference/carchive-class.md#close)。 如果你计划执行其他 [CFile](../mfc/reference/cfile-class.md)操作，则必须调用 `CArchive` 方法 [Flush](../mfc/reference/carchive-class.md#flush) 以防止存档损坏。

> [!NOTE]
> 此实现对每个存档上下文的0x3FFFFFFE 索引施加硬限制。 此数字表示可以保存在单个存档中的唯一对象和类的最大数目，但单个磁盘文件可以具有无限数量的存档上下文。

## <a name="loading-objects-from-the-store-carchivereadobject"></a>正在从存储区加载对象 (CArchive：： ReadObject) 

加载 (提取) 对象时， `CArchive::ReadObject` 会使用方法，并与相反 `WriteObject` 。 与一样 `WriteObject` ， `ReadObject` 不是由用户代码直接调用; 用户代码应调用与预期一起调用的类型安全提取运算符 `ReadObject` `CRuntimeClass` 。 这确保了提取操作的类型完整性。

由于 `WriteObject` 实现已分配增加 pid，从 1 (0 开始预定义为 NULL 对象) ，因此 `ReadObject` 实现可以使用数组来维护存档上下文的状态。 从存储中读取 PID 时，如果 PID 大于 *m_pLoadArray* 的当前上限，则 `ReadObject` 知道 (或类说明) 如下所示。

## <a name="schema-numbers"></a>架构编号

当遇到类的方法时，将分配给类的架构号 `IMPLEMENT_SERIAL` 是类实现的 "版本"。 架构指的是类的实现，而不是对给定对象被赋予持久的次数 (通常称为对象版本) 。

如果你打算在一段时间内维护同一个类的多个不同实现，则在你修改对象的方法实现时递增架构， `Serialize` 使你能够编写代码来加载通过使用较旧版本的实现存储的对象。

`CArchive::ReadObject`如果在持久性存储区中遇到不同于内存中类说明的架构号的架构号，则该方法将引发[CArchiveException](../mfc/reference/carchiveexception-class.md) 。 从此异常中恢复并不容易。

你可以 `VERSIONABLE_SCHEMA` 结合使用与 (按位 **or**) 架构版本，以防止引发此异常。 通过使用 `VERSIONABLE_SCHEMA` ，你的代码可以 `Serialize` 通过检查 [CArchive：： GetObjectSchema](../mfc/reference/carchive-class.md#getobjectschema)中的返回值，在其函数中采取适当的操作。

## <a name="calling-serialize-directly"></a>直接调用序列化

在许多情况下，和的常规对象存档方案的开销 `WriteObject` 并 `ReadObject` 不是必需的。 这是将数据序列化为 [CDocument](../mfc/reference/cdocument-class.md)的常见情况。 在这种情况下， `Serialize` `CDocument` 直接调用的方法，而不是提取或插入运算符。 文档内容可能会依次使用更常规的对象存档方案。

`Serialize`直接调用具有以下优点和缺点：

- 序列化对象之前或之后，不会向存档添加额外的字节。 这不仅会使保存的数据更小，而且允许实现 `Serialize` 可处理任何文件格式的例程。

- MFC 经过优化，因此 `WriteObject` 和 `ReadObject` 实现和相关集合将不会链接到你的应用程序，除非你需要更通用的对象存档方案用于其他目的。

- 你的代码不必从旧的架构编号恢复。 这会使文档序列化代码对架构号、文件格式版本号或在数据文件开头使用的任何识别号进行编码。

- 使用直接调用序列化的任何对象都 `Serialize` 不得使用 `CArchive::GetObjectSchema` 或必须处理 (UINT 的返回值，) -1，指示版本未知。

由于 `Serialize` 是直接在文档上调用的，因此文档的子对象通常不能将对其父文档的引用存档。 这些对象必须被明确地提供给其容器文档的指针，或者必须使用 [CArchive：： MapObject](../mfc/reference/carchive-class.md#mapobject) 函数在将 `CDocument` 这些后端指针存档之前将指针映射到 PID。

如前文所述，您应该在直接调用时自行编码版本和类信息 `Serialize` ，使您可以在以后更改格式，同时仍保持与旧文件的向后兼容性。 在 `CArchive::SerializeClass` 直接序列化对象之前或调用基类之前，可以显式调用函数。

## <a name="see-also"></a>请参阅

[按编号的技术说明](../mfc/technical-notes-by-number.md)<br/>
[按类别列出的技术说明](../mfc/technical-notes-by-category.md)
