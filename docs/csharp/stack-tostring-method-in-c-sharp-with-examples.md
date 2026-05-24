# 叠加。C# 中的 ToString()方法，带示例

> 原文:[https://www . geesforgeks . org/stack-tostring-method-in-c-sharp-with-examples/](https://www.geeksforgeeks.org/stack-tostring-method-in-c-sharp-with-examples/)

**ToString 方法**继承自[对象类](https://www.geeksforgeeks.org/c-object-class/)，用于获取代表当前对象的字符串。它也可以应用于堆栈。它返回一个表示当前堆栈对象的字符串。

> **语法:**公共虚拟字符串 ToString()；
> 
> **返回值:**该方法返回集合的字符串表示形式。

**例 1:** 在下面的程序中，*使用 GetType()* 方法获取当前对象的类型。它将阐明给定的堆栈对象是否被转换为字符串。

```cs
// C# program to demonstrate
// Stack ToString() method
using System;
using System.Collections;

class GFG {

    public static void Main(String[] args)
    {
        // Creating an Empty Stack
        Stack st = new Stack();

        // Use Push() method
        // to add elements to 
        // the stack
        st.Push("Welcome");
        st.Push("To");
        st.Push("Geeks");
        st.Push("For");
        st.Push("Geeks");

        Console.WriteLine("The type of st before "+
                 "ToString Method: "+st.GetType());

        Console.WriteLine("After ToString Method: ");

        foreach(string str in st)
        {
            // Using ToString() method
            Console.WriteLine(str.ToString());
        }

        Console.WriteLine("The type of st after "+
            "ToString Method: "+st.ToString().GetType());
    }
}
```

**Output:**

```cs
The type of st before ToString Method: System.Collections.Stack
After ToString Method: 
Geeks
For
Geeks
To
Welcome
The type of st after ToString Method: System.String

```

**例 2:**

```cs
// C# program to demonstrate
// Stack ToString() method
using System;
using System.Collections;

class GFG {

    public static void Main(String[] args)
    {
        // Creating an Empty Stack
        Stack st = new Stack();

        // Use Push() method
        // to add elements to 
        // the stack
        st.Push(1);
        st.Push(2);
        st.Push(3);
        st.Push(4);
        st.Push(5);

        Console.WriteLine("The type of st before "+
                 "ToString Method: "+st.GetType());

        Console.WriteLine("After ToString Method: ");

        foreach(int i in st)
        {
            // Using ToString() method
            Console.WriteLine(i.ToString());
        }

        Console.WriteLine("The type of st after "+
            "ToString Method: "+st.ToString().GetType());
    }
}
```

**Output:**

```cs
The type of st before ToString Method: System.Collections.Stack
After ToString Method: 
5
4
3
2
1
The type of st after ToString Method: System.String

```