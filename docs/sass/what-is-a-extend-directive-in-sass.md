# 什么是 SASS 中的@extend 指令？

> 原文:[https://www . geesforgeks . org/什么是延伸指令 in-sass/](https://www.geeksforgeeks.org/what-is-a-extend-directive-in-sass/)

[Sass](https://www.geeksforgeeks.org/sass-introduction/) 是“语法上很棒的样式表”的缩写。它是级联样式表(CSS)的升级版，也是编写 CSS 的流行预处理程序之一。

@extend 是 Sass 中的一个关键字，它允许用户从一个选择器到另一个选择器共享一组 CSS 属性。这对于重用样式和使样式表更加模块化非常有用。它存在于 CSS 的所有三个预处理器中。

**扩展指令**的工作

Sass 在扩展选择器时使用智能统一。以下是规则:

*   If two selectors match in every respect, it will combine them together.
*   It prunes and reduces redundant selectors while still ensuring that their specificity is greater than or equal to that of expanders.
*   It knows how to deal with combiners, universal selectors and pseudo-classes containing selectors.
*   It also tries to mix complex selectors so that they continue to work independently of the nesting order of HTML elements.
*   It ensures that selectors that cannot target any element are not generated.

**扩展和混合的区别**

这是每个人从萨斯开始都会遇到的一个普遍问题。根据文档，以下要点可用于消除混淆:

*   When you must express the relationship between related classes (also called semantic classes), it is recommended to use @extend.
*   When there is no relationship between style collections, it is recommended to use mixins. In this way, you can customize it by accepting parameters. This makes it easy to configure and can be used in different environments.

**扩展范围和占位符选择器**

*   **扩展范围:** Sass 可以说有上游流。这使得它的规则可以预测，也容易理解。当一个样式表扩展一个选择器时，效果将只出现在上游的模块上，这些模块是使用@use 或@forward 规则加载的，同样也是以上游的方式加载的。这也称为扩展范围。

*   **占位符选择器:**占位符选择器，正如其名称所描述的，用作样式的占位符。当你想要它在 CSS 输出中的扩展版本，但不要样式本身时，它们就开始发挥作用了。用作占位符选择器的选择器以百分比(%)开头，不像一般的选择器以点(.)开头。).

下面的例子演示了@extend 指令。

**示例 1:** 假设您有两个类，背景图像和轮廓图像，并且都需要一些常见的样式。可以使用@extend 指令，如本例所示。

```html
.backgroundImage{
    border-radius:50%;
    height:100px;
    width:100px;
}

.profileImage{
    @extend .backgroundImage;
    border:none;
}
```

**输出:**这将使编译器获得以下 CSS 示例。

```html
.backgroundImage, .profileImage {
  border-radius: 50%;
  height: 100px;
  width: 100px;
}

.profileImage {
  border: none;
}
```

**示例 2:** 在这个示例中，我们将使用@extend 指令扩展多个类。

```html
.backgroundImage{
    border-radius:50%;
    height:100px;
    width:100px;
}

.profileImage{
    @extend .backgroundImage;
    border:none;
    filter: grayscale(100%);
}
.finalImage{
    @extend .profileImage;
}
```

**输出:**这个转换成下面的 CSS。

```html
.backgroundImage, .profileImage, .finalImage {
  border-radius: 50%;
  height: 100px;
  width: 100px;
}

.profileImage, .finalImage {
  border: none;
  filter: grayscale(100%);
}
```