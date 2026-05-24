# C# |封装

> 原文:[https://www.geeksforgeeks.org/c-sharp-encapsulation/](https://www.geeksforgeeks.org/c-sharp-encapsulation/)

封装被定义为将数据包装在一个单元下。它是将代码及其操作的数据绑定在一起的机制。从另一个角度来说，封装是一个保护屏障，防止数据被这个屏障之外的代码访问。

*   从技术上讲，在封装中，一个类的变量或数据对任何其他类都是隐藏的，只能通过声明它们的自己类的任何成员函数来访问。
*   与封装一样，一个类中的数据对其他类是隐藏的，因此也被称为**数据隐藏**。
*   **封装可以通过:**将类中的所有变量声明为私有，并使用类中的 **[C# Properties](https://www.geeksforgeeks.org/c-properties/)** 来设置和获取变量的值。

![](img/8a6132699def430a1c4936fdb2166d4b.png)

**示例:**

```cs
// C# program to illustrate encapsulation
using System;

public class DemoEncap {

    // private variables declared
    // these can only be accessed by
    // public methods of class
    private String studentName;
    private int studentAge;

    // using accessors to get and 
    // set the value of studentName
    public String Name
    {

        get
        {
            return studentName;    
        }

        set 
        {
            studentName = value;
        }

    }

    // using accessors to get and 
    // set the value of studentAge
    public int Age
    {

        get 
        {
            return studentAge;    
        }

        set 
        {
            studentAge = value;
        }

    }

}

// Driver Class
class GFG {

    // Main Method
    static public void Main()
    {

        // creating object
        DemoEncap obj = new DemoEncap();

        // calls set accessor of the property Name, 
        // and pass "Ankita" as value of the 
        // standard field 'value'
        obj.Name = "Ankita";

        // calls set accessor of the property Age, 
        // and pass "21" as value of the 
        // standard field 'value'
        obj.Age = 21;

        // Displaying values of the variables
        Console.WriteLine("Name: " + obj.Name);
        Console.WriteLine("Age: " + obj.Age);
    }
}
```

**输出:**

```cs
Name: Ankita
Age: 21

```

**解释:**在上面的程序中，类*demoncap*被封装为变量，并被声明为私有。为了访问这些私有变量，我们使用包含 get 和 set 方法的 Name 和 Age 访问器来检索和设置私有字段的值。访问器被定义为公共的，以便它们可以在其他类中访问。

**封装优势:**

*   **数据隐藏:**用户将不知道类的内部实现。用户看不到该类如何在变量中存储值。他只知道我们正在将值传递给访问器，并且变量正在被初始化为该值。
*   **增加灵活性:**我们可以根据自己的需求，将类的变量设为只读或只写。如果我们希望将变量设为只读，那么我们只需要在代码中使用 Get Accessor。如果我们希望将变量设置为只写，那么我们只能使用 Set Accessor。
*   **可重用性:**封装还提高了可重用性，容易随着新的需求而改变。
*   **测试代码很容易:**封装的代码对于单元测试来说很容易测试。