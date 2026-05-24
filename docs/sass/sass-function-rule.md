# 萨斯@功能规则

> 原文:[https://www.geeksforgeeks.org/sass-function-rule/](https://www.geeksforgeeks.org/sass-function-rule/)

函数可以对可在整个样式表中重用的 **SassScript** 值定义复杂的操作。它使得以某种可读的方式抽象出常见的公式和行为变得更加容易。可以使用**@函数** at-rule 定义函数。

**语法:**

```html
@function <function name>(<arguments...>) {
 ... 
}
```

函数名可以是任何 *Sass* 标识符。它必须只包含通用语句，以及指示使用函数调用结果的值的 **@return** at-rule。正常的 CSS 函数用于调用函数。

**示例:**

```html
@function power($base, $expo)
  $result: 1
  @for $_ from 1 through $expo
    $result: $result * $base
  @return $result

.sidebar
  float: right
  margin-left: power(6, 2) * 2px
```

**输出:**

```html
.sidebar {
  float: right;
  margin-left: 64px;
}

```

**参数:**参数允许函数的行为在每次被调用时被改变。参数在函数名后面的**@函数**规则中指定，如语法所示。它只是一个由括号或花括号包围的变量名列表。这些函数总是用相同数量的参数调用，这些参数在 *SassScript* 表达式中。这些表达式的值在函数体中作为相应的变量可用。

**参数类型:**

*   Optional Arguments:
    **Example:**

    ```html
    @function gfg($color, $amount: 100%) {
      $geeks: change-color($color, $hue: hue($color) + 180);
      @return mix($geeks, $color, $amount);
    }

    $primary-color: #ffffff;
    .header {
      background-color: gfg($primary-color, 80%);
    }
    ```

    **输出:**

    ```html
    .header {
      background-color: white;
    }

    ```

*   Arbitrary Arguments:
    **Example:**

    ```html
    $lengths: 50px, 30px, 100px;
    .gfg {
      width: max($lengths...);
    }
    ```

    **输出:**

    ```html
    .gfg {
      width: 100px;
    }

    ```

*   Keyword Arguments:
    **Example:**

    ```html
    $geeks: green;
    .banner {
      background-color: $geeks;
      color: scale-color($geeks, $lightness: +40%);
    }
    ```

    **输出:**

    ```html
    .banner {
      background-color: green;
      color: #1aff1a;
    }

    ```

**@ return:****@ return at-rule**给出被调用函数的结果。仅在*@功能*规则中有效，每个*@功能*必须以*@返回*结束。当调用 *@return* 时，立即结束函数并返回结果。提前返回对于处理边缘情况非常有用。在有效算法可用但没有将整个函数包装在 *@else* 块中的情况下，这也很有用。
**例:**

```html
@function add($numbers...) {
  $add: 0;
  @each $number in $numbers {
    $add: $add + $number;
  }
  @return $add;
}

.gfg {
  width: add(50, 30, 100);
}
```

**输出:**

```html
.gfg {
  width: 180;
}

```