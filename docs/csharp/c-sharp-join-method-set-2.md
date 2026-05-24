# C# |连接方法|集合–2

> 原文:[https://www.geeksforgeeks.org/c-sharp-join-method-set-2/](https://www.geeksforgeeks.org/c-sharp-join-method-set-2/)

在 C# 中 ***Join()*** 是一个字符串方法。此方法用于连接集合的成员或指定数组的元素，在每个成员或元素之间使用指定的分隔符。这个方法可以通过传递不同的参数来重载。前三种方法请参考 C# Set -1 中的 **[Join()方法。](https://www.geeksforgeeks.org/c-join-method-set-1/)**

*   **[弦。连接(字符串，Obj [ ])](https://www.geeksforgeeks.org/c-join-method-set-1/)**
*   **[弦。连接(字符串，字符串[ ])](https://www.geeksforgeeks.org/c-join-method-set-1/)**
*   **[弦。联接(字符串，字符串[ ]，int pos1，int pos2)](https://www.geeksforgeeks.org/c-join-method-set-1/)**
*   **字符串。连接(字符串，IEnumerable <string>)</string>**
*   **字符串。加入<t>(字符串，IEnumerable <t>)</t></t>**

#### **字符串。连接(字符串，IEnumerable <string>)</string>**

**此方法用于连接字符串类型的构造集合的成员，在每个成员之间使用指定的分隔符。**

****语法:****

```cs
public static string Join(string separator, IEnumerable L1) 
```

****参数:****

> ****分隔符**:是用作分隔符的字符串，只有当值有多个元素且类型为*系统时，分隔符才会包含在返回的字符串中。弦*。**
> 
> ****L1** :这是一个包含要连接的字符串的集合，类型是*系统。集合。通用。可数<字符串>* 。**

****返回类型:**该方法返回类型为*系统的字符串。字符串*由分隔符字符串分隔的值的成员组成。如果值没有成员，该方法返回*字符串。清空*。**

****异常:**如果 L1 为空，这个方法可以给出 *ArgumentNullException* 。**

****示例:**在下面的程序中，使用内置的列表集合创建了一个**单词列表**。因此，**同一个列表集合**的对象在 join()方法中与分隔符一起传递，结果，用户得到结果字符串。**

```cs
// C# program to demonstrate the 
// Join(String, IEnumerable <string> L1 )
using System;
using System.Collections.Generic;

namespace ConsoleApplication1 {

class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        // getting the added words 
        // from list collections
        // and copying them into 
        // another object of list type
        List<String> alpha = AddWords();

        // passing the object of list 
        // type along with the separator
        string str1 = string.Join("--", alpha);

        // getting the value of the string..
        Console.WriteLine("The value of the string is " + str1);

    }

    // creating a collection of
    // string values using List
    private static List<String> AddWords()
    {

        List<String> alpha = new List<string>();

        // methods to add a string into list
        alpha.Add("Hello");
        alpha.Add("Geeks");
        alpha.Add("How");
        alpha.Add("are");
        alpha.Add("you?");

        // returning the object 
        // of the list type...
        return alpha;
    }
}
}
```

****Output:**

```cs
The value of the string is Hello--Geeks--How--are--you?

```** 

#### **字符串。加入<t>(字符串，IEnumerable <t>)</t></t>**

**这个方法用于连接任何用户定义的数据类型(比如 T)的构造集合的成员，在每个成员之间使用指定的分隔符。**

****语法:****

```cs
public static string Join(string separator, IEnumerable T1) 
```

****参数:****

> ****分隔符**:是用作分隔符的字符串，只有当值有多个元素且类型为*系统时，分隔符才会包含在返回的字符串中。弦*。**
> 
> ****T1** :它是一个集合，包含要连接的对象，类型是*系统。集合，通用，可数<T>T3。***

****返回类型:**该方法返回类型为*系统的字符串。字符串*由分隔符字符串分隔的值的成员组成。如果值没有成员，该方法返回*字符串。清空*。**

****异常:**如果 T1 为空，这个方法可以给出 *ArgumentNullException* 。**

****示例:**在下面的代码中，首先创建了一个用户定义的**项类**，结果各种项名**被添加到构造器**中。此外，**列表将保存类“项目”类型的对象。**结果，在主方法中，包含类项目类型的对象的列表与**分隔符“/”**一起传递，以获得输出字符串值。**

```cs
// C# program to demonstrate the 
// Join(String, IEnumerable <T > T1)
using System;
using System.Collections.Generic;

namespace ConsoleApplication2 {

// making a user defined data type..
public class items {

    public string itemname;

    // constructor to hold the 
    // string values of item class
    public items(string name1)
    {
        itemname = name1;
    }

    public override string ToString()
    {
        return this.itemname;
    }
}

class Geeks {

    // Main Method
    static void Main(string[] args)
    {
        List<items> alpha = Additems();

        // passing the list of objects
        // of item class to join method( )
        string str1 = string.Join("--", alpha);

        Console.WriteLine("The value of the string is " + str1);

    }

    private static List<items> Additems()
    {

        // adding the objects of item 
        // class into a list
        List<items> alpha = new List<items>();
        alpha.Add(new items("fans"));
        alpha.Add(new items("Bulb"));
        alpha.Add(new items("Windows"));
        alpha.Add(new items("table"));
        alpha.Add(new items("chair"));

        return alpha;
    }
}
}
```

****Output:**

```cs
The value of the string is fans--Bulb--Windows--table--chair

```**