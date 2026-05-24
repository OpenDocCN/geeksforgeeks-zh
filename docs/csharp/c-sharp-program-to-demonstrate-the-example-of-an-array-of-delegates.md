# 演示委托数组示例的 C# 程序

> 原文:[https://www . geeksforgeeks . org/c-sharp-program-to-professional-array-of-delegates/](https://www.geeksforgeeks.org/c-sharp-program-to-demonstrate-the-example-of-an-array-of-delegates/)

在 C# 中，[委托](https://www.geeksforgeeks.org/c-sharp-delegates/)是一个引用方法的对象，或者是一个引用类型变量，可以保存对方法的引用。委托类似于 C/C++函数指针。它还提供了一种方法，告诉在事件被触发时调用哪个方法。顾名思义，委托数组意味着使用以下语法在数组中声明委托数组:

**语法:**

```cs
name[] object = new name[size];
```

其中 name 是委托数组，size 是委托数组的大小。我们还可以通过委托数组的索引将方法传递给委托数组。

```cs
name[0] = method1;
name[1] = method2;
-----------------
-----------------
name[n] = methodn;
```

我们可以用代表的名字来称呼他。

```cs
delegate_array();
```

现在我们将创建三个方法，并创建一个委托数组来指向这些方法，我们使用委托数组来调用方法。

**进场:**

**1。**在此声明代表，Myrect()为代表。

```cs
delegate void Myrect(double len, double width);
```

**2。**创建三种常规方法，命名为面积、周长和对角线。

**3。**创建一个大小为 3 的委托数组。

```cs
Myrect[] del = new Myrect[3];
```

**4。**将这些方法传递给委托的每个数组索引。

```cs
del[0] = Area;
del[1] = Perimeter;
del[2] = Diagonal;
```

**5。**调用迭代循环内部数组的委托。

```cs
for(int i = 0; i < 3; i++)
{
    del[i](len, width);
}
```

**例**:

## C#

```cs
// C# program to illustrate how to create
// an array of delegates.
using System;

// Creating delegates
delegate void Myrect(double len, double width);

class GFG{

// Finding Area of rectangle
static void Area(double len, double width)
{
    double res1 = len * width;
    Console.WriteLine("Area:" + res1);
}

// Finding perimeter of rectangle
static void Perimeter(double len, double width)
{
    double res2 = 2 * (len + width);
    Console.WriteLine("Perimeter:" + res2);
}

// Finding diagonal of rectangle
static void Diagonal(double len, double width)
{
    double res3 = Math.Sqrt(len * len + width * width);
    Console.WriteLine("Diagonal:" + res3);
}

// Driver code
static void Main()
{
    double len = 4, width = 5;

    // Create an array of delegates
    // with array size 3
    Myrect[] del = new Myrect[3];

    // Pass the methods to array index
    del[0] = Area;
    del[1] = Perimeter;
    del[2] = Diagonal;

    Console.WriteLine("Data:");
    for(int i = 0; i < 3; i++)
    {
        del[i](len, width);
    }
}
}
```

**输出:**

```cs
Data:
Area:20
Perimeter:18
Diagonal:6.40312423743285
```

**说明**:在上面的例子中，我们创建了一个名为“Myrect(双透镜，双宽度)”的委托，它需要两个参数。现在我们创建一个名为“GFG”的类，它包含三个名为“面积”、“周长”和“对角线”的方法，这些方法采用两个名为 len(即矩形的长度)和 width(即矩形的宽度)的参数。在主方法中，我们创建两个变量，并用矩形的长度和宽度(即 4 和 5)初始化它们。现在我们创建一个名为“del”的大小为 3 的委托数组，并将这些方法传递给委托的每个数组索引。即 del[0] =面积；del[1] =周长；del[2] =对角线；。通过调用委托(即 del[i](len，width))迭代 for 循环内部的数组来显示数据(这里 for 循环迭代三次)。