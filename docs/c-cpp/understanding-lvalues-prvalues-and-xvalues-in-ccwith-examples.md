# 用例子理解 C/C++ 中的左值、右值和 Xvalues

> 原文:[https://www . geesforgeks . org/understanding-lvalues-pr values-and-xvalues-in-ccwith-examples/](https://www.geeksforgeeks.org/understanding-lvalues-prvalues-and-xvalues-in-ccwith-examples/)

[C 中的左值和右值](https://www.geeksforgeeks.org/lvalue-and-rvalue-in-c-language/)

**背景**

很多将要阅读这篇文章的人可能正在寻找关于什么是基本的澄清:*右值*是可以在赋值运算符右侧弹出的东西，*左值*是属于赋值运算符左侧或右侧的东西。毕竟，这就是 k & R 如何区分某些表达和其他表达:

> 对象是命名的存储区域；一个*左值*是指一个对象的表达式。*左值*表达式的一个明显例子是具有适当类型和存储类的标识符。有产生*左值*的运算符:例如，如果 E 是指针类型的表达式，那么*E 是引用 E 指向的对象的*左值*表达式。**名称“左值”来自赋值表达式 E1 = E2，其中左操作数 E1 必须是左值表达式**。每个运算符的讨论指定了它是否需要*左值*操作数，以及它是否产生一个*左值*。

不幸的是，这种简单的方法现在成了黑暗时代顽固的纪念品。当我们有足够的勇气查阅更近的规范时，3.10 节向我们展示了以下分类:

```cpp
             expression
          /       \
    glvalue       rvalue
       /      \      /      \
lvalue         xvalue        prvalue
```

在谷歌上搜索比规范本身更具可读性的说明，搜索结果会进入*左值引用*和*右值引用*之间的差异、*移动语义*的细微差别……所有这些事实上都是首先需要这种基本概念的混乱层次结构的高级特性。
好吧，这篇文章提供了一些完全不同的东西:它将试图让人们第一次看到这些术语时有一些意义，而不需要通过增强情绪的方法来度过这一切……我们甚至可以提供我们需要牢记在心的第一个建议:

**忘掉赋值运算符左右两边的赋值和东西。**

这个语义标签树中最大的挑战，就是神秘的 *xvalue* 。我们不必理解 *xvalues* ，那是为势利者准备的。我们只能理解*左值*和*前值*。如果你已经了解 *xvalues* ，你可以给你的金色“精英 C++ 程序员”牌匾快速擦亮，并寻找不同的文章来好好利用那些 *xvalues* 。对我们其他人来说，我们可以把这段话改写成第二条建议:

**重点理解各种表达式中的左值和右值。**

**Lvalue**

我们说的是表达式的语法和语义，赋值被巧妙地埋进了这类表达式的 BNF (Backus-Naur-Form)中。这就是为什么第二条建议建议忘记作业。因为规范对什么是*左值*还是很清楚的！但是，与其解读冗长的描述，不如让我们提供一些源代码示例:

```cpp
// Designates an object
int lv1;         

// Reference, designates an object       
int &lv2        {lv1}

// Pointer, designates an object   
int *lv3;               

// Function returning a reference, designates an object
int &lv4() {            
  return lv1;
}

```

差不多就是这样！好吧，我们可以弄清楚类是如何成为类型的，类实例也是对象，并从那里观察到实例和成员的引用和指针也是对象；然而，这正是那种用细节压倒我们的解释，以至于它掩盖了基础！此时，我们有一个典型的例子来说明*左值*的 4 种不同表现。规范没有规定任何关于它的限制，只属于赋值运算符的左侧或右侧！一个*左值*是一个最终在记忆中定位物体的表达式。

> 因此将*左值*描述为“**定位器-值**更加合适。

在这一点上，我们必须承认我们在初始化表达式中偷偷加入了一个*左值*:*lv1*不仅仅是声明它的语句中的*左值*！即使使用 *lv1* 来初始化 *lv2 引用*(一个引用应该被初始化，一直初始化) *lv1* 仍然是一个 *lvalue* ！
说明左值使用的最佳方式，是将其用作结果存储的定位器，以及数据输入的定位器；继续观察他们的行动:

## C++

```cpp
// CPP program to illustrate the concept of lvalue
#include <iostream>
using namespace std;

// §3.10.1
// An lvalue designates a function or an object
// An lvalue is an expression whose
// address can be taken:
// essentially a locator value
int lv1{ 42 }; // Object
int& lv2{ lv1 }; // Reveference to Object
int* lv3{ &lv1 }; // Pointer to Object

int& lv4()
{
    // Function returning Lvalue Reference
    return lv1;
}

int main()
{
    // Examine the lvalue expressions
    cout << lv1 << "\tObject" << endl;
    cout << lv2 << "\tReference" << endl;
    cout << lv3 << "\tPointer (object)" << endl;
    cout << *lv3 << "\tPointer (value=locator)" << endl;
    cout << lv4() << "\tFunction provided reference" << endl;

    // Use the lvalue as the target
    // of an assignment expression
    lv1 = 10;
    cout << lv4() << "\tAssignment to object locator" << endl;
    lv2 = 20;
    cout << lv4() << "\tAssignment to reference locator" << endl;
    *lv3 = 30;
    cout << lv4() << "\tAssignment to pointer locator" << endl;

    // Use the lvalue on the right hand side
    // of an assignment expression
    // Note that according to the specification,
    // those lvalues will first
    // be converted to prvalues! But
    // in the expression below, they are
    // still lvalues...
    lv4() = lv1 + lv2 + *lv3;
    cout << lv1 << "\tAssignment to reference locator (from function)\n"
                   "\t\tresult obtained from lvalues to the right of\n"
                   "\t\tassignment operator"
         << endl;

    return 0;
}
```

**Output:** 

```cpp
42    Object
42    Reference
0x602070    Pointer (object)
42    Pointer (value=locator)
42    Function provided reference
10    Assignment to object locator
20    Assignment to reference locator
30    Assignment to pointer locator
90    Assignment to reference locator (from function)
        result obtained from lvalues to the right of
        assignment operator
```

增值

我们暂时跳过更复杂的*值*。在前面提到的黑暗时代，它们是微不足道的。现在他们包括神秘的声音 *xvalues* ！我们想忽略那些 *xvalues* ，这正是 *prvalue* 的定义让我们做的:

**A*****prvalue*****是 A*****rvalue*****不是 A*****xvalue*****。**
还是少一点混淆:

> 一个*pr 值*代表一个**直接值**。

这在初始化器中最为明显:

```cpp
int prv1                {42};   // Value
```

然而，另一种选择是使用*左值*来初始化:

```cpp
constexpr int lv1       {42};
int prv2                {lv1};  // Lvalue
```

这里发生了什么！这本来很简单，一个*左值*怎么可能是一个*右值*？？？在规范中，3.10.2 有一句话是拯救:

> 每当 *glvalue* 出现在期望出现 *prvalue* 的上下文中时， *glvalue* 被转换为 *prvalue* 。

让我们忽略一个事实:一个 *glvalue* 只不过是一个 *lvalue* 或者一个 *xvalue* 。我们已经禁止了 *xvalues* 这个解释。因此:我们如何从 *lvalue rv2* 中获取一个值( *prvalue* )？通过转换(**评估**)它！

我们可以让它更有趣:

```cpp
constexpr int f1(int x} {
  return 6*x;
}
int prv3  {f1(7)};  // Function return value 
```

我们现在有一个函数 *f1()* ，它返回一个值。该规范确实规定了引入临时变量(*左值*)的情况，然后在需要时将其转换为*值*。假装这一切正在发生:

```cpp
int prv3 {t}; // Temporary variable t created by compiler
                   // . not declared by user),
                   // - initialized to value returned 
                   // by f1(7)
```

对于更复杂的表达式，也有类似的解释:

```cpp
int prv4 {(lv1+f1(7))/2};// Expression: temporary variable
                                    //  gets value of (lv1+f1(7))/2
```

小心点。*值*不是对象，也不是函数。最终使用的是*值*:

*   文字的值(与任何对象无关)。
*   函数返回的值(与任何对象无关，除非我们计算用于返回值的临时对象)。
*   临时对象的值是保存表达式计算结果所必需的。

对于通过执行编译器学习的人来说:

## C++

```cpp
// CPP program to illustrate glvalue
#include <iostream>
using namespace std;

// §3.10.1
// An rvalue is an xvalue, a temporary object (§12.2),
// or a value not associated with an object
// A prvalue is an rvalue that is NOT an xvalue

// When a glvalue appears in a context
// where a prvalue is expected,
// the glvalue is converted to a prvalue
int prv1{ 42 }; // Value

constexpr int lv1{ 42 };
int prv2{ lv1 }; // Expression (lvalue)

constexpr int f1(int x)
{
    return 6 * x;
}
int prv3{ f1(7) }; // Expression (function return value)

int prv4{ (lv1 + f1(7)) / 2 }; // Expression (temporary object)

int main()
{
    // Print out the prvalues used
    // in the initializations
    cout << prv1 << " Value" << endl;
    cout << prv2 << " Expression: lvalue" << endl;
    cout << prv3 << " Expression: function return value" << endl;
    cout << prv4 << " Expression: temporary object" << endl;

    return 0;
}
```

**Output:** 

```cpp
42 Value
42 Expression: lvalue
42 Expression: function return value
42 Expression: temporary object
```

**Xvalue**

等等:我们不是要讨论 *xvalues* 吗？！嗯，在这一点上，我们已经了解到*左值*和*右值*真的没有那么难。几乎是任何理智的人都会期待的。我们不想因为阅读了所有这些文本而失望，只是为了确认*左值*涉及一个可定位的对象， *prvalues* 指的是一些实际值。因此有了这个惊喜:我们不妨也涵盖一下 *xvalues* ，然后我们就完成并理解了它们！
不过，我们需要开始讲一点故事来达到目的…

**参考文献**
故事从说明书中的 8.5.3 开始；我们需要理解，C++ 现在区分了两种不同的*引用*:

```cpp
int&  // lvalue reference
int&&  // rvalue reference
```

它们的功能在语义上完全相同。然而他们是不同的类型！这意味着以下重载函数也是不同的:

```cpp
int f(int&);
int f(int&&);
```

如果不是规范中的这一句话，这将是愚蠢的，这是任何正常人都达不到的，深入到 8.5.3:

> 对类型“cv1 T1”的引用由类型“cv2 T2”的表达式初始化，如下所示:
> …
> **如果该引用是** ***右值*** **引用，则初始值设定项表达式不应是** ***左值*** **。**

查看将引用绑定到*左值*的简单尝试:

```cpp
int lv1         {42};
int& lvr        {lv1};    // Allowed
int&& rvr1      {lv1};   // Illegal
int&& rvr2      {static_cast<int&&>(lv1)};// Allowed
```

这种特殊的行为现在可以用于高级功能。如果你想多玩一点，这里有一个跳转开始:
(操纵第 33 行启用非法语句)。

## C++

```cpp
#include <iostream>
using namespace std;

// §8.3.2
// References are either form of:
// T& D         lvalue reference
// T&& D        rvalue reference
// They are distinct types (differentiating overloaded functions)

// §8.5.3
// The initializer of an rvalue reference shall not be an lvalue

// lvalue references
const int& lvr1{ 42 }; // value

int lv1{ 0 };
int& lvr2{ lv1 }; // lvalue (non-const)

constexpr int lv2{ 42 };
const int& lvr3{ lv2 }; // lvalue (const)

constexpr int f1(int x)
{
    return 6 * x;
}
const int& lvr4{ f1(7) }; // Function return value

const int& lvr5{ (lv1 + f1(7)) / 2 }; // expression

// rvalue references
const int&& rvr1{ 42 }; // value

// Enable next two statements to reveal compiler error
#if 0
int&& rvr2       {lv1}; // lvalue (non-const)
const int&& rvr3  {lv2}; // lvalue (const)
#else
int&& rvr2{ static_cast<int&&>(lv1) }; // rvalue (non-const)
const int&& rvr3{ static_cast<const int&&>(lv2) }; // rvalue (const)
#endif
const int&& rvr4{ f1(7) }; // Function return value
const int&& rvr5{ (lv1 + f1(7)) / 2 }; // expression

int main()
{
    lv1 = 42;
    // Print out the references
    cout << lvr1 << " Value" << endl;
    cout << lvr2 << " lvalue (non-const)" << endl;
    cout << lvr3 << " lvalue (const)" << endl;
    cout << lvr4 << " Function return value" << endl;
    cout << lvr5 << " Expression (temporary object)" << endl;

    cout << rvr1 << " Value" << endl;
    cout << rvr2 << " rvalue (const)" << endl;
    cout << rvr3 << " rvalue (non-const)" << endl;
    cout << rvr4 << " Function return value" << endl;
    cout << rvr5 << " Expression (temporary object)" << endl;

    return 0;
}
```

**Output:** 

```cpp
42 Value
42 lvalue (non-const)
42 lvalue (const)
42 Function return value
21 Expression (temporary object)
42 Value
42 rvalue (const)
42 rvalue (non-const)
42 Function return value
21 Expression (temporary object)
```

**移动语义**

故事的下一部分需要从规范中的 12.8 开始翻译。如果可以“移动”对象资源，可能会比复制对象更快(尤其是对于大型对象)。这与两种不同的情况有关:

1.  初始化(包括参数传递和值返回)。
2.  任务。

这些情况依赖于特殊的成员函数来完成工作:

```cpp
struct S {
  S(T t) : _t(t) {}  // Constructor
  S(const S &s); // Copy Constructor
  S& operator=(const S &s); // Copy Assignment Operator
  T* _t;
};

T t1;
S s1    {t1};    // Constructor with initialization
S s2    {s1};    // Constructor with copy
S s3;        // Constructor with defaults
s3 = s2;    // Copy assignment operator
```

在结构 S 的声明中，指向 T 的指针看起来是多么无辜啊！然而，对于大型、复杂的类型 T，对 member _t 内容的管理可能会涉及到深层拷贝，并且会真正降低性能。每次 struct S 的实例遍历一个函数的参数，一些表达式，然后潜在地从一个函数返回:我们花费更多的时间复制数据，而不是有效地使用它！
我们可以定义一些替代的特殊函数来处理这个问题。这些函数可以这样写，我们不复制信息，只是从其他对象那里窃取信息。只是我们不称之为偷窃，它涉及一个更为法律的术语:移动它。这些函数利用了不同类型的引用:

```cpp
S(const S &&s); // Move Constructor
S& operator=( S &&s); // Move Assignment Operator
```

请注意，当实际参数为*左值*时，我们保留了原始的构造函数和运算符。
但是，如果我们能够强制实际参数为*右值*，那么我们就可以执行这个新的构造函数或赋值运算符！将*左值*变为*右值*其实有几种方法；一种简单的方法是将*左值*静态转换为适当的类型:

```cpp
S s4 {static_cast<S&&>(s3)); // Calls move constructor
s2 = static_cast<S&&>(s4); // Calls move assignment operator 
```

通过指示参数“可用于移动数据”，可以以更全面的方式实现同样的效果:

```cpp
S s4 {std::move(s3)); // Calls move constructor
S2 = std::move(s4); // Calls move assignment operator 
```

最好的洞察力总是在行动中看到它:

## C++

```cpp
#include <iostream>
using namespace std;

// §12
// Special member functions
//  . §12.1     Constructor
//  . §12.8     Copy/Move
//    - §12/1   Copy/Move Constructor
//    - §13.5.3 Copy/Move Assignment Operator
struct T {
    int _v1;
    int _v2;
    int _v3;

    friend std::ostream& operator<<(std::ostream& os, const T& p)
    {
        return os << "[ " << p._v1 << " | " << p._v2 << " | " << p._v3 << " ]";
    }
};

struct S {
    S() // Constructor
    {
        cout << "Constructing instance of S" << endl;
        _t = new T{ 1, 2, 3 };
    }
    S(T& t) // Constructor
    {
        cout << "Initializing instance of S" << endl;
        _t = new T{ t };
    }

    S(const S& that) // Copy Constructor
    {
        cout << "Copying instance of S" << endl;
        _t = new T;
        *_t = *(that._t); // Deep copy
    }
    S& operator=(const S& that) // Copy Assignment Operator
    {
        cout << "Assigning instance of S" << endl;
        *_t = *(that._t); // Deep copy
        return *this;
    }

    S(S&& that) // Move Constructor
    {
        cout << "Moving instance of S" << endl;
        _t = that._t; // Move resources
        that._t = nullptr; // Reset source (protect)
    }
    S& operator=(S&& that) // Move Assignment Operator
    {
        cout << "Move-assigning instance of S" << endl;
        _t = that._t; // Move resources
        that._t = nullptr; // Reset source (protect)
        return *this;
    }

    T* _t;
};

int main()
{
    T t1{ 41, 42, 43 };
    cout << t1 << " Initializer" << endl;
    S s1{ t1 };
    cout << s1._t << " : " << *(s1._t) << " Initialized" << endl;

    S s2{ s1 };
    cout << s2._t << " : " << *(s2._t) << " Copy Constructed" << endl;

    S s3;
    cout << s3._t << " : " << *(s3._t) << " Default Constructed" << endl;
    s3 = s2;
    cout << s3._t << " : " << *(s3._t) << " Copy Assigned" << endl;

    S s4{ static_cast<S&&>(s3) };
    cout << s4._t << " : " << *(s4._t) << " Move Constructed" << endl;

    s2 = std::move(s4);
    cout << s2._t << " : " << *(s2._t) << " Move Assigned" << endl;

    return 0;
}
```

**Output:** 

```cpp
[ 41 | 42 | 43 ] Initializer
Initializing instance of S
0x1d13c30 : [ 41 | 42 | 43 ] Initialized
Copying instance of S
0x1d13c50 : [ 41 | 42 | 43 ] Copy Constructed
Constructing instance of S
0x1d13c70 : [ 1 | 2 | 3 ] Default Constructed
Assigning instance of S
0x1d13c70 : [ 41 | 42 | 43 ] Copy Assigned
Moving instance of S
0x1d13c70 : [ 41 | 42 | 43 ] Move Constructed
Move-assigning instance of S
0x1d13c70 : [ 41 | 42 | 43 ] Move Assigned
```

## 价值观念

我们的故事到此结束:

> *xvalues* 也称为**过期值**。

让我们看看上面例子的移动语义:

```cpp
  S(S &&that) // Move Constructor
  {
    cout << "Moving instance of S" << endl;
    _t = that._t;     // Move resources
    that._t = nullptr;  // Reset source (protect)
  }
  S& operator=(S &&that)  // Move Assignment Operator
  {
    cout << "Move-assigning instance of S" << endl;
    _t = that._t;      // Move resources
    that._t = nullptr;  // Reset source (protect)
    return *this;
  }
```

我们通过将资源从参数对象移动到当前对象来实现性能目标。但是请注意，在此之后我们也将使当前对象无效。这是因为我们不想意外地操纵实际的参数对象:任何变化都会波及到我们当前的对象，这与我们在面向对象编程中所追求的封装并不完全一样。
规范给出了表达式成为 xvalue 的几种可能性，但让我们记住这一点:

*   对对象的*右值引用*的强制转换…

### 摘要

<figure class="table">

| 左值(定位器值) | 指定一个对象，内存中的一个位置 |
| Prvalues(纯保留值) | 表示实际值 |
| Xvalues(过期值 | 一个接近其生命周期结束的对象(通常用于移动语义) |

</figure>