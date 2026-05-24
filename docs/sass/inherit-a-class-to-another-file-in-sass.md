# 在 Sass 中继承一个类到另一个文件

> 原文:[https://www . geesforgeks . org/inherit-a-class-to-other-file-in-sass/](https://www.geeksforgeeks.org/inherit-a-class-to-another-file-in-sass/)

Sass 或语法上令人敬畏的样式表是一个 CSS 预处理器，它赋予了 CSS 普通 CSS 所没有的能力。它提供了使用表达式、变量、嵌套、混合(Sass 形式的函数)、继承等的能力。其他著名的 CSS 预处理器例子包括 Less 和 Stylus，但 Sass 更受欢迎。

Sass 包括两种语法:

*   SCS(sasy CSS)
*   厚颜无耻

**SCSS 或飒爽 CSS**

SCSS 使用*。scss* 的语法和它非常类似于普通的 css。SCSS 完全符合 CSS。SCSS 可以被认为是 CSS 的超集。任何有效的 CSS 样式都是有效的 SCSS。由于与 CSS 的相似性，开始使用它所需的时间更少。

**示例:**

```html
$heading-color: #e94e1b; //Using Sass Variables
h4 {
    color: $heading-color;
}
```

**缩进语法或 Sass**

这是 Sass 的原始语法。它使用*。sass* 文件扩展名。它使用了 Sass 的所有特性，但是它没有使用大括号，而是使用缩进来描述文档的格式。它不完全符合 CSS。

**例**

```html
$heading-color: #e94e1b; 
h4
  color: $heading-color
```

**@导入并@使用:**

单个 CSS 文件最终会变得更大，维护大型样式表将是一项艰巨的工作。因此，如果有一种方法可以将类分成不同的文件，那就更容易了。因此只能导入必要的文件。这样样式表会更小，维护也更容易。样式表还将维护 *DRY(不要重复自己)*规则。

**方法 1:** 要将另一个样式表导入样式表，使用 *@import* 关键字。要导入的 CSS 或 Scss 文件可以位于同一文件夹或互联网上的其他位置。

**语法:**

```html
@import 'file-name';
@import url('url of the stylesheet')

```

**例**

```html
@import './buttons.scss';
@import url('https://example.com/css/breadcrumbs.scss');
```

**编译好的 CSS**

> @ import URL(' https://maxcdn . bootstrapcdn . com/bootstrap/3 . 3 . 7/CSS/bootstrap-theme . min . CSS ')；
> 。BTN-大{
> 边界半径:3rem
> 边框:4px 纯黑；
> 背景:黑色；
> 颜色:白色；
> 宽度:20 雷姆；
> 身高:10 雷姆；
> 显示:flex
> 对齐-项目:居中；
> 狡辩——内容:中心；
> }

将一个 CSS 文件导入到另一个文件中是一个可行的解决方案。但是萨斯已经否决了*@导入*，最终会移除。现在，萨斯不再使用 *@import* ，而是支持 *@use* ，因为 CSS 还有一个 *@import* 功能，使用 *@import* 还有一些其他的主要缺点，这是另一篇文章的主题。

**方法 2:***@ use*必须与命名空间一起使用。假设位于同一目录的文件*按钮*有一个名为*原色*的*颜色*变量。要在其他文件中使用该变量，将遵循以下语法。

**语法:**

```html
@use 'file-name';
```

**示例:**

```html
@use 'buttons';

.card {
    color: buttons.$primary-color;
}
```

**编译 CSS:**

```html
.btn-large {
  border-radius: 3rem;
  border: 4px solid black;
  background: black;
  color: white;
  width: 20rem;
  height: 10rem;
  display: flex;
  align-items: center;
  justify-content: center;
}
```

使用命名空间是因为 *@import* 中存在命名冲突。如果两个导入文件包含两个不同的同名变量， *@import* 将强制使用上次导入文件中定义的变量值。

*@use* 还提供了使用用户定义的名称空间的能力。

**示例:**

```html
@use 'buttons' as btn;

.card {
    color: btn.$primary-color;
}
```

作为关键字的*允许定义自定义名称空间。*

这里需要注意的一点是 VS 代码上的 Live Sass 编译器是基于 *LibSass* 和 *LibSass* 的，目前不支持 *@use* 功能。所以还是用*镖萨斯*比较好，一般是第一个实现新功能的。安装*镖刀*很容易。此帖[此处](https://sass-lang.com/install)描述步骤。

**继承其他职业的风格**

上一节简要描述了如何使用*@导入*和*@使用*操作符导入和使用存储在另一个文件中的样式。要从另一个类或 id 继承样式，可以使用 *@extend* 关键字。我们来看一个例子，假设 buttons 类有一个*颜色:绿色；和不透明度:. 5；*属性，现在要将这些样式继承到另一个类中，将使用 *@extend* 关键字。

**示例:**

**按钮. scss 文件**

```html
/* buttons.scss file */
.btn {
  color: red;
  opacity: 0.5;
}
```

**style . SCS 档案**

```html
/*style.scss file
where the style is to be inherited */
@use 'buttons';

.new-btn {
  @extend .btn;
}
```

所以，上面的代码将继承*的属性。btn* 级到*级。新增-btn* 类。

现在，让我们看看编译后的 CSS 文件。

**编译好的 CSS**

```html
/* style.css */
.btn, .new-btn {
  color: red;
  opacity: 0.5;
}

```

这里需要注意的一点是*的风格。btn* 类不会被复制到 *new-btn* 类，而是用逗号分隔原始选择器，从而减少重复代码。

**结论**

所以，本文对 Sass 中使用的 *@include、@use* 和 *@extend* 关键词进行了简要描述。继承也可以使用 mixins 来实现。要了解 mixin，您可以查看[这篇]((https://www.geeksforgeeks.org/sass-mixin-and-include/)文章。虽然如果样式不带任何参数，最好使用 *@extend* 方法。