# SASS |内省功能

> 原文:[https://www.geeksforgeeks.org/sass-introspection-fuctions/](https://www.geeksforgeeks.org/sass-introspection-fuctions/)

系统自检功能允许您检查系统本身的状况。当你制作样式表的时候，你不能使用它们，但是当有些东西不能按照你想要的方式工作的时候，它们对于知道发生了什么是至关重要的。

下表包含了 SASS 中的所有自省功能:

<figure class="table">

| function | describe | example |
| --- | --- | --- |
| 变量-存在($name) | This method returns a Boolean value indicating whether the given variable exists globally or locally. | $ x:40px；
变量-exists($x)
**输出:**真
变量-exists($y)
**输出:**假
 |
| Global-variable -exists($name) | This method returns a Boolean value indicating whether the given variable exists globally. | $ x:40px；
全局变量-存在($ x)；
**输出:**真
 |
| mixin-exists($ name) | This method returns a Boolean value that represents whether the given mixin exists. | @ mixin text-color { color:blue；}
**输出:**真
 |
| 检查(价值) | This method returns the value given by SASS. | 巡查(54)
**输出:** 【54】
 |
| 类型(价值) | This method returns a string representing the SASS data type of the value. | 类型-of(5 6 4 7 8 9)
**输出:**列表
 |
| 单位(数字) | This method returns the unit associated with a number, or an empty string if the number has no unit. | $ x:40px；
Unit ($ x);
**Output:** [PX T3】 【px】
$ x:40；;
Unit ($ x);
**Output:**
 |
| No unit ($number) | These methods return a Boolean value indicating whether a given number has a unit associated with it. | $ x:40px；
No unit ($ x);
**Output:** False
 |
| 可比($数字 1，$数字 2) | These methods return a Boolean value indicating whether a given number can be added, subtracted or compared. | Comparable (2em, 7em)
**output:** true
comparable (2em, 4px)
**output:** false
comparable (2em, 7)
**output:** true |

</figure>