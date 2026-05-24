# C# | Int16 Struct

> 原文:[https://www.geeksforgeeks.org/c-sharp-int16-struct/](https://www.geeksforgeeks.org/c-sharp-int16-struct/)

在 C# 中，Int16 Struct 表示从范围 **-32768 到+32767** 开始的 16 位有符号整数(也称为**简称**数据类型)。它提供了不同类型的方法来执行各种操作，比如将这种类型的实例的值转换成它的字符串表示，将数字的字符串表示转换成这种类型的实例，以及比较这种类型的实例等。也可以调用数学类的方法进行数学运算。该结构在**系统**命名空间下定义。Int16 结构继承了继承[对象类](https://www.geeksforgeeks.org/c-sharp-object-class/)的值类型类。

#### 菲尔茨

| 菲尔茨 | 描述 |
| [最大值](https://www.geeksforgeeks.org/int16-maxvalue-field-in-c-sharp-with-examples/) | 该字段用于表示 Int16 的最大可能值。该字段是常量。 |
| **[最小值](https://www.geeksforgeeks.org/int16-minvalue-field-in-c-sharp-with-examples/)** | 该字段用于表示 Int16 的最小可能值。该字段是常量。 |

**示例:**

```cs
// C# program to illustrate the
// MaxValue and MinValue field
using System;

class GFG {

    // Main method
    static public void Main()
    {
        Int16 var1 = 100;
        Int16 var2 = 30;
        Int16 var3 = 50;

        // Get the Maximum and Minimum value of 
        // Int16 type Using MaxValue and the 
        // MinValue field
        Console.WriteLine("Value 1: {0}", var1);
        Console.WriteLine("Value 2: {0}", var2);
        Console.WriteLine("Value 3: {0}", var3);
        Console.WriteLine("Maximum Value: {0}", Int16.MaxValue);
        Console.WriteLine("Minimum Value: {0}", Int16.MinValue);
    }
}
```

**Output:**

```cs
Value 1: 100
Value 2: 30
Value 3: 50
Maximum Value: 32767
Minimum Value: -32768

```

#### 方法

| 方法 | 描述 |
| **[【共享()](https://www.geeksforgeeks.org/int16-compareto-method-in-c-sharp/)** | 此方法用于将此实例与指定对象或另一个 Int16 实例进行比较，并返回一个整数，该整数指示此实例的值是小于、等于还是大于指定对象或另一个 Int16 实例的值。 |
| **[等于()](https://www.geeksforgeeks.org/int16-equals-method-in-c-sharp-with-examples/)** | 此方法用于返回一个值，该值指示此实例是否等于指定的对象或 Int16。 |
| **[GethashCode（）](https://www.geeksforgeeks.org/int16-gethashcode-method-in-c-sharp-with-examples/)** | 此方法用于返回此实例的哈希代码。 |
| **[【gettype code()](https://www.geeksforgeeks.org/int16-gettypecode-method-in-c-sharp-with-examples/)** | 此方法用于返回值类型 Int16 的类型代码。 |
| **解析()** | 此方法用于将数字的字符串表示形式转换为其等效的 16 位有符号整数。 |
| **[ToString()](https://www.geeksforgeeks.org/c-sharp-int16-tostring-method-set-1/)** | 此方法用于将此实例的数值转换为其等效的字符串表示形式。 |
| **尽力剖析()** | 此方法用于将数字的字符串表示形式转换为其等效的 16 位有符号整数。返回值指示转换是成功还是失败。 |

**例 1:**

```cs
// C# program to demonstrate the 
// Int16.Equals(Object) Method 
using System; 

class GFG { 

    // Main Method 
    public static void Main() 
    { 
        // Declaring and initializing value1 
        short value1 = 57; 

        // Declaring and initializing value2 
        // It will convert into Int16 implicitly  
        // by the compiler to check whether it is  
        // in the range of short data type i.e.  
        // Int16 or not 
        object value2 = 47; 

        // using Equals(object) method 
        bool status = value1.Equals(value2); 

        // checking the status 
        if (status) 
            Console.WriteLine("{0} is equal to {1}", 
                                    value1, value2); 
        else
            Console.WriteLine("{0} is not equal to {1}", 
                                        value1, value2); 
    } 
} 
```

**Output:**

```cs
57 is not equal to 47

```

**例 2:**

```cs
// C# program to illustrate the 
// GetHashCode() method
using System;

class GFG {

    // Main method
    static public void Main()
    {
        Int16 var1 = 100;
        Int16 var2 = 30;
        Int16 var3 = 50;

        // Get the hash code of all the variables
        // Using GetHashCode() method
        Console.WriteLine("Get the hash code of var1: {0}",
                                       var1.GetHashCode());

        Console.WriteLine("Get the hash code of var2: {0}",
                                       var2.GetHashCode());

        Console.WriteLine("Get the hash code of var3: {0}",
                                       var3.GetHashCode());
    }
}
```

**Output:**

```cs
Get the hash code of var1: 6553700
Get the hash code of var2: 1966110
Get the hash code of var3: 3276850

```

**参考:**

*   [https://docs.microsoft.com/en-us/dotnet/api/system.int16?视图=netframework-4.7.2](https://docs.microsoft.com/en-us/dotnet/api/system.int16?view=netframework-4.7.2)