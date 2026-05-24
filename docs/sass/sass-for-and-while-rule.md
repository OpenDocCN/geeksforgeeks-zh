# SASS @for 和@while 规则

> 原文:[https://www.geeksforgeeks.org/sass-for-and-while-rule/](https://www.geeksforgeeks.org/sass-for-and-while-rule/)

**@for rule** 用于从一个数字到另一个数字向上或向下计数，并检查该部分中给定范围内的每个数字。每个数字都被赋予一个给定的变量名。为了排除最后一个数字，使用**到**，为了包含它，使用**到。**

**语法:**

```html
@for <variable> from <expression> to <expression> {
    ... 
}
```

**和**

```html
@for <variable> from <expression> through <expression> {
    ... 
}
```

**例:**

```html
$gfg: green;

@for $i from 1 through 5 {
  ul:nth-child(2n + #{$i}) {
    background-color: darken($gfg, $i * 5%);
  }
}
```

**输出:**

```html
ul:nth-child(2n+1) {
  background-color: #006700;
}

ul:nth-child(2n+2) {
  background-color: #004d00;
}

ul:nth-child(2n+3) {
  background-color: #003400;
}

ul:nth-child(2n+4) {
  background-color: #001a00;
}

ul:nth-child(2n+5) {
  background-color: #000100;
}

```

**@while 规则**仅当给定表达式为真时才分析该部分。该节继续编译，直到它返回 false，然后该节停止编译。

**语法:**

```html
@while <expression> { 
    ... 
}
```

**例:**

```html
@function scale-below($value, $base, $ratio: 2) {
  @while $value > $base {
    $value: $value / $ratio;
  }
  @return $value;
}

$normal-font-size: 22px;
gfg {
  font-size: scale-below(20px, 12px);
}
```

**输出:**

```html
gfg {
  font-size: 10px;
}

```

**真与假:**其他一些值也可以用在任何地方，允许真或假。值为假和空意味着 Sass 认为它们显示为假，这导致条件失败。其他值都是真的。所以萨斯认为他们有条件成功。有些语言认为虚假的值比虚假和空值多，不包括列表中的 Sass。空字符串、空列表和数字 0 在 Sass 中都被认为是真理。