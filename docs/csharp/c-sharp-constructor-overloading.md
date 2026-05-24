# C# |构造函数重载

> 原文:[https://www . geesforgeks . org/c-sharp-constructor-overloading/](https://www.geeksforgeeks.org/c-sharp-constructor-overloading/)

#### 先决条件:[c# 中的构造函数](https://www.geeksforgeeks.org/c-sharp-constructors/)

与 **[法重载](https://www.geeksforgeeks.org/c-method-overloading/)** 颇为相似。它能够以多种形式重新定义构造函数。用户可以通过在一个类中定义两个或多个同名的构造函数来实现构造函数重载。C# 可以区分不同签名的构造函数。即构造函数必须具有相同的名称，但是具有不同的参数列表。

我们可以通过如下不同的方式控制构造函数:

*   通过使用不同类型的参数
*   通过使用不同的**参数数量**
*   通过使用不同的**参数顺序**

#### 通过更改参数的数据类型

**示例:**

```cs
public ADD (int a, float b);
public ADD (string a, int b);

```

这里类的名字是 **ADD** 。第一个构造函数有两个参数，第一个是 **int** 另一个是 **float** ，第二个构造函数也有两个参数，第一个是 **string** 类型，另一个是 **int** 类型。
这里的构造函数名称相同，但参数类型不同，类似于方法重载的概念。

```cs
// C# program to Demonstrate the overloading of 
// constructor when the types of arguments 
// are different
using System;

class ADD {

    int x, y;
    double f;
    string s;

    // 1st constructor
    public ADD(int a, double b)
    {
        x = a;
        f = b;
    }

    // 2nd constructor
    public ADD(int a, string b)
    {
        y = a;
        s = b;
    }

    // showing 1st constructor's result
    public void show()
    {
        Console.WriteLine("1st constructor (int + float): {0} ",
                                                       (x + f));
    }

    // shows 2nd constructor's result
    public void show1()
    {
        Console.WriteLine("2nd constructor (int + string): {0}", 
                                                       (s + y));
    }
}

// Driver Class
class GFG {

    // Main Method
    static void Main()
    {

        // Creating instance and
        // passing arguments
        // It will call the first constructor
        ADD g = new ADD(10, 20.2);

        // calling the method
        g.show();

        // Creating instance and 
        // passing arguments
        // It will call the second constructor
        ADD q = new ADD(10, "Roll No. is ");

        // calling the method
        q.show1();
    }
}
```

**Output:**

```cs
1st constructor (int + float): 30.2 
2nd constructor (int + string): Roll No. is 10

```