# C# |方法参数

> 原文:[https://www.geeksforgeeks.org/c-sharp-method-parameters/](https://www.geeksforgeeks.org/c-sharp-method-parameters/)

[c# 中的方法](https://www.geeksforgeeks.org/c-sharp-methods/)一般是程序中的代码或语句块，它使用户能够**重用**相同的代码，最终节省了过多的内存使用，起到了节省时间的作用，更重要的是，它提供了更好的代码可读性。所以你可以说一个方法是执行一些特定任务的语句的集合，并且可以/不可以将结果返回给调用者。
在某些情况下，用户可能想要执行一个方法，但是有时该方法需要一些有价值的输入来执行和完成它的任务。这些输入值在计算机语言中被称为**参数**。

***C# 包含以下类型的方法参数:***

*   **命名参数***   **参考参数***   **输出参数***   **默认或可选参数***   **动态参数***   **值参数***   **Params

    #### 命名参数

    使用命名参数，您可以根据参数的名称而不是它们在方法中的顺序来指定参数的值。或者换句话说，它为我们提供了一种不根据参数的顺序来记忆参数的工具。这个概念是在 C# 4.0 中引入的**。当您在方法中使用大量参数时，它使您的程序更容易理解。但是永远记住命名参数总是出现在固定参数之后，如果你试图在命名参数之后提供固定参数，那么编译器就会抛出一个错误。**

    **示例:**

    ```cs
    // C# program to illustrate the 
    // concept of the named parameters
    using System;

    public class GFG {

        // addstr contain three parameters
        public static void addstr(string s1, string s2, string s3)
        {
            string result = s1 + s2 + s3;
            Console.WriteLine("Final string is: " + result);
        }

        // Main Method
        static public void Main()
        {
            // calling the static method with named 
            // parameters without any order
            addstr(s1: "Geeks", s2: "for", s3: "Geeks");

        }
    }
    ```

    **输出:**

    ```cs
    Final string is: GeeksforGeeks

    ```

    #### 参考参数

    ref 是 C# 中的一个关键字，用于通过引用传递值类型。或者我们可以说，当控件返回到调用方法时，如果在方法的这个参数中进行了任何更改，这些更改将反映在该变量中。ref 参数不传递属性。在 ref 参数中，参数必须在传递给 ref 之前初始化。当被调用的方法也需要更改传递的参数值时，通过 ref 参数传递值非常有用。

    **示例:**

    ```cs
    // C# program to illustrate the
    // concept of ref parameter
    using System;

    class GFG {

        // Main Method
        public static void Main()
        {

            // Assigning value
            string val = "Dog";

            // Pass as a reference parameter
            CompareValue(ref val);

            // Display the given value
            Console.WriteLine(val);
        }

        static void CompareValue(ref string val1)
        {
            // Compare the value
            if (val1 == "Dog") 
            {
                Console.WriteLine("Matched!");
            }

            // Assigning new value
            val1 = "Cat";
        }
    }
    ```

    **输出:**

    ```cs
    Matched!
    Cat

    ```

    #### 输出参数

    out 是 C# 中的一个关键字，用于将参数作为引用类型传递给方法。它通常在一个方法返回多个值时使用。out 参数不传递属性。在传递到 out 之前，没有必要初始化参数。当一个方法返回多个值时，在整个参数中声明参数非常有用。

    **示例:**

    ```cs
    // C# program to illustrate the
    // concept of out parameter
    using System;

    class GFG {

        // Main method
        static public void Main()
        {

            // Creating variable
            // without assigning value
            int num;

            // Pass variable num to the method
            // using out keyword
            AddNum(out num);

            // Display the value of num
            Console.WriteLine("The sum of"
              + " the value is: {0}",num);

        }

        // Method in which out parameter is passed
        // and this method returns the value of
        // the passed parameter
        public static void AddNum(out int num)
        {
            num = 40;
            num += num;
        }
    }
    ```

    **输出:**

    ```cs
    The sum of the value is: 80

    ```

    #### 默认或可选参数

    顾名思义，可选参数不是强制参数，它们是可选的。它有助于排除某些参数的参数。或者我们可以说在可选参数中，没有必要传递方法中的所有参数。这个概念是在 C# 4.0 中引入的**。**这里，每个可选参数都包含一个默认值，这是其定义的一部分。如果我们不向可选参数传递任何参数，那么它将采用默认值。可选参数总是在参数列表的末尾定义。或者换句话说，方法、构造函数等的最后一个参数。是可选参数。

    **示例:**

    ```cs
    // C# program to illustrate the 
    // concept of optional parameters 
    using System; 

    class GFG { 

        // This method contains two regular 
        // parameters, i.e. ename and eid
        // And two optional parameters, i.e. 
        // bgrp and dept 
        static public void detail(string ename,  
                                   int eid, 
                                   string bgrp = "A+", 
                        string dept = "Review-Team") 

        { 
            Console.WriteLine("Employee name: {0}", ename); 
            Console.WriteLine("Employee ID: {0}", eid); 
            Console.WriteLine("Blood Group: {0}", bgrp); 
            Console.WriteLine("Department: {0}", dept); 
        } 

        // Main Method 
        static public void Main() 
        { 

            // Calling the detail method 
            detail("XYZ", 123); 
            detail("ABC", 456, "B-"); 
            detail("DEF", 789, "B+", 
               "Software Developer"); 
        } 
    } 
    ```

    **输出:**

    ```cs
    Employee name: XYZ
    Employee ID: 123
    Blood Group: A+
    Department: Review-Team
    Employee name: ABC
    Employee ID: 456
    Blood Group: B-
    Department: Review-Team
    Employee name: DEF
    Employee ID: 789
    Blood Group: B+
    Department: Software Developer

    ```

    #### 动态参数

    在 **C# 4.0** 中，引入了一种新型参数，称为动态参数。这里，参数动态传递意味着编译器在编译时不检查动态类型变量的类型，相反，编译器在运行时获取类型。动态类型变量是使用动态关键字创建的。

    **示例:**

    ```cs
    // C# program to illustrate the concept 
    // of the dynamic parameters
    using System;

    class GFG {

        // Method which contains dynamic parameter
        public static void mulval(dynamic val)
        {
            val *= val;
            Console.WriteLine(val);
        }

        // Main method
        static public void Main()
        {

            // Calling mulval method
            mulval(30);
        }
    }
    ```

    **输出:**

    ```cs
    900

    ```

    #### 值参数

    它是方法中的一个普通值参数，或者你可以说是通过值传递值类型。因此，当变量作为值类型传递时，它们包含数据或值，而不是任何引用。如果您将对值类型参数进行任何更改，那么它将不会反映作为参数存储的原始值。

    **示例:**

    ```cs
    // C# program to illustrate value parameters
    using System;

    public class GFG {

        // Main Method
        static public void Main()
        {

            // The value of the parameter
            // is already assigned
            string str1 = "Geeks";
            string str2 = "geeks";
            string res = addstr(str1, str2);
            Console.WriteLine(res);
        }

        public static string addstr(string s1, string s2)
        {
            return s1 + s2;
        }
    }
    ```

    **输出:**

    ```cs
    Geeksgeeks

    ```

    #### 参数

    当程序员不知道要使用的参数数量时，这很有用。通过使用参数，您可以传递任意数量的变量。仅允许一个 params 关键字，并且在 params 关键字之后的函数声明中不允许有其他 Params。如果不传递任何参数，参数的长度将为零。

    **示例:**

    ```cs
    // C# program to illustrate params
    using System;
    namespace Examples {

    class Geeks {

        // function containing params parameters
        public static int mulval(params int[] num)
        {
            int res = 1;

            // foreach loop
            foreach(int j in num)
            {
                res *= j;
            }
            return res;
        }

        static void Main(string[] args)
        {

            // Calling mulval method
            int x = mulval(20, 49, 56, 69, 78);

            // show result
            Console.WriteLine(x);
        }
    }
    }
    ```

    **输出:**

    ```cs
    295364160

    ```**