# c# 中的对象和集合初始化器

> 原文:[https://www . geesforgeks . org/object-and-collection-initializer-in-c-sharp/](https://www.geeksforgeeks.org/object-and-collection-initializer-in-c-sharp/)

对象和集合初始值设定项是 C# 语言的一个有趣且非常有用的特性。此功能提供了一种不同的方法来初始化类或集合的对象。该功能在 *C# 3.0* 或以上版本中引入。使用这些的主要优点是使您的代码更易读，提供了一种在集合中添加元素的简单方法，并且主要用于多线程。

#### **c# 中的对象初始化器**

在对象初始化器中，您可以在创建对象时将值初始化为类的字段或属性，而无需调用[构造函数](https://www.geeksforgeeks.org/c-sharp-constructors/)。在此语法中，您可以创建一个对象，然后此语法使用其属性将新创建的对象初始化为赋值中的变量。它还可以放置索引器来初始化字段和属性，这个特性是在 C# 6.0 中引入的。
**示例:**在下面的示例中，Geeks 类不包含任何构造函数，我们只需在 main 方法中使用花括号创建对象并同时初始化值。这种值的初始化称为对象初始值设定项。

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate
// object initializer syntax
using System;

class Geeks {

    public string author_name
    {
        get;
        set;
    }
    public int author_id
    {
        get;
        set;
    }
    public int total_article
    {
        get;
        set;
    }
}

class GFG {

    // Main method
    static public void Main()
    {

        // Initialize fields using
        // an object initializer
        Geeks obj = new Geeks() {
            author_name = "Ankita Saini",
            author_id = 102,
            total_article = 178};

        Console.WriteLine("Author Name: {0}", obj.author_name);

        Console.WriteLine("Author Id: {0}", obj.author_id);

        Console.WriteLine("Total no of articles: {0}",
                                   obj.total_article);
    }
}
```

**Output:** 

```cs
Author Name: Ankita Saini
Author Id: 102
Total no of articles: 178
```

**注意:**当编译器编译上述程序时，它给对象赋值，如下所示:

```cs
Geeks __geeks = new Geeks();
__geeks.author_name = "Ankita Saini";
__geeks.author_id = 102;
__geeks. total_article = 178;

Geeks obj =  __geeks; 
```

#### C# 中的集合初始值设定项

集合初始值设定项也类似于对象初始值设定项。集合的初始化类似于使用对象初始化器初始化对象。或者换句话说，一般来说，我们使用 **Add()** 方法在集合中添加元素，但是使用集合初始值设定项，您可以在不使用 Add()方法的情况下添加元素。
T3】例:

## c sharp . c sharp . c sharp . c sharp

```cs
// C# program to illustrate how
// to create a SortedList using
// collection Initializer
using System;
using System.Collections;

class GFG {

    // Main Method
    static public void Main()
    {

        // Creating another SortedList
        // using  collection Initializer to
        // initialize sortedlist
        SortedList my_slist = new SortedList() {
                             { "b.09", 234 },
                             { "b.11", 395 },
                             { "b.01", 405 },
                             { "b.67", 100 },
                             { "b.55", 500 }};

        foreach(DictionaryEntry pair in my_slist)
        {
            Console.WriteLine("{0} and {1}", pair.Key, pair.Value);
        }
    }
}
```

**Output:** 

```cs
b.01 and 405
b.09 and 234
b.11 and 395
b.55 and 500
b.67 and 100
```

**要点:**

*   您可以同时初始化集合和对象。
    **例:**

## c sharp . c sharp . c sharp . c sharp

```cs
var author1 = new Geeks() { author_name = "Soniya",
                            author_id = 103,
                            total_article = 120 };

var author2 = new Geeks() { author_name = "Siya",
                            author_id = 106,
                            total_article = 90 };

var author3 = new Geeks() { author_name = "Arpita",
                            author_id = 111,
                            total_article = 130 };

List<Geeks> author = new List<Geeks>() {
                                author1,
                                author2,
                                author3
};
```

*   您也可以在集合初始值设定项中使用 null 作为元素。
    **例:**

## c sharp . c sharp . c sharp . c sharp

```cs
SortedList my_slist = new SortedList() {
                          { 1.2, "Cat" },
                          { 1.3, null },
                          { 1.5, 234 },};
```