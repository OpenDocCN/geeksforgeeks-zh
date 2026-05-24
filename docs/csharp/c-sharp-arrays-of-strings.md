# C# |字符串数组

> 原文:[https://www.geeksforgeeks.org/c-sharp-arrays-of-strings/](https://www.geeksforgeeks.org/c-sharp-arrays-of-strings/)

一个 *[阵](https://www.geeksforgeeks.org/c-sharp-arrays/)* 是同类型变量的集合。而[字符串](https://www.geeksforgeeks.org/c-string/)是一系列 Unicode 字符或字符数组。因此，字符串数组是字符数组的数组。这里，字符串数组和字符串数组是同一个术语。

*例如*，如果你想存储一个班级的学生名字，那么你可以使用字符串数组。字符串数组可以是一维的，也可以是多维的。

**声明字符串数组:**有两种方法可以声明字符串数组，如下所示

*   **Declaration without size:**

    **语法:**

    > String[]变量 _ name
    > 
    > 或者
    > 
    > string[]变量 _ name

*   **Declaration with size:**

    **语法:**

    > 字符串[]变量 _ 名称=新字符串[在此提供 _ 大小]；
    > 
    > 或者
    > 
    > string[]variable _ name = new string[provide _ size _ here]；

**示例:**

> //使用字符串关键字
> 字符串[] s1 的声明；
> 
> //使用 String 类对象
> 进行声明//通过赋予其大小 4
> String[] s2 =新 String[4]；

**字符串数组的初始化:**数组可以在声明后初始化。没有必要使用 new 关键字同时声明和初始化。但是，在声明后初始化数组时，必须使用新的关键字进行初始化。它不能仅通过赋值来初始化。

**示例:**

> //数组
> 字符串[] str1，str2 的声明；
> 
> //数组
> 的初始化 str1 =新字符串[5]{“元素 1”、“元素 2”、“元素 3”、“元素 4”、“元素 5”}；
> 
> str2 =新字符串[]{“元素 1”、“元素 2”、“元素 3”、“元素 4”、“元素 5”}；

**注意:**未给出大小的初始化在 C# 中无效。它会给出编译时错误。

**示例:**初始化数组的声明错误

> //编译时错误:必须给出数组的大小
> String[]str = new String[]；
> 
> //错误:数组
> 字符串[] str1 初始化错误；
> str1 = {“元素 1”、“元素 2”、“元素 3”、“元素 4”}；

**访问字符串元素数组:**初始化时，我们可以赋值。但是，我们也可以在声明和初始化之后，使用数组的索引随机分配数组的值。我们可以通过索引来访问数组值，将元素的索引放在带有数组名称的方括号中。

**示例:**

```cs
// declares & initializes string array
String[] s1 = new String[2];

// assign the value "Geeks" in array on its index 0
s1[0] = 10; 

// assign the value "GFG" in array on its index 1
s1[1] = 30;

// assign the value "Noida" in array on its index 2
s1[2] = 20;

// Accessing array elements using index
s1[0];  // returns Geeks
s1[2];  // returns Noida

```

**单行字符串数组的声明和初始化:**字符串数组也可以单行声明和初始化。这个方法更值得推荐，因为它减少了代码行。

**示例:**

```cs
String[] weekDays = new string[3] {"Sun", "Mon", "Tue", "Wed"}; 

```

**代码# 1:** 字符串数组声明、初始化和访问其元素

```cs
// C# program to illustrate the String array 
// declaration, initialization and accessing 
// its elements
using System;

class Geeks {

    // Main Method
    public static void Main()
    {
        // Step 1: Array Declaration
        string[] stringarr; 

        // Step 2:Array Initialization
        stringarr = new string[3] {"Element 1", "Element 2", "Element 3"}; 

        // Step 3:Accessing Array Elements
        Console.WriteLine(stringarr[0]); 
        Console.WriteLine(stringarr[1]); 
        Console.WriteLine(stringarr[2]); 
    }
}
```

**输出:**

```cs
Element 1
Element 2
Element 3

```

**代码# 2:** 单行数组声明和初始化

```cs
// C# code to illustrate Array declaration
// and initialization in single line
using System;

class Geeks {

    // Main Method
    public static void Main()
    {
        // array initialization and declaration
        String[] stringarr = new String[] {"Geeks", "GFG", "Noida"}; 

        // accessing array elements
        Console.WriteLine(stringarr[0]);
        Console.WriteLine(stringarr[1]);
        Console.WriteLine(stringarr[2]);
    }
}
```

**输出:**

```cs
Geeks
GFG
Noida

```

**注:**

*   In the `*public static void main(String[] args)*`, ***String[] args*** is also an array of string.

    **示例:**显示*字符串[]参数*是字符串数组。

    ```cs
    // C# program to get the type of "args"
    using System;

    class GFG {

        // Main Method
        static public void Main (String[] args) {

            // using GetType() method to
            // get type at runtime
            Console.WriteLine(args.GetType());
        }
    }
    ```

    **输出:**

    ```cs
    System.String[]

    ```

*   C# 字符串数组基本上是一个 ***数组的对象*** 。
*   It doesn’t matter whether you are creating an array of string using *string* keyword or *String class object*. Both are same.

    **示例:**

    ```cs
    // C# program to get the type of arrays of 
    // strings which are declared using 'string'
    // keyword and 'String class object'
    using System;

    class GFG {

        // Main Method
        static public void Main (String[] args) {

            // declaring array of string 
            // using string keyword
            string[] s1 = {"GFG", "Noida"};

             // declaring array of string 
            // using String class object
            String[] s2 = new String[2]{"Geeks", "C#"};

            // using GetType() method to
            // get type at runtime
            Console.WriteLine(s1.GetType());
            Console.WriteLine(s2.GetType());
        }
    }
    ```

    **输出:**

    ```cs
    System.String[]
    System.String[]

    ```