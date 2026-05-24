# C# |是运算符关键字

> 原文:[https://www.geeksforgeeks.org/c-sharp-is-operator-keyword/](https://www.geeksforgeeks.org/c-sharp-is-operator-keyword/)

在软件开发中，类型转换是一件不可避免的事情。在许多情况下，需要将一个对象(类型)转换成另一个对象(类型)，有时会得到 *InvalidCastException* 。所以，要克服这类异常 C# 提供的**就是**运算符。
是运算符，用于检查对象的运行时类型是否与给定类型兼容。如果给定对象是同一类型，则返回*真*，否则返回*假*。对于*空*对象，也返回*假*。
**语法:**

```cs
expression is type
```

这里，*表达式*将被评估为某种类型的实例。而*类型*是类型的名称，表示*表达式*的结果将被转换。如果*表达式*不为空，并且通过评估*表达式*得到的对象可以转换为指定的*类型*，则 is 运算符将返回 *true* ，否则将返回 *false* 。
**示例 1:** 在下面的代码中，我们有三个类，即作者、作品和 GFG。 *GFG* 是包含 Main 方法的驱动类。类“作者”和“作品”有数据成员和方法。在 Main 方法中，创建类*作者*和*工作*的对象，并使用类的实例调用这些类的方法。之后，一个 bool 值 *bool 结果；*用来存储*的返回值是*运算符。代码行即*结果= a 是作者；*用于检查一个(类作者的对象)是否为作者类型。它将返回真，因为 *a* 是作者类的实例。但是实例 *w* 不是作者类型，这就是它返回 false 的原因。之后，我们将*空值*赋给对象 *a* ，与作者的实例相比，这将给出错误的结果。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// use of 'is' operator keyword
using System;

class Author {

    // data members
    public string name;
    public int rank;

    // method of Author class
    public void details(string n, int r)
    {
        name = n;
        rank = r;
    }
}

class Work {

    // data members
    public int articl_no;
    public int improv_no;

    // method of Work class
    public void totalno(int a, int i)
    {
        articl_no = a;
        improv_no = i;
    }
}

// Driver Class
public class GFG {

    // Main method
    static public void Main()
    {

        // Creating objects of
        // Author and Work class
        Author a = new Author();

        a.details("Ankita", 5);

        Work w = new Work();

        w.totalno(80, 50);

        bool result;

        // Check 'a' is of Author
        // type or not
        // Using is operator
        result = a is Author;
        Console.WriteLine("Is a is Author? : {0}", result);

        // Check w is of Author type
        // using is operator
        result = w is Author;
        Console.WriteLine("Is w is Author? : {0}", result);

        // Take the value of a is null
        a = null;

        // Check null object
        // Using is operator
        result = a is Author;
        Console.WriteLine("Is a is Author? : {0}", result);
    }
}
```

**输出:**

```cs
Is a is Author? : True
Is w is Author? : False
Is a is Author? : False
```

**例 2:** 在下面的程序中，我们正在检查派生类型是否是*左侧的表达式类型是*运算符。如果是派生的，那么它将返回 true，否则返回 false。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate the
// use of is operator keyword
using System;

// taking a class
public class G1 {

}

// taking a class
// derived from G1
public class G2 : G1 {

}

// taking a class
public class G3 {

}

// Driver Class
public class GFG {

    // Main Method
    public static void Main()
    {
        // creating an instance
        // of class G1
        G1 obj1 = new G1();

        // creating an instance
        // of class G2
        G2 obj2 = new G2();

        // checking whether 'obj1'
        // is of type 'G1'
        Console.WriteLine(obj1 is G1);

        // checking whether 'obj1' is
        // of type Object class
        // (Base class for all classes)
        Console.WriteLine(obj1 is Object);

        // checking whether 'obj2'
        // is of type 'G2'
        Console.WriteLine(obj2 is G2);

        // checking whether 'obj2' is
        // of type Object class
        // (Base class for all classes)
        Console.WriteLine(obj2 is Object);

        // checking whether 'obj2'
        // is of type 'G1'
        // it will return true as G2
        // is derived from G1
        Console.WriteLine(obj2 is G1);

        // checking whether obj1
        // is of type G3
        // it will return false
        Console.WriteLine(obj1 is G3);

         // checking whether obj2
        // is of type G3
        // it will return false
        Console.WriteLine(obj2 is G3);

    }
}
```

**输出:**

```cs
True
True
True
True
True
False
False
```

**注:**

*   *只考虑引用、装箱和取消装箱转换，是*运算符关键字。
*   用户定义的转换或使用*隐式*和*显式*定义的转换不被*视为*运算符。对于编译时已知的或由*隐式*运算符处理的转换， *is* 运算符将对此发出警告。