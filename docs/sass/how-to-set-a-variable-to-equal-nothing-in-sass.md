# 如何在 SASS 中设置一个变量等于零？

> 原文:[https://www . geesforgeks . org/如何将变量设置为等于零/in-sass/](https://www.geeksforgeeks.org/how-to-set-a-variable-to-equal-nothing-in-sass/)

变量就像一个容器，我们可以在其中存储一些数据，然后在以后的代码中重用它。因此，人们可以定义它一次，然后在任何地方重用它。变量的值可以在代码中随时更改，并且在下次使用时会在任何地方生效。

可能会有这样一种情况，我们必须在 SASS 中声明一个等于零的变量。这可以通过两种方式实现:

*   变量可以通过将其值设为“null”来声明。使用“null”的好处是，当与属性一起使用时，它将在编译后的 CSS 中完全消失。
*   也可以通过将其值设为“false”来声明变量。这种类型的值没有任何意义，因此不会影响属性。

以下示例演示了这种方法:

**HTML 代码:**

## 超文本标记语言

```html
<nav>
  <ul class="navigation">
     <li><a href="#">About us </a></li>
     <li><a href="#">blogs </a></li>
     <li><a href="#">contact </a></li>
  </ul>
  <div class="button">
    <a class="btn-main" href="#">Sign up</a>
    <a class="btn-hot" href="#">log in</a>
  </div>
</nav>
```

**带有“空”值的** **变量的 SASS 文件:**这里名为 color 的变量被赋予“空”值。然后，它被传递给一个属性。

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
*
  margin:0
  padding:0

$color: null

nav
  margin:30px
  background-color: $color
```

**输出:**这是变量为空值的编译后的 CSS 文件。保存空值的变量在最终文件中消失，因此对输出没有影响。

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
*{
  margin: 0;
  padding: 0;
}

nav {
  margin: 30px;
}
```

**带有“假”值的变量的 SASS 文件:**这里名为 color 的变量被赋予了“假”值。然后，它被传递给一个属性。

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
*
  margin:0
  padding:0

$color: false

nav
  margin:30px
  background-color: $color
```

**输出:**这是编译后的 CSS 文件，变量的值为假。这里，名为 color 的变量的值实际上显示在指定的属性中，但是由于该值不合适，因此不会影响输出。

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
* {
  margin: 0;
  padding: 0;
}

nav {
  margin: 30px;
  background-color: false;
}
```