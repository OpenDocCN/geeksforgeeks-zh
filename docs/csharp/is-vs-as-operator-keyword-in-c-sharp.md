# c# 中 Is vs As 运算符关键字

> 原文:[https://www . geesforgeks . org/is-vs-as-operator-关键字 in-c-sharp/](https://www.geeksforgeeks.org/is-vs-as-operator-keyword-in-c-sharp/)

***[的区别是](https://www.geeksforgeeks.org/c-is-operator-keyword/)* 的**和 ***的[作为](https://www.geeksforgeeks.org/c-as-operator-keyword/)*** 的操作符如下:

*   **是**运算符，用于检查对象的运行时类型是否与给定类型兼容，而**是**运算符，用于执行兼容引用类型或可空类型之间的转换。
*   **是**运算符是布尔类型，而作为运算符的**不是布尔类型。**
*   如果给定对象是同一类型的，则**是**运算符返回真，而当与给定类型兼容时，作为运算符的**返回该对象。**
*   如果给定的对象不是同一类型的，则**是**运算符返回 false，而如果无法进行转换，则作为运算符的**返回 null。**
*   **是**运算符，仅用于引用、装箱和取消装箱转换，而**是**运算符，仅用于可空、引用和装箱转换

**例*T2 是符 T4:***

```cs
// C# program to illustrate the
// use of is operator keyword
using System;

// taking a class
public class P { }

// taking a class
// derived from P
public class P1 : P { }

// taking a class
public class P2 { }

// Driver Class
public class GFG {

    // Main Method
    public static void Main()
    {

        // creating an instance
        // of class P
        P o1 = new P();

        // creating an instance
        // of class P1
        P1 o2 = new P1();

        // checking whether 'o1'
        // is of type 'P'
        Console.WriteLine(o1 is P);

        // checking whether 'o1' is
        // of type Object class
        // (Base class for all classes)
        Console.WriteLine(o1 is Object);

        // checking whether 'o2'
        // is of type 'P1'
        Console.WriteLine(o2 is P1);

        // checking whether 'o2' is
        // of type Object class
        // (Base class for all classes)
        Console.WriteLine(o2 is Object);

        // checking whether 'o2'
        // is of type 'P'
        // it will return true as P1
        // is derived from P
        Console.WriteLine(o2 is P1);

        // checking whether o1
        // is of type P2
        // it will return false
        Console.WriteLine(o1 is P2);

        // checking whether o2
        // is of type P2
        // it will return false
        Console.WriteLine(o2 is P2);
    }
}
```

**输出:**

```cs
True
True
True
True
True
False
False

```

**T2 作为操作员 T4 的例子:**

```cs
// C# program to illustrate the
// concept of 'as' operator
using System;

// Classes
class Y { }
class Z { }

class GFG {

    // Main method
    static void Main()
    {

        // creating and initializing object array
        object[] o = new object[5];
        o[0] = new Y();
        o[1] = new Z();
        o[2] = "Hello";
        o[3] = 4759.0;
        o[4] = null;

        for (int q = 0; q < o.Length; ++q) {

            // using as operator
            string str1 = o[q] as string;

            Console.Write("{0}:", q);

            // checking for the result
            if (str1 != null) {
                Console.WriteLine("'" + str1 + "'");
            }
            else {
                Console.WriteLine("Is is not a string");
            }
        }
    }
}
```

**输出:**

```cs
0:Is is not a string
1:Is is not a string
2:'Hello'
3:Is is not a string
4:Is is not a string

```