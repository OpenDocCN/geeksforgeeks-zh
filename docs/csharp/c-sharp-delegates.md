# C# |委托

> 原文:[https://www.geeksforgeeks.org/c-sharp-delegates/](https://www.geeksforgeeks.org/c-sharp-delegates/)

委托是一个引用方法的对象，或者你可以说它是一个引用类型变量，可以保存对方法的引用。C# 中的委托类似于 C/C++ 中的[函数指针。它提供了一种方法，告诉在事件被触发时调用哪个方法。
例如，如果你点击窗体(Windows 窗体应用程序)上的*按钮*，程序会调用一个特定的方法。简单地说，它是一种类型，表示对具有特定参数列表和返回类型的方法的引用，然后在需要时调用程序中的方法来执行。
**关于代表的要点:**](https://www.geeksforgeeks.org/function-pointer-in-c/) 

*   提供封装方法的好方法。
*   委托是系统命名空间中的库类。
*   这些是任何方法的类型安全指针。
*   委托主要用于实现回调方法和事件。
*   委托可以链接在一起，因为在一个事件上可以调用两个或多个方法。
*   它不关心它引用的对象的类。
*   委托也可以在“匿名方法”调用中使用。
*   匿名方法(C# 2.0)和 Lambda 表达式(C# 3.0)被编译成在某些上下文中的委托类型。有时，这些特性合在一起称为匿名函数。

#### 代表宣言

委托类型可以使用**委托**关键字来声明。一旦声明了委托，委托实例将引用并调用那些返回类型和参数列表与委托声明匹配的方法。
**语法:**

```cs
[modifier] delegate [return_type] [delegate_name] ([parameter_list]);
```

> *修饰符:*是定义委托访问的必需修饰符，可以选择使用。
> *委托:*是用于定义委托的关键字。
> *return_type:* 是委托将要调用的方法返回的值的类型。它可以是空的。方法必须与委托具有相同的返回类型。
> *delegate_name:* 是用户为委托定义的名称或标识符。
> *parameter_list:* 包含通过委托调用时方法所需的参数。

**例:**

```cs
// "public" is the modifier
// "int" is return type
// "GeeksForGeeks" is delegate name
// "(int G, int F, int G)" are the parameters
public delegate int GeeksForGeeks(int G, int F, int G);
```

**注意:**委托将只调用与其签名和返回类型一致的方法。方法可以是与类关联的静态方法，也可以是与对象关联的实例方法，这并不重要。

#### 委托的实例化和调用

声明委托后，借助 **new** 关键字创建委托对象。一旦委托被实例化，对该委托的方法调用就由该委托传递给该方法。由调用方传递给委托的参数被传递给方法，方法的返回值(如果有的话)由委托返回给调用方。这被称为调用委托。
**语法:**

```cs
[delegate_name]  [instance_name] = new [delegate_name](calling_method_name);
```

**例:**

```cs
GeeksForGeeks GFG = new GeeksForGeeks (Geeks);
       // here,
       // "GeeksForGeeks" is delegate name. 
       // "GFG" is instance_name
       // "Geeks" is the calling method.
```

下面的程序说明了委托的使用:

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the use of Delegates
using System;
namespace GeeksForGeeks {

// declare class "Geeks"
class Geeks {

// Declaring the delegates
// Here return type and parameter type should
// be same as the return type and parameter type
// of the two methods
// "addnum" and "subnum" are two delegate names
public delegate void addnum(int a, int b);
public delegate void subnum(int a, int b);

    // method "sum"
    public void sum(int a, int b)
    {
        Console.WriteLine("(100 + 40) = {0}", a + b);
    }

    // method "subtract"
    public void subtract(int a, int b)
    {
        Console.WriteLine("(100 - 60) = {0}", a - b);
    }

// Main Method
public static void Main(String []args)
{

    // creating object "obj" of class "Geeks"
    Geeks obj = new Geeks();

    // creating object of delegate, name as "del_obj1"
    // for method "sum" and "del_obj2" for method "subtract" &
    // pass the parameter as the two methods by class object "obj"
    // instantiating the delegates
    addnum del_obj1 = new addnum(obj.sum);
    subnum del_obj2 = new subnum(obj.subtract);

    // pass the values to the methods by delegate object
    del_obj1(100, 40);
    del_obj2(100, 60);

    // These can be written as using
    // "Invoke" method
    // del_obj1.Invoke(100, 40);
    // del_obj2.Invoke(100, 60);
}
}
}
```

**输出:**

```cs
(100 + 40) = 140
(100 - 60) = 40
```

**说明:**在上面的程序中，有两个代表 *addnum* 和 *subnum* 。我们正在创建极客类的对象 *obj* ，因为这两个方法( *addnum* 和 *subnum* )都是实例方法。所以他们需要一个对象来调用。如果方法是静态的，那么就不需要创建类的对象。

#### 代理的多播

委托的多播是普通委托的扩展(有时称为单次委托)。它帮助用户在一次调用中指向多个方法。
**属性:**

*   委托是组合在一起的，当您调用委托时，就会调用一个完整的方法列表。
*   所有方法都是按照先进先出的顺序调用的。
*   “+”或“+=”运算符用于将方法添加到委托中。
*   –'或'-= '运算符用于从委托列表中移除方法。

**注意:**记住，委托的多播应该有一个 Void 的返回类型，否则它会抛出一个运行时异常。此外，委托的多播将只返回多播中添加的最后一个方法的值。虽然，其他方法会成功执行。
下面的程序演示了委托多播的使用:

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// Multicasting of Delegates
using System;

class rectangle {

// declaring delegate
public delegate void rectDelegate(double height,
                                  double width);

    // "area" method
    public void area(double height, double width)
    {
        Console.WriteLine("Area is: {0}", (width * height));
    }

    // "perimeter" method
    public void perimeter(double height, double width)
    {
        Console.WriteLine("Perimeter is: {0} ", 2 * (width + height));
    }

// Main Method
public static void Main(String []args)
{

    // creating object of class
    // "rectangle", named as "rect"
    rectangle rect = new rectangle();

    // these two lines are normal calling
    // of that two methods
    // rect.area(6.3, 4.2);
    // rect.perimeter(6.3, 4.2);

    // creating delegate object, name as "rectdele"
    // and pass the method as parameter by
    // class object "rect"
    rectDelegate rectdele = new rectDelegate(rect.area);

    // also can be written as
    // rectDelegate rectdele = rect.area;

    // call 2nd method "perimeter"
    // Multicasting
    rectdele += rect.perimeter;

    // pass the values in two method
    // by using "Invoke" method
    rectdele.Invoke(6.3, 4.2);
    Console.WriteLine();

    // call the methods with
    // different values
    rectdele.Invoke(16.3, 10.3);
}
}
```

**输出:**

```cs
Area is: 26.46
Perimeter is: 21 

Area is: 167.89
Perimeter is: 53.2 
```