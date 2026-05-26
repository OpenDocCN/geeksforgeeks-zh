# SASS | 内省功能

> 原文: [https://www.geeksforgeeks.org/sass-introspection-fuctions/](https://www.geeksforgeeks.org/sass-introspection-fuctions/)

系统自检功能允许您检查系统本身的状况。当你制作样式表的时候，你不能使用它们，但是当有些东西不能按照你想要的方式工作的时候，它们对于知道发生了什么是至关重要的。

下表包含了 SASS 中的所有自省功能:

<figure class="table">

| function | describe | example |
| --- | --- | --- |
| `variable-exists($name)` | This method returns a Boolean value indicating whether the given variable exists globally or locally. | `$x: 40px;`<br>`variable-exists($x)`<br>**输出:** `true`<br>`variable-exists($y)`<br>**输出:** `false` |
| `global-variable-exists($name)` | This method returns a Boolean value indicating whether the given variable exists globally. | `$x: 40px;`<br>`global-variable-exists($x);`<br>**输出:** `true` |
| `mixin-exists($name)` | This method returns a Boolean value that represents whether the given mixin exists. | `@mixin text-color { color: blue; }`<br>`mixin-exists(text-color)`<br>**输出:** `true` |
| `inspect($value)` | This method returns the value given by SASS. | `inspect(54)`<br>**输出:** `54` |
| `type-of($value)` | This method returns a string representing the SASS data type of the value. | `type-of(5 6 4 7 8 9)`<br>**输出:** `list` |
| `unit($number)` | This method returns the unit associated with a number, or an empty string if the number has no unit. | `$x: 40px;`<br>`unit($x);`<br>**输出:** `px`<br>`$x: 40;`<br>`unit($x);`<br>**输出:** `""` |
| `unitless($number)` | These methods return a Boolean value indicating whether a given number has a unit associated with it. | `$x: 40px;`<br>`unitless($x);`<br>**输出:** `false` |
| `comparable($number1, $number2)` | These methods return a Boolean value indicating whether a given number can be added, subtracted or compared. | `comparable(2em, 7em)`<br>**output:** `true`<br>`comparable(2em, 4px)`<br>**output:** `false`<br>`comparable(2em, 7)`<br>**output:** `true` |

</figure>