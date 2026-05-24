# C# |属性限制

> 原文:[https://www . geesforgeks . org/c-sharp-对属性的限制/](https://www.geeksforgeeks.org/c-sharp-restrictions-on-properties/)

### 先决条件:[c# 中的属性](https://www.geeksforgeeks.org/c-sharp-properties/)

属性是一种特殊类型的类成员，它提供了一种灵活的机制来读取、写入或计算私有字段的值。属性可以像公共数据成员一样使用，但它们实际上是称为访问器的特殊方法。这使得数据易于访问，并有助于提高方法的灵活性和安全性。信息的封装和隐藏也可以使用属性来实现。它使用预定义的方法，即“获取”和“设置”方法，帮助访问和修改属性。

**语法:**

```cs
<access_modifier> <return_type> <property_name>
{
        get { // body }
        set { // body }
}

```

**对属性的限制:**我们在编写属性时必须遵循一些规则或限制，如下所示:

*   **属性不能通过 ref 或 out 参数传递给方法:**属性不能通过 out 或 ref 传递，因为**属性实际上是方法**。在编译时，*参考*和*输出*都不被认为是方法签名的一部分。因此，它会给出一个编译时错误。除了从程序中完全删除 ref 或 out 之外，没有解决这个限制的办法。
*   **You cannot overload a property:** A property cannot be overloaded. It means that one can only put a single get and set accessor and mutator in a class respectively. The program given below shows what happens when we give more than one get accessor in the same class.

    ```cs
    // C# program to show what happens when
    // we try to overload a property
    using System;

    class Myprop {

        int _number;

        public int Number
        {
            get
            {
                return this._number;
            }
            set
            {
                this._number = value;
            }
            get
            {

                // Causes a compile time error
                // which tells get accessor
                return this._number; 

            } // has already been called.
        }
    }

    // Driver Class
    class GFG {

        // Main Method
        static void Main()
        {
            Myprop ex = new Myprop();

             // set { }
            ex.Number = 5;
            console.WriteLine("If there are only two properties"+
                          " in class ex we will get the output");

            // get { }
            Console.WriteLine(ex.Number); 
        }
    }
    ```

    **编译时错误:**

    > prog.cs(19，3):错误 CS1007:属性访问器已经定义

    但是通过在同一个程序中使用不同类中的**属性，可以多次使用 get 和 set。下面给出了一个说明这一点的例子。**

    ```cs
    // C# program to demonstrate the use
    // of properties in different classes
    using System;

    class Myprop {

        int _number;

        public int Number
        {
            get
            {
                return this._number;
            }
            set
            {
                this._number = value;
            }
        }
    }

    class Myprops {

        int _number;
        public int Number
        {
            get
            {
                return this._number;
            }
            set
            {
                this._number = value;
            }
        }
    }

    // Driver Class
    class GFG {

        // Main Method
        static void Main()
        {
            Myprop ex = new Myprop();
            Myprops exs = new Myprops();

            // Calls set mutator from the Myprops class
            exs.Number = 7; 

            // Calls set mutator from the Myprop class
            ex.Number = 5; 

            // Gets the get accessor form the Myprop class
            Console.WriteLine("The value set in the class "+
                                 "Myprop is: " + ex.Number); 

            // Gets the get accessor form the Myprops class
            Console.WriteLine("The value set in the class"+
                             " Myprops is: " + exs.Number); 
        }
    }
    ```

    **输出:**

    ```cs
    The value set in the class Myprop is: 5
    The value set in the class Myprops is: 7

    ```

*   **A property should not alter the state of the underlying variable when the get accessor is called:** The **get** accessor of properties is preset to read-only mode while the **set** command is set to write-only mode. Due to this, if we try to enter values or modify in the scope of the get accessor we’ll get a warning which tells that the code we are trying to access is unreachable. The example given below illustrates that.

    ```cs
    // C# program to demonstrate the 
    // above-mentioned restriction
    using System;

    class Myprop {

        int _number;
        public int Number
        {
            get
            {
                return this._number;

                // We get the warning saying that
                // the code is unreachable.
                this._number = 5; 
            }
            set
            {
                this._number = value;
            }
        }
    }

    // Driver Class
    class GFG {

        static void Main()
        {
            Myprop ex = new Myprop();

            // set { }
            ex.Number = 5; 

             // get { }
            Console.WriteLine(ex.Number);
        }
    }
    ```

    **警告:**

    > prog.cs(16，4):警告 CS0162:检测到无法访问的代码

    **输出:**

    ```cs
    5
    ```

    从程序的输出可以看出，代码运行成功，但是我们在 get 访问器中添加的值无法使用，因为它不可访问。这就是为什么在调用 get 访问器时没有必要更改基础变量的原因。