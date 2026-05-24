# C# | Join()方法| Set–1

> 原文:[https://www.geeksforgeeks.org/c-sharp-join-method-set-1/](https://www.geeksforgeeks.org/c-sharp-join-method-set-1/)

在 C# 中 ***Join()*** 是一个 **[串](https://www.geeksforgeeks.org/c-string/)** 的方法。此方法用于连接集合的成员或指定数组的元素，在每个成员或元素之间使用指定的分隔符。这个方法可以通过传递不同的参数来重载。Join()方法的重载列表中总共有 5 个方法，其中 3 个在本文中讨论，其余 2 个将在 [C# | Join()方法| Set–2](https://www.geeksforgeeks.org/c-join-method-set-2/)中讨论。

*   **字符串。联接(字符串，Obj [ ])**
*   **字符串。联接(字符串，字符串[ ])**
*   **字符串。联接(字符串，字符串[ ]，int pos1，int pos2)**
*   **[弦。连接(字符串，可数<字符串> )](https://www.geeksforgeeks.org/c-join-method-set-2/)**
*   **[弦。加入< T >(字符串，IEnumerable < T > )](https://www.geeksforgeeks.org/c-join-method-set-2/)**

#### **字符串。联接(字符串，Obj [ ])**

**此方法用于借助对象数组的每个元素之间的分隔符来连接对象数组的元素。**

****语法:****

```cs
public static string Join(string separator, params obj[] array) 
```

*   ****参数:**该方法取两个参数，其中一个是*系统类型的*分离器*。Sting* 用于根据用户选择定义分隔符。另一个参数是*系统类型的*阵列*。对象[]* ，包含要连接的元素。**
*   ****返回类型:**该方法的返回类型为*系统。弦*。**
*   ****异常:**如果数组为空，这个方法可以给出 *ArgumentNullException* 。**

****示例:**在下面的代码中，首先创建一个对象数组，然后将其与要使用的分隔符一起传递给 join 方法，这里使用了'，'逗号分隔符，在方法返回后，字符串作为输出。**

```cs
// C# program to demonstrate the
// Join(String, Obj [ ]) method
using System;
namespace ConsoleApplication1 {

class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        // Creating an object array
        // Here, It is consist of four 
        // elements only
        object[] array = {"Hello", "Geeks", 12345, 786};

        // Using Join method
        // Here separator is ', '( comma )
        string s1 = string.Join(", ", array);

        // Finally after joining process gets over
        // Getting the output of value of string s1
        Console.WriteLine("Value of string  s1 is " + s1);
    }
}
}
```

****输出:****

```cs
Value of string  s1 is Hello, Geeks, 12345, 786
```

#### **字符串。联接(字符串，字符串[ ])**

**此方法用于在字符串数组的每个元素之间使用用户指定的分隔符来连接字符串数组的元素。**

****语法:****

```cs
public static string Join(string separator, params string[ ] array) 
```

*   ****参数:**该方法取两个参数，其中一个是*系统类型的*分离器*。Sting* 用于根据用户选择定义分隔符。另一个参数是*系统类型的*阵列*。包含要连接的元素的字符串[]* 。**
*   ****返回类型:**该方法的返回类型为*系统。弦*。**
*   ****异常:**如果数组为空，这个方法可以给出 *ArgumentNullException* 。**

****示例:**在下面的代码中，首先创建一个字符串数组，并将其与要使用的分隔符一起传递给 join 方法，这里使用“/”斜杠分隔符，在方法返回后，将字符串打印为输出。**

```cs
// C# program to demonstrate the
// Join(String, String [])
using System;
namespace ConsoleApplication2 {

class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        // Creating a string array
        // Here It contains five 
        // elements only
        string[] array = {"hello", " World ", 
                "Geeks", " are ", "  here " };

        // Using Join method
        // Here separator used is '/'( slash )
        string s1 = string.Join("/", array);

        // Finally after join method
        // Getting the output of value of string s1
        Console.WriteLine("Value of string  s1 is " + s1);
    }
}
}
```

****输出:****

```cs
Value of string  s1 is hello/ World /Geeks/ are /  here 
```

#### **字符串。联接(字符串，字符串[ ]，int pos1，int pos2)**

**此方法用于在指定位置之间连接字符串数组的元素，并在数组的每个元素之间使用用户定义的分隔符。**

****语法:****

```cs
public static string Join(string separator, params string[] array, int pos1, int pos2) 
```

*   ****参数:**该方法取四个参数，第一个是*系统类型的*分离器*。Sting* 用于根据用户选择定义分隔符。第二个参数是*系统类型的*数组*。包含要连接的元素的字符串[]* 。第三个参数是*系统类型的 *pos1* 。Int32* 是数组中第一个要使用的元素，关于这个参数需要记住的重要一点是它使用了*零基*索引。第四个参数是*系统类型的 *pos2* 。Int32* 用于指定要使用的数组元素的数量，它总是从 1 开始，即它将 pos1’值作为其第一个元素进行计数。**
*   ****返回类型:**该方法的返回类型为*系统。弦*。也可以返回类型*字符串。如果 pos2 的值为零，则清空*。**
*   ****异常:**如果数组为空，这个方法可以给出 *ArgumentNullException* 。*如果 pos1 或 pos2 小于零或者 pos1 + pos2 大于数组中的元素个数，则可以给出 argumentoutofrangerexception*，同样这个方法也可以给出 *OutOfMemoryException* 。**

****示例:**在下面的代码中，创建了一个字符串数组，假设用户想要连接位置索引 2 中的字符串，并且想要覆盖五个元素。**

```cs
// C# program to demonstrate the
// Join(String, string [ ], int 
// pos1, int pos2) method
using System;
namespace ConsoleApplication3 {

class Geeks {

    // Main Method
    static void Main(string[] args)
    {

        // Creating a string array
        string[] array = {"lazy", "dog", "jumps", "Over",
                                  "the", "Lazy", "fox" };

        // Using Join method
        // Here separator used is '-'( hiphen )
        // from index 2 and covers upto 5 
        // elements from index 2
        string s1 = string.Join("-", array, 2, 5);

        // Finally after joining process gets over
        // Getting the output of value of string s1
        Console.WriteLine("Value of string is " + s1);

    }
}
}
```

****输出:****

```cs
Value of string is jumps-Over-the-Lazy-fox
```

****参考文献:****

*   **[https://msdn . Microsoft . com/en-us/library/tk0xe5h 0(v = vs . 110)。aspx](https://msdn.microsoft.com/en-us/library/dd988350(v=vs.110).aspx)**
*   **[https://msdn . Microsoft . com/en-us/library/57a 79 xd 0(v = vs . 110)。aspx](https://msdn.microsoft.com/en-us/library/57a79xd0(v=vs.110).aspx)**
*   **[https://msdn . Microsoft . com/en-us/library/tk0xe5h 0(v = vs . 110)。aspx](https://msdn.microsoft.com/en-us/library/tk0xe5h0(v=vs.110).aspx)**