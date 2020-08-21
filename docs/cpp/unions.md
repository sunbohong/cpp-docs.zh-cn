---
title: union
description: 标准 c + + union class 类型和关键字的说明、其使用和限制。
ms.date: 08/18/2020
f1_keywords:
- union_cpp
helpviewer_keywords:
- class type [C++], union as
- union keyword [C++]
ms.assetid: 25c4e219-fcbb-4b7b-9b64-83f3252a92ca
no-loc:
- union
- struct
- enum
- class
- static
ms.openlocfilehash: a4dc07df5e7858dffe62478509ee1d8dc759ce96
ms.sourcegitcommit: f1752bf90b4f869633a859ace85439ca19e208b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "88722175"
---
# `union`

> [!NOTE]
> 在 c + + 17 和更高版本中， `std::variant` class 是的类型安全的替代项 union 。

**`union`** 是用户定义的类型，其中的所有成员共享相同的内存位置。 此定义意味着，在任何给定时间， union 都不能包含来自其成员列表的多个对象。 这也意味着无论有多少个成员 union ，它始终只使用足够的内存来存储最大的成员。

union当有大量对象和内存有限时，可以使用来保存内存。 但是， union 正确使用需要特别注意。 您需要负责确保您始终访问您所分配的同一成员。 如果任何成员类型具有非普通用户 struct 或，则必须编写额外的代码以显式设置 struct 并销毁该成员。 使用之前，请 union 考虑您尝试解决的问题是否可以通过使用基 class 类型和派生类型来更好地表示 class 。

## <a name="syntax"></a>语法

> **`union`***`tag`* <sub>opt</sub> **`{`** opt *`member-list`***`};`**

### <a name="parameters"></a>参数

*`tag`*<br/>
为提供的类型名称 union 。

*`member-list`*<br/>
union可以包含的成员。

## <a name="declare-a-no-locunion"></a>声明一个 union

使用关键字开始的声明 union **`union`** ，并将成员列表括在大括号中：

```cpp
// declaring_a_union.cpp
union RecordType    // Declare a simple union type
{
    char   ch;
    int    i;
    long   l;
    float  f;
    double d;
    int *int_ptr;
};

int main()
{
    RecordType t;
    t.i = 5; // t holds an int
    t.f = 7.25; // t now holds a float
}
```

## <a name="use-a-no-locunion"></a>使用 union

在前面的示例中，访问的任何代码都 union 需要知道哪个成员保存了数据。 此问题的最常见解决方案称为可*区分 union *。 它将 union 放在中 struct ，并包含一个 enum 成员，该成员指示当前存储在中的成员类型 union 。 下面的示例演示了基本模式：

```cpp
#include <queue>

using namespace std;

enum class WeatherDataType
{
    Temperature, Wind
};

struct TempData
{
    int StationId;
    time_t time;
    double current;
    double max;
    double min;
};

struct WindData
{
    int StationId;
    time_t time;
    int speed;
    short direction;
};

struct Input
{
    WeatherDataType type;
    union
    {
        TempData temp;
        WindData wind;
    };
};

// Functions that are specific to data types
void Process_Temp(TempData t) {}
void Process_Wind(WindData w) {}

void Initialize(std::queue<Input>& inputs)
{
    Input first;
    first.type = WeatherDataType::Temperature;
    first.temp = { 101, 1418855664, 91.8, 108.5, 67.2 };
    inputs.push(first);

    Input second;
    second.type = WeatherDataType::Wind;
    second.wind = { 204, 1418859354, 14, 27 };
    inputs.push(second);
}

int main(int argc, char* argv[])
{
    // Container for all the data records
    queue<Input> inputs;
    Initialize(inputs);
    while (!inputs.empty())
    {
        Input const i = inputs.front();
        switch (i.type)
        {
        case WeatherDataType::Temperature:
            Process_Temp(i.temp);
            break;
        case WeatherDataType::Wind:
            Process_Wind(i.wind);
            break;
        default:
            break;
        }
        inputs.pop();

    }
    return 0;
}
```

在前面的示例中， union 中的 `Input` struct 没有名称，因此称为 *匿名* union 。 其成员可以直接访问，就像它们是的成员一样 struct 。 有关如何使用匿名的详细信息 union ，请参阅[anonymous union ](#anonymous_unions)部分。

前面的示例演示了一个问题，还可以通过使用 class 从公共基派生的类型来解决该问题 class 。 您可以基于容器中每个对象的运行时类型对代码进行分支。 你的代码可能更易于维护和理解，但它也可能比使用更慢 union 。 此外，使用 union 可以存储不相关的类型。 union利用，可以在不更改变量本身类型的情况下动态更改存储值的类型 union 。 例如，可以创建的异类数组 `MyUnionType` ，其元素存储不同类型的不同值。

`Input`在示例中，可以轻松地滥用 struct 。 用户需要正确使用鉴别器来访问保存数据的成员。 您可以通过创建 union **`private`** 和提供特殊的访问功能来防止滥用，如下面的示例中所示。

## <a name="unrestricted-no-locunion-c11"></a>无限制 union (c + + 11) 

在 c + + 03 及更早版本中， union 可以包含 static 具有类型的非数据成员，前提是 class 该类型没有用户提供的 struct or、de struct or 或赋值运算符。 在 C++11 中，消除了这些限制。 如果在中包含此类成员 union ，则编译器会自动标记不是用户提供的任何特殊成员函数 **`deleted`** 。 如果 union 是 union 或内的匿名，则 class struct 或不是用户提供的任何特殊成员函数 class struct 都将标记为 **`deleted`** 。 下面的示例演示如何处理这种情况。 的成员之一 union 具有要求此特殊处理的成员：

```cpp
// for MyVariant
#include <crtdbg.h>
#include <new>
#include <utility>

// for sample objects and output
#include <string>
#include <vector>
#include <iostream>

using namespace std;

struct A
{
    A() = default;
    A(int i, const string& str) : num(i), name(str) {}

    int num;
    string name;
    //...
};

struct B
{
    B() = default;
    B(int i, const string& str) : num(i), name(str) {}

    int num;
    string name;
    vector<int> vec;
    // ...
};

enum class Kind { None, A, B, Integer };

#pragma warning (push)
#pragma warning(disable:4624)
class MyVariant
{
public:
    MyVariant()
        : kind_(Kind::None)
    {
    }

    MyVariant(Kind kind)
        : kind_(kind)
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            new (&a_) A();
            break;
        case Kind::B:
            new (&b_) B();
            break;
        case Kind::Integer:
            i_ = 0;
            break;
        default:
            _ASSERT(false);
            break;
        }
    }

    ~MyVariant()
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            a_.~A();
            break;
        case Kind::B:
            b_.~B();
            break;
        case Kind::Integer:
            break;
        default:
            _ASSERT(false);
            break;
        }
        kind_ = Kind::None;
    }

    MyVariant(const MyVariant& other)
        : kind_(other.kind_)
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            new (&a_) A(other.a_);
            break;
        case Kind::B:
            new (&b_) B(other.b_);
            break;
        case Kind::Integer:
            i_ = other.i_;
            break;
        default:
            _ASSERT(false);
            break;
        }
    }

    MyVariant(MyVariant&& other)
        : kind_(other.kind_)
    {
        switch (kind_)
        {
        case Kind::None:
            break;
        case Kind::A:
            new (&a_) A(move(other.a_));
            break;
        case Kind::B:
            new (&b_) B(move(other.b_));
            break;
        case Kind::Integer:
            i_ = other.i_;
            break;
        default:
            _ASSERT(false);
            break;
        }
        other.kind_ = Kind::None;
    }

    MyVariant& operator=(const MyVariant& other)
    {
        if (&other != this)
        {
            switch (other.kind_)
            {
            case Kind::None:
                this->~MyVariant();
                break;
            case Kind::A:
                *this = other.a_;
                break;
            case Kind::B:
                *this = other.b_;
                break;
            case Kind::Integer:
                *this = other.i_;
                break;
            default:
                _ASSERT(false);
                break;
            }
        }
        return *this;
    }

    MyVariant& operator=(MyVariant&& other)
    {
        _ASSERT(this != &other);
        switch (other.kind_)
        {
        case Kind::None:
            this->~MyVariant();
            break;
        case Kind::A:
            *this = move(other.a_);
            break;
        case Kind::B:
            *this = move(other.b_);
            break;
        case Kind::Integer:
            *this = other.i_;
            break;
        default:
            _ASSERT(false);
            break;
        }
        other.kind_ = Kind::None;
        return *this;
    }

    MyVariant(const A& a)
        : kind_(Kind::A), a_(a)
    {
    }

    MyVariant(A&& a)
        : kind_(Kind::A), a_(move(a))
    {
    }

    MyVariant& operator=(const A& a)
    {
        if (kind_ != Kind::A)
        {
            this->~MyVariant();
            new (this) MyVariant(a);
        }
        else
        {
            a_ = a;
        }
        return *this;
    }

    MyVariant& operator=(A&& a)
    {
        if (kind_ != Kind::A)
        {
            this->~MyVariant();
            new (this) MyVariant(move(a));
        }
        else
        {
            a_ = move(a);
        }
        return *this;
    }

    MyVariant(const B& b)
        : kind_(Kind::B), b_(b)
    {
    }

    MyVariant(B&& b)
        : kind_(Kind::B), b_(move(b))
    {
    }

    MyVariant& operator=(const B& b)
    {
        if (kind_ != Kind::B)
        {
            this->~MyVariant();
            new (this) MyVariant(b);
        }
        else
        {
            b_ = b;
        }
        return *this;
    }

    MyVariant& operator=(B&& b)
    {
        if (kind_ != Kind::B)
        {
            this->~MyVariant();
            new (this) MyVariant(move(b));
        }
        else
        {
            b_ = move(b);
        }
        return *this;
    }

    MyVariant(int i)
        : kind_(Kind::Integer), i_(i)
    {
    }

    MyVariant& operator=(int i)
    {
        if (kind_ != Kind::Integer)
        {
            this->~MyVariant();
            new (this) MyVariant(i);
        }
        else
        {
            i_ = i;
        }
        return *this;
    }

    Kind GetKind() const
    {
        return kind_;
    }

    A& GetA()
    {
        _ASSERT(kind_ == Kind::A);
        return a_;
    }

    const A& GetA() const
    {
        _ASSERT(kind_ == Kind::A);
        return a_;
    }

    B& GetB()
    {
        _ASSERT(kind_ == Kind::B);
        return b_;
    }

    const B& GetB() const
    {
        _ASSERT(kind_ == Kind::B);
        return b_;
    }

    int& GetInteger()
    {
        _ASSERT(kind_ == Kind::Integer);
        return i_;
    }

    const int& GetInteger() const
    {
        _ASSERT(kind_ == Kind::Integer);
        return i_;
    }

private:
    Kind kind_;
    union
    {
        A a_;
        B b_;
        int i_;
    };
};
#pragma warning (pop)

int main()
{
    A a(1, "Hello from A");
    B b(2, "Hello from B");

    MyVariant mv_1 = a;

    cout << "mv_1 = a: " << mv_1.GetA().name << endl;
    mv_1 = b;
    cout << "mv_1 = b: " << mv_1.GetB().name << endl;
    mv_1 = A(3, "hello again from A");
    cout << R"aaa(mv_1 = A(3, "hello again from A"): )aaa" << mv_1.GetA().name << endl;
    mv_1 = 42;
    cout << "mv_1 = 42: " << mv_1.GetInteger() << endl;

    b.vec = { 10,20,30,40,50 };

    mv_1 = move(b);
    cout << "After move, mv_1 = b: vec.size = " << mv_1.GetB().vec.size() << endl;

    cout << endl << "Press a letter" << endl;
    char c;
    cin >> c;
}
```

union无法存储引用。 union也不支持继承。 这意味着不能使用 union 作为基 class ，也不能从另一个中继承，也不能 class 具有虚函数。

## <a name="initialize-a-no-locunion"></a>初始化 union

可以 union 通过分配括在大括号中的表达式，在同一语句中声明和初始化。 计算表达式并将其分配给的第一个字段 union 。

```cpp
#include <iostream>
using namespace std;

union NumericType
{
    short       iValue;
    long        lValue;
    double      dValue;
};

int main()
{
    union NumericType Values = { 10 };   // iValue = 10
    cout << Values.iValue << endl;
    Values.dValue = 3.1416;
    cout << Values.dValue << endl;
}
/* Output:
10
3.141600
*/
```

`NumericType` union (在概念上按) 排列，如下图所示。

![数据在数值类型中的存储：：：非 loc (联合) ：：：](../cpp/media/vc38ul1.png "将数据存储在 NumericType：：： no (联合) ：：：") <br/>
数据存储在 `NumericType`union

## <a name="anonymous-no-locunion"></a><a name="anonymous_unions"></a> 匿名 union

匿名 union 是在没有或的情况下声明的 *`class-name`* *`declarator-list`* 。

> **`union  {`**  *`member-list`*  **`}`**

直接使用在匿名中声明的名称 union ，就像非成员变量一样。 这意味着，匿名中声明的名称在 union 周围范围内必须是唯一的。

匿名 union 受以下其他限制的约束：

- 如果在文件或命名空间范围中声明，则还必须将其声明为 **`static`** 。

- 它只能具有 **`public`** 成员; 匿名拥有 **`private`** 和 **`protected`** 中的成员会 union 生成错误。

- 它不能包含成员函数。

## <a name="see-also"></a>请参阅

[类和结构](../cpp/classes-and-structs-cpp.md)<br/>
[关键字](../cpp/keywords-cpp.md)<br/>
[`class`](../cpp/class-cpp.md)<br/>
[`struct`](../cpp/struct-cpp.md)
