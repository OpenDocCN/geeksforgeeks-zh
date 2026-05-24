# C# |检查两个字符串对象是否有相同的值| Set-1

> 原文:[https://www . geesforgeks . org/c-sharp-check-if-two-string-objects-同值集-1/](https://www.geeksforgeeks.org/c-sharp-check-if-two-string-objects-have-the-same-value-set-1/)

**弦。Equals 方法**方法用于检查两个 String 对象是否具有相同的值。通过向该方法传递不同数量和类型的参数，可以重载该方法。该方法的重载列表中共有 5 种方法，其中前 2 种在本文中讨论，其余的在 [**Set-2**](https://www.geeksforgeeks.org/c-equalsstring-string-method/) 和 **Set-3** 中讨论。

1.  **等于(对象)**
2.  **等于(字符串)**
3.  **等于(字符串，字符串)**
4.  **等于(字符串，字符串比较)**
5.  **等于(字符串，字符串，字符串比较)**

### 1.等于(对象)

此方法用于检查此实例和指定的对象(也必须是字符串对象)是否具有相同的值。此方法还在区分大小写和不区分区域性的情况下执行序数比较。

**语法:**

```cs
public override bool Equals (object ob1);
```

这里， *ob1* 是用来和这个实例比较的字符串对象。

**返回值:**该方法的返回类型为**系统。布尔**。如果 *ob1* 是一个字符串，并且它的值与这个实例相同，那么这个方法将返回真，否则返回假。如果 *ob1* 的值为空，则该方法将返回 false。

**示例:**

## C#

```cs
// C# program to illustrate
// Equals(Object) method
using System;

// Structure
public struct Student
{

    private string name;

    public string StudentName
    {
        get
        {
            return name;
        }
    }

    public Student(string Sname)
    {
        name = Sname;
    }

    public override string ToString()
    {
        return name;
    }
}

// Driver Class
public class GFG {

    // Main method
    static void Main(String[] args)
    {
        // Creating object of Student structure
        Student s1 = new Student("Ankita");
        Student s2 = new Student("Soniya");
        Student s3 = new Student("Ankita");

        // Check the given objects are equal or not
        Console.WriteLine("Object 1 is equal to object 2: {0}",
                                                s1.Equals(s2));

        Console.WriteLine("Object 1 is equal to object 3: {0}",
                                                s1.Equals(s3));
    }
}
```

**Output:** 

```cs
Object 1 is equal to object 2: False
Object 1 is equal to object 3: True
```

### 2.等于(字符串)

此方法用于检查此实例和另一个指定的字符串对象是否具有相同的值。此方法还在区分大小写和不区分区域性的情况下执行序数比较。

**语法:**

```cs
public bool Equals (string item);
```

这里，*项*是用来和这个实例比较的字符串。

**返回值:**该方法的返回类型为**系统。布尔**。如果*项*的值与该实例的值相同，则该方法返回真，否则返回假。如果*项*的值为空，则该方法将返回 false。

**示例:**

## C#

```cs
// C# program to illustrate
// Equals(String) method
using System;

class GFG {

    // Main method
    static void Main(String[] args)
    {

        // Creating object of Student structure
        string s1 = "GeeksforGeeks";
        string s2 = "hellogeeksforgeeks";
        string s3 = "GeeksforGeeks";

        // Check the given strings are equal or not
        Console.WriteLine("String 1 is equal to String 2: {0}",
                                                s1.Equals(s2));

        Console.WriteLine("String 1 is equal to String 3: {0}",
                                                s1.Equals(s3));
    }
}
```

**Output:** 

```cs
String 1 is equal to String 2: False
String 1 is equal to String 3: True
```

**下一个:** [*Set-2*](https://www.geeksforgeeks.org/c-equalsstring-string-method/) 和 *Set-3*
**参考:**[https://docs . Microsoft . com/en-us/dotnet/API/system . string . equals？view = net framework-4 . 7 . 2](https://docs.microsoft.com/en-us/dotnet/api/system.string.equals?view=netframework-4.7.2)