# C# |本关键词

> 原文:[https://www.geeksforgeeks.org/c-sharp-this-keyword/](https://www.geeksforgeeks.org/c-sharp-this-keyword/)

***这个*** 关键字是用来引用类的当前实例的。它用于从构造函数、实例方法和实例访问器中访问成员。*这个*关键字也用于跟踪实例，该实例被调用来执行与该实例相关的一些计算或进一步处理。以下是在 C# 中使用“this”关键字的不同方式:
**程序 1:** 使用“this”关键字引用当前类实例成员

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program for using 'this' keyword to
// refer current class instance members
using System;
namespace geeksforgeeks {

class Geeks {

    // instance member
    public string Name;

    public string GetName()
    {
        return Name;
    }

    public void SetName(string Name)
    {
         // referring to current instance
         //"this.Name" refers to class member
         this.Name = Name;
    }
}

class program {

    // Main Method
    public static void Main()
    {
        Geeks obj = new Geeks();
        obj.SetName("Geeksforgeeks");
        Console.WriteLine(obj.GetName());
    }
}
}
```

**Output:** 

```cs
Geeksforgeeks
```

**程序 2 :** 用这个()调用同一个类的构造函数

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program for using 'this' keyword to
// invoke the constructor in same class
using System;
namespace geeksforgeeks {

class Geeks {

    // calling another constructor
    // calls Geeks(string Name)
    // before Geeks()
    public Geeks() : this("geeks")
    {
        Console.WriteLine("Non-Parameter Constructor Called");
    }

    // Declare Parameter Constructor
    public Geeks(string Name)
    {
        Console.WriteLine("Parameter Constructor Called");
    }
}

class program {

    // Main Method
    public static void Main()
    {
            Geeks obj = new Geeks();
            // Warning: obj never used..
    }
}
}
```

**输出:**

```cs
Parameter Constructor Called
Non-Parameter Constructor Called
```

**程序 3:** 使用‘this’关键字调用当前类方法

## c sharp . c sharp . c sharp . c sharp

```cs
// C# code for using this to invoke current
// class method
using System;
class Test {

    void display()
    {
        // calling function show()
        this.show();

        Console.WriteLine("Inside display function");
    }

    void show()
    {
        Console.WriteLine("Inside show function");
    }

    // Main Method
    public static void Main(String []args)
    {
        Test t1 = new Test();
        t1.display();
    }
}
```

**Output**

```cs
Inside show function
Inside display function
```

**程序 4:** 使用‘this’关键字作为方法参数

## c sharp . c sharp . c sharp . c sharp

```cs
// C# code for using 'this'
// keyword as method parameter
using System;
class Test
{
    int a;
    int b;

    // Default constructor
    Test()
    {
        a = 10;
        b = 20;
    }

    // Method that receives 'this'
    // keyword as parameter
    void display(Test obj)
    {
        Console.WriteLine("a = " + a + " b = " + b);
    }

    // Method that returns current
    // class instance
    void get()
    {
        display(this);
    }

    // Main Method
    public static void Main(String[] args)
    {
        Test obj = new Test();
        obj.get();
    }
}
```

**Output:** 

```cs
a = 10 b = 20
```

**程序 5:** 使用此关键字声明索引器

## c sharp . c sharp . c sharp . c sharp

```cs
// C# code for using 'this'
// keyword to declare indexer
using System;
namespace geeksforgeeks {

class Geeks {

    private string[] days = new string[7];

    // declaring an indexer
    public string this[int index]
    {
        get
        {
            return days[index];
        }

        set
        {
            days[index] = value;
        }
    }
}

class Program {

    // Main Method
    public static void Main()
    {
        Geeks g = new Geeks();
        g[0] = "Sun";
        g[1] = "Mon";
        g[2] = "Tue";
        g[3] = "Wed";
        g[4] = "Thu";
        g[5] = "Fri";
        g[6] = "Sat";
        for (int i = 0; i < 7; i++)
            Console.Write(g[i] + " ");
    }
}
}
```

**Output:** 

```cs
Sun Mon Tue Wed Thu Fri Sat
```