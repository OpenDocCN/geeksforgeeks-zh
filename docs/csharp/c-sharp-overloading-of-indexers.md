# C# |索引器过载

> 原文:[https://www . geeksforgeeks . org/c-sharp-索引器过载/](https://www.geeksforgeeks.org/c-sharp-overloading-of-indexers/)

#### 先决条件:[c# 中的索引器](https://www.geeksforgeeks.org/c-indexers/)

像函数一样，索引器也可以重载。在 C# 中，我们可以在一个类中有多个索引器。若要重载索引器，请用多个参数声明它，并且每个参数都应有不同的数据类型。索引器通过传递两种不同类型的参数来重载。这与 [**方法重载**](https://www.geeksforgeeks.org/c-method-overloading/) 颇为相似。

**示例 1:** 在下面的程序中 ***int*** 和 ***float*** 类型用于重载索引器。这里，“ *Hello* ”这个词是使用 *int* 索引器分配的，而 float 参数是用来给字符串赋予值“ *Geeks* ”。

```cs
// C# Program to illustrate 
// the overloading of indexers
using System;

namespace HelloGeeksApp {

class HelloGeeks {

    // private array of 
    // strings with size 2
    private string[] word = new string[2];

    // this indexer gets executed
    // when Obj[0]gets executed
    public string this[int flag]
    {

        // using get accessor
        get
        {
            string temp = word[flag];
            return temp;
        }

        // using set accessor
        set
        {
            word[flag] = value;
        }
    }

    // this is an Overloaded indexer
    // which will execute when 
    // Obj[1.0f] gets executed
    public string this[float flag]
    {

        // using get accessor
        get
        {
            string temp = word[1];
            return temp;
        }

        // using set accessor
        set
        {

            // it will set value of 
            // the private string 
            // assigned in main
            word[1] = value;

        }
    }

// Main Method
static void Main(string[] args)
{
    HelloGeeks Obj = new HelloGeeks();

    Obj[0] = "Hello"; // Value of word[0]

    Obj[1.0f] = " Geeks"; // Value of word[1]

    Console.WriteLine(Obj[0] + Obj[1.0f]);
}
}
}
```

**输出:**

```cs
Hello Geeks

```

**示例 2:** 在下面的程序中，我们在启用只读模式的重载索引器中仅使用 get 访问器。意味着我们不能修改给定值。这里 ***int*** 和 ***string*** 类型用来重载索引器。*公共字符串此[字符串标志]* 仅包含启用只读模式的 get 访问器。

```cs
// C# program to illustrate the concept
// of indexer overloading by taking 
// only get accessor in overloaded indexer
using System;

namespace Geeks {

class G4G {

    // private array of 
    // strings with size 2
    private string[] str = new string[2];

    // this indexer gets called
    // when Obj[0] gets executed
    public string this[int flag]
    {
        // using get accessor
        get
        {
            string temp = str[flag];
            return temp;
        }

        // using set accessor
        set
        {
            str[flag] = value;
        }
    }

    // this indexer gets called
    // when Obj["GFG"] gets executed
    public string this[string flag]
    {

        // using get accessor
        get
        {
            return " C# Indexers Overloading."; // read only mode
        }
    }

// Driver Code    
static void Main(string[] args)
{
    G4G Obj = new G4G();

    Obj[0] = "This is"; // Value of str[0]

    Console.WriteLine(Obj[0] + Obj["GFG"]);
}
}
}
```

**输出:**

```cs
This is C# Indexers Overloading.

```

**注意:**索引器重载**不能通过仅仅改变 get 块的返回类型来完成**。