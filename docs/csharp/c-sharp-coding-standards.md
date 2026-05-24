# C# 编码标准

> 原文:[https://www.geeksforgeeks.org/c-sharp-coding-standards/](https://www.geeksforgeeks.org/c-sharp-coding-standards/)

C# 是一种通用、现代和面向对象的编程语言，发音为“C Sharp”。它是由微软开发的，由安德斯·海尔斯伯格和他的团队领导。NET 倡议，并获得了欧洲计算机制造商协会(ECMA)和国际标准组织(ISO)的批准。C# 是公共语言基础设施的语言之一。 [C# ](https://www.geeksforgeeks.org/csharp-programming-language/) 在句法上与 Java 有很多相似之处，对于有 C、C++、或者 [Java](https://www.geeksforgeeks.org/java/) 知识的用户来说很容易理解。

以下是一些最佳实践。网络开发人员应遵循:

**1。类和方法的名称应该总是以帕斯卡为单位**

```cs
public class Employee
{
    public Employee GetDetails()
    {
        //...
    }
    public double GetBonus()
    {
        //...
    }
}
```

**2。方法参数和局部变量应该总是在 Camel Case**

```cs
public class Employee
{
    public void PrintDetails(int employeeId, String firstName)
    {
        int totalSalary = 2000;
        // ...
    }
}
```

**3。命名标识符时避免使用下划线**

```cs
// Correct
public DateTime fromDate;
public String firstName;

// Avoid
public DateTime from_Date;
public String first_Name;
```

**4。避免使用系统数据类型，更喜欢使用预定义的数据类型。**

```cs
// Correct
int employeeId;
string employeeName;
bool isActive;

// Avoid
Int32 employeeId;
String employeeName;
Boolean isActive;
```

**5。始终在接口前面加上字母 I.**

```cs
// Correct
public interface IEmployee
{
}
public interface IShape
{
}
public interface IAnimal
{
}

// Avoid
public interface Employee
{
}
public interface Shape
{
}
public interface Animal
{
}
```

**6。为了更好的代码缩进和可读性，请始终垂直对齐大括号。**

```cs
// Correct
class Employee
{
    static void PrintDetails()
    {
    }
}

// Avoid
class Employee
    {
    static void PrintDetails()
    {
      }
}
```

**7。使用一次性类型时，请始终使用 use 关键字。当程序流离开作用域时，它会自动处置对象。**

```cs
using(var conn = new SqlConnection(connectionString))
{
    // use the connection and the stream
    using (var dr = cmd.ExecuteReader())
    {
     //
    }
}
```

**8。始终尽可能接近变量的用途来声明变量。**

```cs
// Correct
String firstName = "Shubham";
Console.WriteLine(firstName);
//--------------------------

// Avoid
String firstName = "Shubham";
//--------------------------
//--------------------------
//--------------------------
Console.WriteLine(firstName);
```

**9。始终将属性声明为私有，以实现封装并确保数据隐藏。**

```cs
// Correct
private int employeeId { get; set; }

// Avoid
public int employeeId { get; set; }
```

**10。总是用一个空格把程序的不同部分分开。**

```cs
// Correct
class Employee
{
private int employeeId { get; set; }

public void PrintDetails()
{
//------------
}
}

// Avoid
class Employee
{

private int employeeId { get; set; }

public void PrintDetails()
{
//------------
}

}
```

**11。常量应该总是以大写形式声明。**

```cs
// Correct
public const int MIN_AGE = 18;
public const int MAX_AGE = 60;

// Avoid
public const int Min_Age = 18;
public const int Max_Age = 60;
```