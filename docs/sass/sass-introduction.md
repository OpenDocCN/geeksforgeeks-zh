# SASS |简介

> 原文:[https://www.geeksforgeeks.org/sass-introduction/](https://www.geeksforgeeks.org/sass-introduction/)

**Sass** 是语法上很棒的样式表的简称。它是级联样式表的升级。Sass 是一个 CSS 预处理器。它完全兼容 CSS 的每个版本。Sass 减少了 CSS 的重复，因此节省了时间。它由汉普顿·卡特林设计，娜塔莉·韦森鲍姆于 2006 年开发。Sass 可以免费下载和使用。

**先决条件:**

*   超文本标记语言
*   半铸钢ˌ钢性铸铁(Cast Semi-Steel)

**工作:**网络浏览器不理解 Sass 代码本身。这就是为什么你需要一个萨斯预处理器来把萨斯代码变成简单的标准 CSS。
以上过程称为**运输**。所以，你需要给 transpiler 一些 Sass 代码，然后作为回报，拿回一些 CSS 代码。

**注:** Transpiling 是将一种语言的源代码输入，翻译成另一种语言的输出的术语。

**文件类型:**所有萨斯文件必须有`".scss"`文件扩展名。

**评论:**萨斯支持标准 CSS 评论`" /* comment */ "`，同时也支持线内评论`"// comment"`。

**示例:**

```html
/* Define fonts using variables */
$font_1: Algerian;
$font_2: Times New Roman;

.main {
    font: $font_1;
}
```

这将导致以下 CSS 输出:

```html
/* Define fonts using variables */
.main {
    font: Algerian;
}

```

**系统要求和 SASS 的安装:**

*   **操作系统:** Sass 是平台无关的。
*   **浏览器支持:** Sass 在 Edge/IE(来自 IE 8)、Firefox、Chrome、Safari、Opera 中工作。
*   **编程语言:** Sass 基于 Ruby。

有关萨斯和安装的更多信息，请访问官方萨斯网站[https://sass-lang.com/](https://sass-lang.com/)

**萨斯的一个基本例子。**假设一个网站基本上有 3 种字体。如果不得不一次又一次地写同样的字体风格，那就乱套了。您可以一次又一次地使用下面的 Sass，而不是编写字体值。
T3】例:

```html
$font_1: Algerian;
$font_2: Times New Roman;
$font_3: Serif;

.main  {
    font: $font_1;
}

.menu-1 {
    font: $font_2;
}

.menu-2 {
    font: $font_3;
}
```

这将导致以下 CSS 输出:

```html
.main {
    font: Algerian;
}

.menu-1 {
    font: Times New Roman;
}

.menu-2 {
    font: Serif;
}

```