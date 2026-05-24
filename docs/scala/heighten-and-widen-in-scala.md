# Scala 增高和加宽

> 原文:[https://www.geeksforgeeks.org/heighten-and-widen-in-scala/](https://www.geeksforgeeks.org/heighten-and-widen-in-scala/)

加高和加宽是使客户端能够将不同宽度的元素放置在彼此之上，或者将不同高度的元素放置在彼此旁边所需的功能。这些函数采用宽度或高度，并返回分别具有相同宽度或高度的元素。

例如，计算以下表达式将无法正常工作，因为组合元素中的第二行比第一行长:

```scala
new ArrayElement(Array("geeks")) above 
new ArrayElement(Array("forgeeks"))

```

同样，计算下面的表达式也不能正常工作，因为第一个 ArrayElement 的高度为 2，第二个 ArrayElement 的高度仅为 1:

```scala
new ArrayElement(Array("yes", "no")) beside 
new ArrayElement(Array("yes"))

```

下面的代码片段包含一个私有函数**加宽**，该函数取一个宽度并返回一个该宽度的元素。结果包含此元素的内容，该元素居中，并通过任何需要的空格向左和向右填充，以获得所需的宽度。同样，它包含另一个私有功能**加高**，在垂直方向执行相同的功能。加宽方法由上方的**调用，以确保放置在彼此上方的元素具有相同的宽度。同样，加高方法由**旁边的**调用，以确保彼此相邻放置的元素具有相同的高度。**

**示例:**

```scala
// Widen function
def widen(w: Int): Element =

// if w is less than or equal to the width of the Element
// then do nothing
if (w <= width) this 
else{

    // if w is greater than the width of the Element
    // then add padding of spaces

    // half padding on the left
    val left = elem(' ', (w - width) / 2, height)

    // half padding on the right
    var right = elem(' ', w - width - left.width, height)

    left beside this beside right
}

// Heighten function
def heighten(h: Int): Element =

// if h is less than or equal to the height of the Element
// then do nothing
if (h <= height) this 
else{

    // if h is greater than the height of the Element
    // then add padding of spaces

    // half padding on the top
    val top = elem(' ', width, (h - height) / 2)

    // half padding at the bottom
    var bot = elem(' ', width, h - height - top.height)

    top above this above bot
}
```