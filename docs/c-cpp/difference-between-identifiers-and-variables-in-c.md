# C 中标识符和变量的区别

> 原文:[https://www . geesforgeks . org/标识符和变量之间的差异-in-c/](https://www.geeksforgeeks.org/difference-between-identifiers-and-variables-in-c/)

**附加条件** : [标识符](https://www.geeksforgeeks.org/cc-tokens/)，[变量](https://www.geeksforgeeks.org/variables-in-c/)

### **标识符**

[标识符](https://www.geeksforgeeks.org/cc-tokens/)用于变量、函数和数组的命名。它是以字母或下划线( **_** )开头的字母数字字符串，用于变量、函数、数组、结构、联合等。它也被称为用户定义的词。标识符名称的拼写和大小写必须不同于任何关键字。我们不能使用关键字作为标识符；它们是为特殊用途保留的。一旦声明了标识符，我们就可以在程序中的任何地方使用该标识符来引用关联的值。

### **变量**

一个[变量](https://www.geeksforgeeks.org/variables-in-c/)是一个指向内存位置的名称。它是程序中的基本存储单元。变量的值可以在程序执行过程中改变。所有的操作都是在那个记忆位置的可变效应上完成的。在 C 语言中，所有的变量都必须在使用前声明，在 C++ 中，我们可以在程序中的任何方便的地方声明。

### **标识符和变量之间的差异**

<figure class="table">

| 标识符 | 变量 |
| --- | --- |
| 它是一个唯一的名称，在执行源代码的同时赋予实体以明确的标识 | 变量是分配给内存位置的名称，用于包含其中的相应值。变量只是标识符的一种。 |
| 严禁两个或两个以上标识符相同。例如:结构名、函数名、类、枚举名、联合等。 | 可以毫不夸张地说，所有变量都是标识符，反之亦然。这些值可以是实数、字符、字符串、整数、浮点、双精度、无符号等。 |
| 标识符名称不应该与关键字相似，因为关键字是预定义的。Double、Continue、float、else 等不能在程序中用作标识符。 | 存储在内存块中的值可以在程序执行时修改。同样，作为标识符，程序中的两个或多个变量也不能同名。 |
| **Ex:**T2【enum geeks _ artiles _ in {

**1 月=1 日、2 月、3 月、4 月、5 月、6 月、7 月****}****Ex:****int geeks _ f _ geeks(int gfg _ id){/*…。****代码****…… */ }** | **Ex:****短 int geeks_id{}，int a{}，长 float b{ }，无符号 int c{ }，char ch 等** |

</figure>