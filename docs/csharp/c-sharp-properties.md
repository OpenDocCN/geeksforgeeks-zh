# C# |属性

> 原文:[https://www.geeksforgeeks.org/c-sharp-properties/](https://www.geeksforgeeks.org/c-sharp-properties/)

在讨论属性之前，让我们先来看看为什么属性的概念会出现在 C# 中？这是因为两个原因:

*   如果一个类的成员是私有的，那么 C# 中的另一个类将如何读取、写入或计算该字段的值。
*   如果该类的成员是公共的，那么另一个类可能会误用该成员。

**例:**

## C#

```cs
// C# program to illustrate the problems
// with public and private members
using System;

// public class
public class C1
{

    // public data members
    public int rn;
    public string name;

    // private field
    // private int marks = 35;

}

// another public class
public class C2
{

// Main Method
public static void Main(string[] args)
{

    // Creating object of C1 class
    C1 obj = new C1();

    // setting values to public
    // data members of class C1
    obj.rn = 10000;
    obj.name = null;

    // setting values to private
    // data members of class C1
    // obj.mark = 0;

    // display result
    Console.WriteLine("Name:  {0} \nRoll No: {1}", obj.name, obj.rn);

}
}
```

**输出:**

```cs
Name:   
Roll No: 10000
```

**解释:**在上面你可以看到 C1 类的公共成员可以被 C2 类访问，使用 C1 的对象“obj”，它可以向成员提供值，比如 Name 被赋予值 null，但是我们不希望这个值为 null。C2 不能向成员“marks”提供值，因为它在 C1 是私有的。要测试私有成员访问，删除注释并尝试运行，您可以看到编译器会给出一个错误。没有属性的编程语言使用 getter 和 setter 方法来提供这种访问机制。

使用属性

属性是一种特殊类型的类成员，它提供了一种灵活的机制来读取、写入或计算私有字段的值。属性可以像公共数据成员一样使用，但它们实际上是称为 ***访问器*** 的特殊方法。这使得数据易于访问，并有助于提高方法的灵活性和安全性。信息的封装和隐藏也可以使用属性来实现。它使用预定义的方法，即“获取”和“设置”方法，帮助访问和修改属性。
**存取器:**块的“集”和“获取”被称为“存取器”。限制财产的可及性是非常必要的。有两种访问器，即**获取访问器**和**设置访问器**。基于“获取”和“设置”访问器有不同类型的属性:

*   **读写属性:**当属性同时包含 get 和 set 方法时。
*   **只读属性:**当属性只包含 get 方法时。
*   **只写属性:**当属性只包含 set 方法时。
*   **自动实现的属性:**当属性访问器中没有额外的逻辑并且它在 C# 3.0 中引入时。

**定义属性的语法:**

```cs
<access_modifier> <return_type> <property_name>
{
        get { // body }
        set { // body }
}
```

其中，<access_modifier>可以是公共的、私有的、受保护的或内部的。<return_type>可以是任何有效的 C# 类型。<property_name>可以自定义。属性可以是不同的访问修饰符，如公共的、私有的、受保护的、内部的。访问修饰符定义了类的用户如何访问属性。同一属性的 get 和 set 访问器可能有不同的访问修饰符。可以使用静态关键字将属性声明为**静态属性**，或者使用虚拟关键字将属性标记为**虚拟属性**。</property_name></return_type></access_modifier> 

*   **Get Accessor:** 指定字段的值可以公开访问。它返回一个值，并指定*只读属性*。
    **例:**

```cs
class Geeks {
// Declare roll_no field
private int roll_no;

// Declare roll_no property
public int Roll_no 
{ 

   get 
     {
      return roll_no;
     }

}
}
```

*   **Set Accessor:** 它将指定一个值分配给属性中的私有字段。它返回一个值，并指定了*只写属性*。
    **例:**

```cs
class Geeks {

// Declare roll_no field
private int roll_no;

// Declare roll_no property
public int Roll_no
 { 

   get 
     {
         return roll_no;
      }

   set 
     {
         roll_no = value;
      }
}
}
```

**访问者可访问性**

*   我们不能在接口或显式接口成员实现上使用访问器修饰符。
*   只有当属性同时具有 set 和 get 访问器时，我们才能使用访问器修饰符。
*   如果属性是重写修饰符，则访问器修饰符必须与重写的访问器的访问器匹配。
*   访问器的可访问性级别必须比属性的可访问性级别更严格。

下面是演示不同类型属性的程序:
**程序 1:** 使用“get”访问器演示只读属性。

## C#

```cs
// C# program to illustrate the
// read-only property
using System;

public class Student {

    // Declare counter field as cnt
    private static int cnt;

    // to define constructor
    public Student()
    {

        // increment the counter
        // using constructor
        cnt++;
    }

    // Declare counter property
    public static int Counter
    {

        // read-only property
        get
        {
            return cnt;
        }
    }
}

class StudentTest {

    // Main Method
    public static void Main(string[] args)
    {

        // create three instances of
        // Student class it call constructor
        // three times which increase the counter
        Student s1 = new Student();
        Student s2 = new Student();
        Student s3 = new Student();

        // s1.Counter = 10;
        // Compile Time Error: Can't set value of
        // Counter because it is read only.

        Console.WriteLine("Total No of Student: " + Student.Counter);

        // Program Give Warning
        // The variable `s1' is assigned but its value is never used
    }
}
```

**输出:**

```cs
Total No of Student: 3
```

**程序 2:** 使用“获取”和“设置”访问器演示“读取”&写入属性。

## C#

```cs
// C# program to illustrate the
// read and write property
using System;

public class Student {

    // Declare name field
    private string name = "GeeksforGeeks";

    // Declare name property
    public string Name
    {

       get
        {
            return name;
        }

        set
        {
            name = value;
        }
    }
}

class TestStudent {

    // Main Method
    public static void Main(string[] args)
    {
        Student s = new Student();

        // calls set accessor of the property Name,
        // and pass "GFG" as value of the
        // standard field 'value'.
        s.Name = "GFG";

        // displays GFG, Calls the get accessor
        // of the property Name.
        Console.WriteLine("Name: " + s.Name);
    }
}
```

**输出:**

```cs
Name: GFG
```