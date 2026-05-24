# 使用 HTML 和 CSS 设计网页

> 原文:[https://www . geesforgeks . org/design-a-web-page-use-html-and-CSS/](https://www.geeksforgeeks.org/design-a-web-page-using-html-and-css/)

对于那些不是 CSS 专家的人来说，创建一个有吸引力的页面会很困难。没有使用 CSS，你将无法使网页，更有吸引力。所以为了制作一个网页，我们需要有 HTML 和 CSS 的知识。在本文中，主要的焦点将是实现 CSS。为了设计一个网页，我们需要首先创建一个 HTML 网页结构。

**创建结构:**在本节中，我们将使用< li >和<节>标签创建网页的简单结构。因此，这将创建一个简单的接口，您可以通过运行以下代码来进行检查。

**HTML 代码:**

## 超文本标记语言

```html
<!DOCTYPE html>

<html>

<head>
    <title>
        Simple web Development Template
    </title>
</head>

<body>
    <nav class="navbar background">
        <ul class="nav-list">
            <div class="logo">
                <img src="logo.png">
            </div>
            <li><a href="#web">Web Technology</a></li>
            <li><a href="#program">C Programming</a></li>
            <li><a href="#course">Courses</a></li>
        </ul>

        <div class="rightNav">
            <input type="text" name="search" id="search">
            <button class="btn btn-sm">Search</button>
        </div>
    </nav>

    <section class="firstsection">
        <div class="box-main">
            <div class="firstHalf">
                <h1 class="text-big" id="web">
                    Web Technology
                </h1>

                <p class="text-small">
                    HTML stands for HyperText Markup
                    Language. It is used to design
                    web pages using a markup language.
                    HTML is the combination of Hypertext
                    and Markup language. Hypertext
                    defines the link between the web
                    pages. A markup language is used
                    to define the text document within
                    tag which defines the structure of
                    web pages. HTML is a markup language
                    that is used by the browser to
                    manipulate text, images, and other
                    content to display it in the required
                    format.
                </p>

            </div>
        </div>
    </section>

    <section class="secondsection">
        <div class="box-main">
            <div class="secondHalf">
                <h1 class="text-big" id="program">
                    C Programming
                </h1>
                <p class="text-small">
                    C is a procedural programming language.
                    It was initially developed by Dennis
                    Ritchie as a system programming
                    language to write operating system.
                    The main features of C language include
                    low-level access to memory, simple set
                    of keywords, and clean style, these
                    features make C language suitable for
                    system programming like operating system
                    or compiler development.
                </p>

            </div>
        </div>
    </section>

    <section class="section">
        <div class="paras">
            <h1 class="sectionTag text-big">Java</h1>

            <p class="sectionSubTag text-small">
                Java has been one of the most
                popular programming language
                for many years. Java is Object
                Oriented. However it is not
                considered as pure object oriented
                as it provides support for primitive
                data types (like int, char, etc) The
                Java codes are first compiled into byte
                code (machine independent code). Then
                the byte code is run on Java Virtual
                Machine (JVM) regardless of the
                underlying architecture.
            </p>

        </div>

        <div class="thumbnail">
            <img src="img.png" alt="laptop image">
        </div>
    </section>

    <footer class="background">
        <p class="text-footer">
            Copyright ©-All rights are reserved
        </p>

    </footer>
</body>

</html>
```