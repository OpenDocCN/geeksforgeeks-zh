# C# |数组 vs 数组列表

> 原文:[https://www.geeksforgeeks.org/c-sharp-array-vs-arraylist/](https://www.geeksforgeeks.org/c-sharp-array-vs-arraylist/)

**数组:**数组是一组相似类型的变量，由一个公共名称引用。

**例:**

```cs
// C# program to demonstrate the Arrays
using System;

class GFG {

    // Main Method
    public static void Main(string[] args)
    {

        // creating array
        int[] arr = new int[4];

        // initializing array
        arr[0] = 47;
        arr[1] = 77;
        arr[2] = 87;
        arr[3] = 97;

        // traversing array
        for (int i = 0; i < arr.Length; i++) {

            Console.WriteLine(arr[i]);
        }
    }
}
```

**输出:**

```cs
47
77
87
97

```

欲了解更多关于数组的信息，请参考**T1】c# |数组 T3】**

**ArrayList:** ArrayList 表示可以单独索引的对象的有序集合。它基本上是数组的替代。它还允许动态内存分配、添加、搜索和排序列表中的项目。

**例:**

```cs
// C# program to illustrate the ArrayList
using System;
using System.Collections;

class GFG {

    // Main Method
    public static void Main(string[] args)
    {

        // Create a list of strings
        ArrayList al = new ArrayList();
        al.Add("Ajay");
        al.Add("Ankit");
        al.Add(10);
        al.Add(10.10);

        // Iterate list element using foreach loop
        foreach(var names in al)
        {
            Console.WriteLine(names);
        }
    }
}
```

**输出:**

```cs
Ajay
Ankit
10
10.1

```

要了解更多关于数组列表的信息，请参考 **[C# |数组列表类](https://www.geeksforgeeks.org/c-arraylist-class/)**

#### 数组和数组列表的区别

| **功能** | **阵列** | **数组列表** |
| --- | --- | --- |
| 内存 | 这个有固定大小，不能动态增减。 | 尺寸可以动态增减。 |
| 命名空间 | 数组属于**系统。数组**命名空间 | 数组列表属于**系统。集合**命名空间。 |
| 【数据类型】 | 在数组中，我们只能存储一种数据类型:int、string、char 等。 | 在数组列表中，我们可以存储不同的数据类型变量。 |
| 操作速度 | 插入删除操作快。 | 数组列表中的插入和删除操作比数组慢。 |
|  | 数组是强类型的，这意味着它只能存储特定类型的项目或元素。 | 数组列表不是强类型的。 |
| null | 数组不能接受 null。 | 数组列表可以接受空值。 |