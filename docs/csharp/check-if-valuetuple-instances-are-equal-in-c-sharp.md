# 检查值元组实例在 C# 中是否相等

> 原文:[https://www . geesforgeks . org/check-if-value tuple-instance-is-equal-in-c-sharp/](https://www.geeksforgeeks.org/check-if-valuetuple-instances-are-equal-in-c-sharp/)

[ValueTuple](https://www.geeksforgeeks.org/valuetuple-in-c-sharp/) 是 C# 7.0 中引入的一个结构，代表值类型 Tuple。它允许您存储包含多个值的数据集，这些值可能彼此相关，也可能彼此不相关。
在值元组中，可以使用**值元组检查两个值元组是否相同。平等法**。此方法将返回一个值，该值指示给定的 ValueTuple 实例是否等于指定的对象。如果给定的元组相等，它将返回 true，否则返回 false。该方法可以通过两种不同的方式重载:

1.  **等于(值元组)方法**
2.  **等于(对象)法**

#### 等于(值元组)方法

Equals(ValueTuple)方法用于检查两个 ValueTuple 实例是否相等。它总是返回真。该方法的返回类型为*系统。布尔*。

**语法:**

```cs
public bool Equals (ValueTuple other);
```

这里， *other* 是一个值元组，用于与当前实例进行比较。

**返回:**总是返回真。

**示例:**

```cs
// C# program to illustrate to check the
// given ValueTuples are equal or not
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating a value tuples with two elements
        var MyTple1 = ValueTuple.Create(56, 45);
        var MyTple2 = ValueTuple.Create(56, 45);

        bool res1 = MyTple1.Equals(MyTple2);
        Console.WriteLine("Is MyTple1 and MyTple2 equal?: " + res1);
    }
}
```

**Output:**

```cs
Is MyTple1 and MyTple2 equal?: True

```

#### 等于(对象)方法

Equals(Object)方法用于返回一个值，该值确定当前 ValueTuple 实例是否等于指定的对象。如果给定的 ValueTuple 实例等于指定的对象，该方法将返回 *true* ，否则将返回 false。

**语法:**

```cs
public override bool Equals (object obj);
```

这里， *obj* 是要与当前实例进行比较的对象。

**返回类型:**该方法的返回类型为*系统。布尔*。

**示例:**

```cs
// C# program to illustrate how to check the 
// given value tuples is equal or not 
// using Equal(Object) method
using System;

class GFG {

    // Main method
    static public void Main()
    {

        // Creating a value tuples 
        // with one element
        var MyTple1 = (56);

        object ob1 = 56;

        // Check the given object is equal or not
        // Using Equals(Object) method
        bool res = MyTple1.Equals(ob1);
        if (res == true) 
        {
            Console.WriteLine("The given object is equal to"+
                            " the value tuple element...!!");
        }

        else
        {
            Console.WriteLine("Not equal....!!");
        }
    }
}
```

**Output:**

```cs
The given object is equal to the value tuple element...!!

```

**参考:**

*   [https://docs . Microsoft . com/en-us/dotnet/API/system . value tuple . equals？视图=netframework-4.8](https://docs.microsoft.com/en-us/dotnet/api/system.valuetuple.equals?view=netframework-4.8)