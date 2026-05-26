# 软件工程中的代码行

> 原文：`https://www.geeksforgeeks.org/lines-of-code-loc-in-software-engineering/`

一行`代码(LOC)`是代码中的任何一行文本，它不是注释或空行，在任何情况下都是该行中语句或语句片段的数量。`LOC`显然由包含程序头文件、任何变量的声明以及可执行和不可执行语句的所有行组成。由于代码行(`LOC`)只计算代码量，因此您只能使用它来比较或评估使用相同语言并使用相同编码标准编码的项目。

**特征:**

*   `Variants`，例如`Source Line`，用于设置代码库。
*   `LOC`常用于某些类型的论证中。
*   它们用于评估项目的性能或效率。

**优势:**

*   成本估算中最常用的指标。
*   与该指标相比，其替代品存在许多问题。
*   它易于进行硬估算。

**缺点:**

*   在编写更多代码行的同时提高生产率。
*   低效代码。
*   它不考虑复杂性。

研究表明，在软件开发中，`LOC`与开发项目/产品的总成本和时间长度之间，以及`LOC`与缺陷数量之间存在大致的相关性。这意味着您的`LOC`测量值越低，您在产品开发中的处境可能就越好。

让我们举个例子，检查一下下面给出的简单排序程序中的`Line`代码是如何工作的：

## c++

```cpp
void selSort(int x[], int n) {
  //Below function sorts an array in ascending order 
   int i, j, min, temp;
   for (i = 0; i < n - 1; i++) {
      min = i;
      for (j = i + 1; j < n; j++)
      if (x[j] < x[min])
      min = j;
      temp = x[i];
      x[i] = x[min];
      x[min] = temp;
   }
}
```

所以，现在如果`LOC`只是行数的计数，那么上面显示的函数包含`13 行代码(LOC)`。但是当注释和空行被忽略时，上面显示的函数包含`12 行代码(LOC)`。

让我们再举一个例子，检查一下下面给出的代码行是如何工作的：

## c++

```cpp
void main()
{
    int fN, sN, tN;
    cout << "Enter the 2 integers: ";
    cin >> fN >> sN;
    // sum of two numbers in stored in variable sum
    sum = fN + sN;
    // Prints sum 
    cout << fN << " + " <<  sN << " = " << sum;     
    return 0;
}
```

同样，如果`LOC`只是行数，那么上面显示的函数包含`11 行代码(LOC)`。但是当忽略注释和空行时，上面显示的函数包含`9 行代码(LOC)`。