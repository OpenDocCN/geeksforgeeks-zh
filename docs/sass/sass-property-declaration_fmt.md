# SASS属性声明

> 原文: [https://www.geeksforgeeks.org/sass-property-declaration/](https://www.geeksforgeeks.org/sass-property-declaration/)

SASS中的属性声明用于定义匹配选择器的元素需要如何设置样式。除此之外，SASS还在属性声明中添加了一些额外的特性，以便于编写和自动化它们。
首先，声明值可以是任何可以被求值并包含在结果中的表达式。

**例:**

```html
.rectangle
  $side: 80px
  width: $side / 2
  length: $side
  border-radius: $side / 4
```

这将给出以下CSS输出:

```html
.circle {
  width: 40px;
  length: 80px;
  border-radius: 20px;
}
```

## 内插

一份属性声明的名称可能包含[内插](https://www.geeksforgeeks.org/sass-interpolation/#:~:text=Interpolation%20is%20a%20new%20principle,%20wrap%20the%20expression%20using%20%23%7B%20%7D.&text=where%20%E2%80%A6..%20represents%20some%20text.&text=Interpolation%20in%20SASS%20expressions%20always,%20string%20is%20quoted%20or%20not.)。这允许SASS根据我们的需求动态生成属性。用户还可以插入整个属性名。

**例:**

```html
@mixin create($property, $value, $lhs) 
  @each $create in $lhs 
    -#{$create}-#{$property}: $value
  #{$property}: $value

.gfg 
  @include create(font, times new roman, moz webkit)
```

这将给出以下CSS输出:

```html
.gfg {
  -moz-font: times new roman;
  -webkit-font: times new roman;
  font: times new roman;
}
```

## 嵌套

各种CSS属性以相同的前缀开始。例如`margin-bottom`、`margin-top`、`margin-left`、`margin-right`。SASS借助[嵌套](https://www.geeksforgeeks.org/sass-nesting/)使它更容易，冗余更少。外部属性名自动添加到内部属性名中，并用`-`分隔。

**例:**

```html
.fonts 
  transition-duration: 4s
  font: 
    size: 4px
    family: times new roman
    color: green

&:hover  
    font: 
      size: 36px
      color: black
```

这将给出以下CSS输出:

```html
.fonts {
  transition-duration: 4s;
  font-size: 4px;
  font-family: times new roman;
  font-color: green;
}
.fonts:hover {
  font-size: 36px;
  font-color: black;
}
```

这些CSS属性中有一些使用命名空间作为属性名的简写版本。对于这些，您可以编写简写值和更显式的嵌套版本。

**例:**

```html
.gfg
  margin: auto
    left: 5px
    right: 5px
    bottom: 10px
    top: 2px
```

这将给出以下CSS输出:

```html
.gfg {
  margin: auto;
  margin-left: 5px;
  margin-right: 5px;
  margin-bottom: 10px;
  margin-top: 2px;
}
```

## 隐藏声明

在某些情况下，当你只需要在某些条件下实现一个属性时，也就是只有当某些属性跟随时，你才可以使用SASS的隐藏声明。

**例:**

```html
$times_new_roman: true
$arial: false

.gfg 
  font-size: 5px
  color: if($times_new_roman, green, null)
  color: if($arial, black, null)
```

这将给出以下CSS输出:

```html
.gfg {
  font-size: 5px;
  color: green;
}
```