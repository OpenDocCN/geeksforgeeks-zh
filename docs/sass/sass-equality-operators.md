# SASS |等式运算符

> 原文:[https://www.geeksforgeeks.org/sass-equality-operators/](https://www.geeksforgeeks.org/sass-equality-operators/)

**兼容性:**
Dart Sass 完全兼容使用相等运算符，而 LibSass 和旧版 Ruby Sass(4 . 0 . 0 版以上)认为数字相等，即使它们有不同的单位，或者一个有单位而另一个没有。这种行为是没有用的，因此新版本已经删除了这一点，因为它违反了**的传递性。**

相等运算符告诉两个值是否相等。

**语法:**
<表达式>=<表达式>
这个返回的输出显示了两个表达式是否相等，
<表达式>！= <表达式>

返回的输出显示了这两个表达式是否相等。如果两个表达式具有相同的值和相同的类型，则称它们相等，这意味着不同类型的表达式不同，如下所示:

*   两个**数字**如果具有相同的值和相同的单位，或者转换成相同的单位后，它们的值相等。

**示例:**

```html
@debug 2px == 2px 
```

**输出:**

```html
true
```

```html
@debug 1px == 1em 
```

**输出:**

```html
false
```

```html
@debug 96px == 1in 
```

**输出:**

```html
true
```

*   如果两个**字符串的内容相同，无论它们是否被引用，都被认为是相等的。**

**示例:**

```html
@debug geeksforgeeks == "geeksforgeeks"
```

**输出:**

```html
true
```

```html
@debug geeksforgeeks == GFG
```

**输出:**

```html
false
```

*   如果两种**颜色的红、绿、蓝和 alpha 值相等，则认为它们相等**

**示例:**

```html
@debug hsl(120, 72%, 80%) == #1ba61b
```

**输出:**

```html
true
```

```html
@debug rgba(120\. 236, 135, 0.1) == rgba(120, 236, 135, 0.5)
```

**输出:**

```html
false
```

*   两个**列表**内容相同则相等。请记住，空格分隔的列表不等于逗号分隔的列表，括号内的列表不等于无括号的列表。

**示例:**

```html
@debug (2, 4, 6) == (2, 4, 6)
```

**输出:**

```html
true
```

```html
@debug (2 4 6) == (2, 4, 6)
```

**输出:**

```html
false
```

```html
@debug (2 4 6) == [2 4 6]
```

**输出:**

```html
false
```

*   如果两个**贴图的关键点和值相等，则两个**贴图相等。

**示例:**

```html
$gradient: ("green" : abc, "cyan" : def)
```

**输出:**

```html
true
```

```html
@debug $gradient == ("green" : abc, "blue" : ghi)
```

**输出:**

```html
true
```

*   **真、假、空**只等于它们自己。

**示例:**

```html
@debug true == true
```

**输出:**

```html
true
```

```html
@debug false == null
```

**输出:**

```html
false
```

*   一个**函数**只等于它自己。通过引用来比较**函数，所以即使两个函数有相同的名称和定义，如果它们没有在同一个地方定义，它们也被认为是不同的。**

**示例:**

```html
@debug solve(24) == solve(24)
```

**输出:**

```html
true
```

```html
@debug solve(24) == solve("geeksforgeeks")
```

**输出:**

```html
false
```