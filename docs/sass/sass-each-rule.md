# 在每条规则上斗嘴

> 原文:[https://www.geeksforgeeks.org/sass-each-rule/](https://www.geeksforgeeks.org/sass-each-rule/)

**@每个规则**用于为列表中的每个元素或每对地图发出样式或评估代码。对于有一些差异的重复样式来说，这是最有利的。对于已分配给所提供变量名的列表或映射对的每个元素，都会对该部分进行评估。

**语法:**

```html
@each <variable> in <expression> {
   ... 
}
```

**示例:**

```html
$sizes: 20px, 30px, 100px;
@each $size in $sizes {
  .gfg-#{$size} {
    font-size: $size;
    height: $size;
    width: $size;
  }
}
```

**输出:**

```html
.gfg-20px {
  font-size: 20px;
  height: 20px;
  width: 20px;
}

.gfg-30px {
  font-size: 30px;
  height: 30px;
  width: 30px;
}

.gfg-100px {
  font-size: 100px;
  height: 100px;
  width: 100px;
}

```

通过迭代映射的每个键/值对，**@每个**规则也可以用于映射。

**语法:**

```html
@each <variable>, <variable> in <expression> { 
   ... 
}
```

**示例:**在本例中，键被分配给第一个变量名，元素被分配给第二个。

```html
$colors: (arial: black, sans-serif: green, algerian: gray);

@each $name, $font in $colors {
  .font-#{$name}:before {
    background-color: white;
    font-family: $name;
    color: $font;
  }
}
```

**输出:**

```html
.font-arial:before {
  background-color: white;
  font-family: arial;
  color: black;
}

.font-sans-serif:before {
  background-color: white;
  font-family: sans-serif;
  color: green;
}

.font-algerian:before {
  background-color: white;
  font-family: algerian;
  color: gray;
}

```

**析构:**每个规则还可以自动将列表中的变量分配给内部列表中的每个值。由于变量与内部列表的结构相匹配，因此称为析构。每个变量名都分配给列表中相应位置的值，如果列表中没有足够的值，则为 null。

**语法:**

```html
@each <variables...> in <expression> {  
   ... 
}
```

**示例:**在本例中，键被分配给第一个变量名，元素被分配给第二个。

```html
$colors: 
  arial black 10px,
  sans-serif green 12px, 
  algerian gray 20px;

@each $name, $font, $size in $colors {
  .font-#{$name}:before {
    background-color: white;
    font-family: $name;
    color: $font;
    font-size: $size;
  }
}
```

**输出:**

```html
.font-arial:before {
  background-color: white;
  font-family: arial;
  color: black;
  font-size: 10px;
}

.font-sans-serif:before {
  background-color: white;
  font-family: sans-serif;
  color: green;
  font-size: 12px;
}

.font-algerian:before {
  background-color: white;
  font-family: algerian;
  color: gray;
  font-size: 20px;
}

```