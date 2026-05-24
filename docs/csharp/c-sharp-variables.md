# C# |变量

> 原文:[https://www.geeksforgeeks.org/c-sharp-variables/](https://www.geeksforgeeks.org/c-sharp-variables/)

典型的程序使用各种值，这些值在执行过程中可能会改变。例如，对用户输入的值执行某些操作的程序。一个用户输入的值可能与另一个用户输入的值不同。因此，这使得有必要使用变量，因为另一个用户可能不会使用相同的值。当用户输入一个将在操作过程中使用的新值时，可以将其临时存储在计算机的随机存取存储器中，并且这些值在整个执行过程中会发生变化，因此出现了另一个术语，称为**变量**。因此，基本上，变量是可以在运行时更改的信息的占位符。并且变量允许**检索和操作**存储的信息。

**语法:**

```cs
type variable_name = value; 
or
type variable_names;

```

**例:**

```cs
char var = 'h'; // Declaring and Initializing character variable
int a, b, c; // Declaring variables a, b and c of int type

```

**变量的特征:**

*   **Name:** must be a valid identifier. In the above example, var is a valid identifier.
*   **Type:** Defines the type of information to be stored in the variable. In the above example, char is a type.
*   **Value:** is the actual data to be stored in the variable. In the above example, h is the value.

#### 变量命名规则

*   变量名可以包含字母“a-z”或“A-Z”或数字 0-9 以及字符“_”。
*   变量的名称不能以数字开头。
*   变量的名称不能是任何 C# 关键字，比如 int、float、null、String 等。

**示例:**

*   **有效变量名称**

    ```cs
    int age;

    float _studentname;
    ```

*   **无效变量名称**

    ```cs
    int if; // "if" is a keyword

    float 12studentname; // Cannot start with digit

    ```

#### 定义或声明变量

声明变量时必须遵循一些规则:

*   Specify its type (such as int)
*   Specify its name (such as age)
*   You can provide an initial value (such as 17).

**例:**

```cs
int geeks;
float interest;

```

#### 初始化变量

术语**初始化**意味着给变量赋值。基本上，变量的实际使用属于初始化部分。在 [C# ](https://www.geeksforgeeks.org/introduction-to-c-sharp/) 中，每个数据类型都有一些[默认值](https://www.geeksforgeeks.org/c-data-types-2/)，当给定变量没有显式设置值时使用。初始化可以单独完成，也可以通过声明完成。

**例:**

```cs
int y = 7; // Declaring and initializing the variable at same time
int x; // Declaring variable x
x = 5; // initializing x with value 5
```

#### 

两种初始化方式:

1.  编译时初始化
2.  运行时初始化

### 1.编译时初始化

它意味着在程序编译期间向变量提供值。如果程序员没有提供任何值，那么编译器会在某些情况下为变量提供一些默认值。通常，当程序员想要提供一些默认值时，这种类型的初始化很有帮助。

**例:**

```cs
// C# program to demonstrate the 
// Compile Time Initialization
using System;
class Geeks {

        // only declaration, compiler will 
        // provide the default value 0 to it
        int y;

    // Main Method
    public static void Main(String []args)
    {

        // Compile Time Initialization of variable 'x'
        // Assigning value 32 to x
        int x = 32;    

        // printing the value
        Console.WriteLine("Value of x is "+x);

        // creating object to access
        // the variable y
        Geeks gfg = new Geeks(); 

        // printing the value
        Console.WriteLine("Value of y is "+gfg.y);
    }
}
```

**输出:**

```cs
Value of x is 32
Value of y is 0

```

### 2.运行时初始化

在这种情况下，用户必须输入值，该值将被复制到所需的变量中。在这种类型的初始化中，还有一种可能，即在函数调用完成后将值赋给变量。

**例:**

```cs
Input : 45
Output : Value of num is 45

Input : 27
Output : Value of num is 27

```

```cs
// C# program to demonstrate the 
// Run Time Initialization
using System;
class Geeks {

    // Main Method
    public static void Main(String []args)
    {

        // Value will be taken from user 
        // input and assigned to variable
        // num
        int num = Convert.ToInt32(Console.ReadLine());

        // printing the result
        Console.WriteLine("Value of num is " + num);

    }
}
```

**输出:**

```cs
Value of num is 45

```

**注意:**这里是控制台。ReadLine()方法要求用户输入该值，然后在“num”变量中输入相同的值。因此，该值将根据用户输入显示。