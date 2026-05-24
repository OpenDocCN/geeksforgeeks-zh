# C# |多维索引器

> 原文:[https://www . geeksforgeeks . org/c-sharp-多维-索引器/](https://www.geeksforgeeks.org/c-sharp-multidimensional-indexers/)

#### 先决条件:[c# 中的索引器](https://www.geeksforgeeks.org/c-indexers/)

多维索引器几乎类似于多维数组。为了高效的基于内容的数据检索，使用了多维索引器。要创建多维索引器，您必须在索引器声明的参数列表中至少传递两个参数。若要访问多维索引器的单个元素，请使用整数下标。每个下标索引一个维度，就像第一个下标索引行维度，第二个下标索引列维度等等。

**示例 1:** 使用获取和设置访问器

```cs
// C# program to illustrate the 
// Multidimensional Indexers
using System;

class GFG {

    // reference to underlying 2D array
    int[, ] data = new int[5, 5];

    // declaring Multidimensional Indexer
    public int this[int index1, int index2]
    {
        // get accessor
        get 
        {

             // it returns the values which
            // read the indexes
            return data[index1, index2];

        }

        // set accessor
        set 
        {

            // write the values in 'data'
            // using value keyword
            data[index1, index2] = value;

        }
    }
}

// Driver Class
class Geeks {

    // Main Method
    public static void Main(String []args)
    {

        // creating the instance of 
        // Class GFG as "index"
        GFG index = new GFG();

        // assign the values accordingly to
        // the indexes of the array
        // 1st row
        index[0, 0] = 1;
        index[0, 1] = 2;
        index[0, 2] = 3;

        // 2nd row
        index[1, 0] = 4;
        index[1, 1] = 5;
        index[1, 2] = 6;

        // 3rd row
        index[2, 0] = 7;
        index[2, 1] = 8;
        index[2, 2] = 9;

        // displaying the values
        Console.WriteLine("{0}\t{1}\t{2}\n{3}\t{4}\t{5}\n{6}\t{7}\t{8}",
                                  index[0, 0], index[0, 1], index[0, 2],
                                  index[1, 0], index[1, 1], index[1, 2], 
                                  index[2, 0], index[2, 1], index[2, 2]);

    }
}
```

**Output:**

```cs
1    2    3
4    5    6
7    8    9

```

**示例 2:** 不使用“set”访问器，即仅使用 **[只读属性](https://www.geeksforgeeks.org/c-properties/)**

```cs
// C# program to illustrate the Multidimesional 
// Indexer without using set accessor 
using System;

class GFG {

    // default constructor
    public GFG() {} 

    // Multidimesional Indexer
    public int this[int i1, int i2]
    {

        // get accessor
        get 
        {

            // read only properties
            return (i1 + i2);
        }

        // No set accessor used
    }

// Main Method
public static void Main(String []args)
{

    // creating object of class
    // "GFG" as "index"
    GFG index = new GFG();

    // displaying the values
    for (int i = 0; i <= 2; i++) {

        for (int j = 1; j <= 3; j++)
        {
            Console.Write(index[i, j] + "\t");
        }

        Console.WriteLine();
    }
}
}
```

**Output:**

```cs
1    2    3    
2    3    4    
3    4    5

```