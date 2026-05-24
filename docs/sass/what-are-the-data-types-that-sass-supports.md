# 【SASS 支持哪些数据类型？

> 原文:[https://www . geesforgeks . org/sass 支持的数据类型是什么/](https://www.geeksforgeeks.org/what-are-the-data-types-that-sass-supports/)

Sass 是一种 CSS 预处理器脚本语言。在这里，我们不需要混淆 Sass 和 Scss，两者是相同的东西，但是在 CSS3 之前，Sass 拥有更老的语法&在 CSS3 之后，它被称为 SCSS。与所有其他编程语言一样，Sass 也包含数据类型，用于处理正在使用的不同类型的数据。然而，Sass 不是一种标准的编程语言，但它确实由数据类型组成。在本文中，我们将查看 Sass 中使用的所有可用数据类型，并寻找一些用例。如果您不了解 SASS，请参考 [SASS 简介](https://www.geeksforgeeks.org/sass-introduction/) & [SASS 全表](https://www.geeksforgeeks.org/sass-full-form/)文章。
Sass 总共包含 7 种数据类型:

*   数字
*   布尔运算
*   列表
*   地图
*   空
*   线
*   颜色；色彩；色调

让我们按顺序讨论每种数据类型。

**Numbers:** Sass 将 Number 视为整数和实数，在使用时，它确实会识别正在使用哪些值。有一些标准单位被用作 px(像素单位)或 em(短暂单位)。为了对数字进行运算，我们必须确保使用相同的单位，否则会产生一些错误。

**示例:**

```html
$len: 10;
$wid: 20.5;

.main{
    height: 10px + 10; // It is valid
    width: 20px - 5; // It is valid
}

.box0{
    height: 10px + $len; // Valid
    height: 10em + $wid; // Valid
}

.box{
    height: 10em + 10em; // It is valid
    width: 10px + 10em; // Error
}

```

**布尔:** Sass 也有布尔数据类型，布尔有两个值，可以是真也可以是假。为了使用布尔运算，它提供了三个基本操作符，它们被称为**和，或者**和**不是。**请注意，我们使用小写字母作为运算符，因为大写字母在 Sass 中将被视为字符串。

*   **和:**如果两个值都为真，则返回真值，否则返回假值。

    ```html
    @debug true and true; // Returns true value
    ```

*   **或:**如果两个值中有一个为真，则返回真值；如果两个值都为假，则返回假值&。

    ```html
    @debug true or false; // Returns true value
    @debug false or false; // Returns false value
    ```

*   **not:** 返回当前已有值的否定值。

    ```html
    @debug not true; // Returns false value
    @debug not false; // Returns true value
    ```

**List:**Sass 支持 List 数据类型，基本上是用来表示一系列用空格或逗号分隔的值。请注意，如果列表中使用了单个值，它将被视为有效列表。

**示例:**

```html
$number-list: 10, 23, 10; // Seperated by commas.
$number-list2: 10px 20px 30px; // Seperated by spaces.
```

我们也可以使用嵌套列表。在这种情况下，我们将使用由逗号和空格分隔的两种类型的值，如下例所示。

```html
$number-list3: 10, 20 30, 10; // Nested list.
$number-list4: 10, (20 30), 10; // Nested list same as $number-list3.
```

还有一种情况，列表可以是空的。

```html
$empty-list: ();
```

**地图:**Sass 中的地图基本都是键值对。这些对必须用逗号分隔，并且所有对都必须用括号括起来。

```html
$new-map: (primary: #fdfdfd, secondary: $fff, background: #f1f1f1);  
```

为了在 Sass 中使用地图，我们不能直接使用它们。但是，在 sass 中有一些功能是可用的，借助这些功能，我们可以检索地图的价值，并在需要的地方使用它。这些是一些功能:-

*   地图获取
*   地图合并
*   地图键
*   地图有钥匙
*   地图-移除
*   地图值

**Null:**Null 数据类型只包含一个基本上不知道或未知的值，它表示为小写的 **null。**正如我们看到的，有些数据类型有一些函数和运算符，但是对于 null，在 Sass 中没有任何运算符和函数可用。

```html
$primary-color: null;
```

请注意，如果任何变量用 null 初始化，并且如果我们尝试使用该变量，那么它将在编译时被忽略，并且该特定变量将不会被考虑。

**字符串:**字符串是有序的字符序列，可以用双引号或单引号表示，也可以不用引号。这里有一些例子，将明确我们对字符串的看法。

```html
$color: blue;
$font-family: 'Courier New', Courier, monospace;
$heading: "Welcome";
```

在萨斯还有一件事我们需要知道。有一个插值的概念，用于将变量传递给选择器。其语法由 **#{ <变量> }表示。**当我们使用插值时，引用的字符串将从引用中展开，如示例所示。

```html
$heading: "GeeksforGeeks";

h2.#{$heading} {
  color: green;
}
```

在下面的代码中，我们可以看到上面用于插值的 Sass 代码的 CSS 代码。

```html
h2.GeeksforGeeks {
 color: green;
}
```

**颜色:** Sass 支持颜色作为数据类型，因为它用于定义颜色值。在这里，我们可以看到在常规 CSS 中使用的相同的颜色表达式。

*   **RGB(红、绿、蓝):**

    ```html
    $primary: rgb(214,121,45);
    ```

*   **RGBA(红、绿、蓝、阿尔法):**

    Alpha 用于透明度&它的值从 0.0 到 1.0 不等，其中 0 是完全透明的，1.0 是完全不透明的。

    ```html
    $color: rgba(210, 122, 54, 0.5)
    ```

*   **HSL(色相、饱和度、明度):**

    该表达式包含一些不同于常规颜色的参数。

    ```html
    $color: hsl(0, 0%, 100%);
    ```

    *   **色相**可以认为是在色轮中表示的纯色，可以通过 0 到 360 之间的值进行选择，其中每个值都持有稍微不同的颜色。
    *   **饱和度** 随着颜色值的百分比增加，会对颜色应用一个阴影。在 0%时，颜色看起来会褪色，随着值的增加，颜色会变成最纯净的形式。
    *   **亮度**对颜色应用灯光层。它的值从 0 到 100%不等，0 时使颜色完全变暗，100%时完全变白。
*   **HSLA(色相、饱和度、明度、Alpha):**

    ```html
    $color: hsla(100, 60%, 60%, 0.7)
    ```

    这里，alpha 再次用于透明度&它的值从 0.0(透明)到 1.0(不透明)不等。