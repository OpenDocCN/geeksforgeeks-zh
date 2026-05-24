# 重载对继承有用吗？

> 原文:[https://www . geesforgeks . org/do-overload-work-with-inheritation/](https://www.geeksforgeeks.org/does-overloading-work-with-inheritance/)

如果我们在基类中有一个函数，在派生类中有一个同名的函数，基类函数可以从派生类对象中调用吗？这是一个有趣的问题，作为一个实验，预测以下 **C++** 程序的输出。

## C++

```cpp
#include <iostream>
using namespace std;
class Base
{
public:
    int f(int i)
    {
        cout << "f(int): ";
        return i+3;
    }
};
class Derived : public Base
{
public:
    double f(double d)
    {
        cout << "f(double): ";
        return d+3.3;
    }
};
int main()
{
    Derived* dp = new Derived;
    cout << dp->f(3) << '\n';
    cout << dp->f(3.3) << '\n';
    delete dp;
    return 0;
}
```

这个程序的输出是:

```cpp
f(double): 6.3
f(double): 6.6 
```

而不是假设的输出:

```cpp
f(int): 6
f(double): 6.6 
```

重载不适用于 C++ 编程语言中的派生类。基础和派生之间没有重载解析。编译器查看派生类的范围，找到单个函数“double f(double)”并调用它。它从不干扰基地的(封闭)范围。在 C++ 中，作用域之间没有重载——派生类作用域也不例外。(更多例子见[本](https://www.geeksforgeeks.org/g-fact-89/)

参考:[www.stroustrup.com 技术常见问题解答](http://www.stroustrup.com/bs_faq2.html#overloadderived)

现在考虑一下这个程序的 **Java** 版本:

## Java 语言(一种计算机语言，尤用于创建网站)

```cpp
class Base
{
    public int f(int i)
    {
        System.out.print("f (int): ");
        return i+3;
    }
}
class Derived extends Base
{
    public double f(double i)
    {
        System.out.print("f (double) : ");
        return i + 3.3;
    }
}
class myprogram3
{
    public static void main(String args[])
    {
        Derived obj = new Derived();
        System.out.println(obj.f(3));
        System.out.println(obj.f(3.3));
    }
}
```

上述程序的输出是:

```cpp
f (int): 6
f (double): 6.6 
```

所以在 Java 中，重载跨范围工作，这与 C++ 相反。Java 编译器根据用于调用方法的参数类型来确定编译时要执行的重载方法的正确版本，这两个类的重载方法的参数接收调用中使用的参数值并执行重载方法。

最后，让我们试试下面 **C#** 程序的输出:

## C#

```cpp
using System;                    
class Base
{
    public int f(int i)
    {
        Console.Write("f (int): ");
        return i + 3;
    }
}
class Derived : Base
{
    public double f(double i)
    {
        Console.Write("f (double) : ");
        return i+3.3;
    }
}
class MyProgram
{  
    static void Main(string[] args)
    {
        Derived obj = new Derived();
        Console.WriteLine(obj.f(3));
        Console.WriteLine(obj.f(3.3));
        Console.ReadKey(); // write this line if you use visual studio
    }
}
```

**注**:控制台。ReadKey()用于暂停控制台。它类似于 C/C++ 中的 getch。
上述程序的输出是:

```cpp
f(double) : 6.3
f(double):  6.6 
```

代替假设的输出

```cpp
f(int) : 6
f(double) : 6.6 
```

**解释:**这里，我们正在创建派生类的对象，因此编译器将首先优先考虑派生类，如果需要，将执行隐式类型转换。所以一旦编译器来到*控制台。write line(obj . f(3))；*这一行代码它会检查参数的兼容性。这里的 3 是 *int* ，兼容*派生类函数 f* 的*双*。所以编译器会执行 *int 到 double* 的隐式类型转换。于是输出 *f(双):6.3* 就来了。

现在当编译器进入*控制台时。write line(obj . f(3.3))；*同样，它会优先选择派生类，并发现它是可调用的。所以它将评估派生类函数 *f* 。于是输出 *f(双):6.6* 就来了。

现在让我们看另一个例子，我们将基类函数 f 放入派生类中，反之亦然，如下所示:

## C#

```cpp
using System;                    
class Base
{
    public double f(double i)
    {
        Console.Write("f (double) : ");
        return i+3.3;
    }
}

class Derived : Base
{

    public int f(int i)
    {
        Console.Write("f (int): ");
        return i + 3;
    }

}

class MyProgram
{
    static void Main(string[] args)
    {
        Derived obj = new Derived();
        Console.WriteLine(obj.f(3));
        Console.WriteLine(obj.f(3.3));
        Console.ReadKey(); // write this line if you use visual studio
    }
}
```

**输出:**

```cpp
f (int): 6
f (double) : 6.6
```

**看到预期产量，你是否感到震惊？怎么可能？**
好了，这些问题我们都有答案了。因为我们已经创建了派生类的对象，所以 C#编译器将首先优先考虑派生类，如果它没有找到任何兼容性，那么它将选择基类。所以当编译器来到*控制台时。write line(obj . f(3))；*一行代码，它将检查*派生类方法 f* ，并发现它是可调用的，因此执行它，并输出 *f (int): 6* 。现在当*控制台。write line(obj . f(3.3))；*一行代码将执行它会发现派生类方法不适合，因为 3.3(double)与 int 数据类型不兼容，因此编译器现在更喜欢基类，在那里它找到了最佳匹配，并执行那个。所以那个的输出将是 *f(双):6.6* 。

原因和 C++ 程序中解释的一样。像 C++ 一样，基类和派生类之间没有重载解析。在 C#中，没有跨作用域的重载，派生类作用域也不例外。这与 C++ 相同，因为根据 C#语言的创造者[Anders hejsberg](http://en.wikipedia.org/wiki/Anders_Hejlsberg)的说法，C#被设计得更接近 C++。

本文由 **Pravasi Meet** 供稿。如果你发现任何不正确的地方，请写评论，或者你想分享更多关于上面讨论的话题的信息