# C# 程序在同一个类中实现多个接口

> 原文:[https://www . geesforgeks . org/c-sharp-程序到实现-多接口同类/](https://www.geeksforgeeks.org/c-sharp-program-to-implement-multiple-interfaces-in-the-same-class/)

像类一样，[接口](https://www.geeksforgeeks.org/c-interface/) 可以有方法、属性、事件和索引器作为其成员。但是接口将只包含成员的声明。接口成员的实现将由隐式或显式实现接口的类给出。C# 允许单个[类](https://www.geeksforgeeks.org/c-class-and-object/)一次可以实现多个接口，并且还可以在该接口中定义方法和变量。

**接近**

**1。**要在同一个类的所有接口中实现三个接口和一些方法，请执行以下步骤:

**2。**创建三个名为第一接口、第二接口和第三接口的接口，并在其中声明方法。

```cs
interface firstinterface
{
    // Declaration of method
    void myfun1();
}
```

**3。**现在我们创建一个 Int_Class，它将实现所有这些接口，如下所示:

```cs
class Int_Class : firstinterface, secondinterface, thirdinterface
```

*   之后，在 Int_Class 中，我们定义了方法 1、方法 2 和方法 3 的定义。
*   现在，在主函数中创建名为 Int_class 的 obj1、obj2、obj3 的对象。
*   创建对象后，使用主函数中 Int_Class 的对象调用方法。

**例:**

## c#

```cs
// C# program to implement multiple interfaces 
// in the same class.
using System;

// Creating interfaces
interface firstinterface
{

    // Declaring Method 
    void myfun1();
}

interface secondinterface
{

    // Declaring Method
    void myfun2();
}

interface thirdinterface
{

    // Declaring Method 
    void myfun3();
}

// Here Int_Class implements three interfaces
class Int_Class : firstinterface, secondinterface, thirdinterface
{

    // Definition of Method
    public void myfun1()
    {
        Console.WriteLine("Hello! i am method of firstinterface");
    }

    // Definition of Method
    public void myfun2()
    {
        Console.WriteLine("Hello! i am method of secondinterface");
    }   

    // Definition of Method 
    public void myfun3()
    {
        Console.WriteLine("Hello! i am method of thirdinterface");
    }
}

class GFG{

// Driver code
public static void Main(String[] args)
{

    // Creating the objects of Int_Class class
    firstinterface obj1;
    secondinterface obj2;
    thirdinterface obj3;

    obj1 = new Int_Class();
    obj2 = new Int_Class();
    obj3 = new Int_Class();

    // Call the methods from firstinterface, 
    // secondinterface, and thirdinterface
    obj1.myfun1();
    obj2.myfun2();
    obj3.myfun3();
}
}
```

**输出:**

```cs
Hello! i am method of firstinterface
Hello! i am method of secondinterface
Hello! i am method of thirdinterface
```

**说明:**在上面的代码中，首先我们创建了三个名为 firstinterface、secondinterface 和 thirdinterface 的接口，以及每个接口中一个名为 myfun1、myfun2 和 myfun3 的方法。现在我们创建一个 Int_Class 来实现所有这三个接口。现在在主函数中，我们创建了 Int_class 的三个对象，即 obj1、obj2 和 obj3，使用这些对象，我们将调用 firstinterface、secondinterface 和 thirdinterface 的方法。