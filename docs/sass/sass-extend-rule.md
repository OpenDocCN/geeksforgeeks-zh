# 萨斯@扩展规则

> 原文:[https://www.geeksforgeeks.org/sass-extend-rule/](https://www.geeksforgeeks.org/sass-extend-rule/)

Sass **@extend** 规则可以在一个类需要拥有另一个类的样式，以及自己特定的样式时使用。这条规则告诉 Sass，一个选择器应该从另一个选择器继承类。

**语法:**

```html
@extend <selector>
```

**例:**

## SASS

```html
.gfg
  border: 1px green
  background-color: black
  font-family: sans-serif

  &--geeks
    @extend .gfg
    border-width: 4px
```

**输出:**

```html
.gfg, .gfg--geeks {
  border: 1px green;
  background-color: black;
  font-family: sans-serif;
}
.gfg--geeks {
  border-width: 4px;
}

```

当一个类扩展另一个类时，Sass 样式是匹配扩展程序的元素，就好像它们也匹配被扩展的类一样。选择器不仅仅是在样式规则中单独使用。Sass 知道在选择器被使用的地方进行扩展。这确保了元素的样式与扩展选择器完全匹配。

**例:**

## SASS

```html
.gfg:hover
  border: 1px green
  background-color: black
  font-family: sans-serif

.gfg--geeks
  @extend .gfg
  border-width: 4px
```

**输出:**

```html
.gfg:hover, .gfg--geeks:hover {
  border: 1px green;
  background-color: black;
  font-family: sans-serif;
}
.gfg--geeks {
  border-width: 4px;
}

```

**规则的工作:****@扩展**规则更新包含扩展选择器的样式规则，使其包含扩展选择器。当扩展选择器时，Sass 通过从不生成像 **#main#footer** 这样不可能匹配任何元素的选择器来实现智能统一。它还确保了复杂的选择器是交错的，这样无论 HTML 元素以何种顺序嵌套，它们都可以工作。

智能统一也是通过尽可能修剪冗余选择器来完成的，同时仍然确保特异性大于或等于扩展器的特异性。简而言之，它智能地处理组合符、通用选择器和包含选择器的伪类。

**例:**

## CSS

```html
.content nav.sidebar
  @extend .gfg

/* This won't be extended, because 
  `p` is incompatible with `nav` */
p.gfg
  background-color: green
  color: white

/* There is no way to know whether
  `<div class="guide">` will be inside
   or outside `<div class="content">`,
   so Sass generates both to be safe */
.geeks .gfg
  border: 1px solid black
  border-radius: 4px

/* Sass knows that every element 
   matching "main.content" also 
   matches ".content" and avoids
   generating unnecessary 
   interleaved selectors */
main.content .gfg
  font-size: 2px
  font-family: sans-serif
```

**输出:**

```html
p.gfg {
  background-color: green;
  color: white;
}

.geeks .gfg, .geeks .content nav.sidebar, 
.content .geeks nav.sidebar {
  border: 1px solid black;
  border-radius: 4px;
}

main.content .gfg, main.content nav.sidebar {
  font-size: 2px;
  font-family: sans-serif;
}

```

使用选择器功能可以直接访问 Sass 的智能统一。selector.unify()函数返回一个与两个选择器的交集相匹配的选择器，而 selector.extend()函数的工作方式与 **@extend** 类似，但在单个选择器上。