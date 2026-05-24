# 参考 C#

> 原文:[https://www.geeksforgeeks.org/ref-in-c-sharp/](https://www.geeksforgeeks.org/ref-in-c-sharp/)

C# 中的 ref 关键字用于传递或返回对[方法](https://www.geeksforgeeks.org/c-sharp-methods/)的值的引用。基本上，这意味着对引用传递的值所做的任何更改都将反映这种更改，因为您修改的是地址上的值，而不仅仅是值。可以在以下情况下实施:

*   通过引用将参数传递给方法。
*   定义方法签名以返回变量的引用。
*   将结构声明为引用结构
*   作为本地参考

**例 1:** 这里定义了两种方法*加值*和*减值*。addValue 方法是一种只修改其参数值的方法。因此，当“a”的值作为参数传递给 addValue 后显示时，其值没有区别。而方法*减法值*使用参数的引用，关键字 ref 表示相同。因此，当“b”的值作为参数传递给*减法值*后显示时，您可以看到其值反映了变化。ref 关键字必须在方法定义中以及在调用方法时使用。

## C#

```cs
// C# program to illustrate the
// use of ref keyword
using System;

namespace ref_keyword {

class GFG {

    // Main Method
    static void Main(string[] args)
    {

        // Initialize a and b
        int a = 10, b = 12;

        // Display initial values
        Console.WriteLine("Initial value of a is {0}", a);
        Console.WriteLine("Initial value of b is {0}", b);
        Console.WriteLine();

        // Call addValue method by value
        addValue(a);

        // Display modified value of a
        Console.WriteLine("Value of a after addition"+
                              " operation is {0}", a);

        // Call subtractValue method by ref
        subtractValue(ref b);

        // Display modified value of b
        Console.WriteLine("Value of b after "+
            "subtraction operation is {0}", b);
    }

    // Define addValue
    // Parameters passed by value
    public static void addValue(int a)
    {
        a += 10;
    }

    // Define subtractValue
    // Parameters passed by ref
    public static void subtractValue(ref int b)
    {
        b -= 5;
    }
}
}
```

**Output**

```cs
Initial value of a is 10
Initial value of b is 12

Value of a after addition operation is 10
Value of b after subtraction operation is 7
```

**示例 2:** 您也可以在类的实例中使用关键字 ref。在下面给出的程序中，我们有一个类 Complex 来表示复数。该类还包含一个更新方法，该方法使用对象的引用并反映对象实部和虚部的值的更新。

## C#

```cs
// C# program to show the use of ref
// with  an instance of a class
using System;

namespace class_ref {

class Complex {

    private int real, img;

    // Parameterize Constructor
    public Complex(int r, int i)
    {
        real = r;
        img = i;
    }

    // Method to get value of real
    public int getRealValue()
    {
        return real;
    }

    // Method to get value of img
    public int getImgValue()
    {
        return img;
    }

    // Method to update value of complex
    // object Using reference of the object
    public static void Update(ref Complex obj)
    {
        obj.real += 5;
        obj.img += 5;
    }
}

class GFG {

    // Main Method
    static void Main(string[] args)
    {
        // Declare Complex object
        Complex C = new Complex(2, 4);
        Console.WriteLine("Complex number C = " + C.getRealValue() +
                                         " + i " + C.getImgValue());

        // Call update method
        // Pass ref of C
        Complex.Update(ref C);
        Console.WriteLine("After updating C");
        Console.WriteLine("Complex number C = " + C.getRealValue() +
                                         " + i " + C.getImgValue());
    }
}
}
```

**Output:** 

```cs
Complex number C = 2 + i 4
After updating C
Complex number C = 7 + i 9
```