# 使用 HTML 和 CSS 设计一个联系我们的页面

> 原文:[https://www . geesforgeks . org/design-a-contact-us-page-using-html-and-CSS/](https://www.geeksforgeeks.org/design-a-contact-us-page-using-html-and-css/)

对于不懂 HTML 和 CSS 的人来说，创建一个有吸引力的页面似乎很难。如果有人不知道使用 CSS，那么他们将无法使页面看起来更好或更有吸引力。因此，本文的主要焦点将是 CSS 的实现。

**创建结构:**在本节中，我们将使用一些标签来创建网页的简单结构，如< li >和<部分>。这将有助于我们创建一个简单的网页，我们可以通过运行以下代码进行检查:

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<head>
    <title>Contact Us page</title>
</head>

<body>
    <nav class="navbar background">

        <!-- It is used to create the list of
            items that will be displayed-->
        <ul class="nav-list">
            <li><a href="#Home">Home</a></li>
            <li><a href="#Topics">Topics</a></li>
            <li><a href="#ContactUs">Contact Us</a></li>
            <li><a href="#AboutUs">About Us</a></li>
        </ul>

        <!-- This is to create the search bar
            and the button-->
        <div class="rightNav">
            <input type="text" name="search" id="search">
            <button class="btn btn-sm">Search</button>
        </div>
    </nav>
    <section class="background firstsection">
        <div class="box-main">
            <div class="firstHalf">

                <!-- The class text-big is used to make
                    the text bigger than the text which
                    will be written after this -->
                <p class="text-big">Contact Us</p>

                <!-- The class text-small is used to make
                    the text smaller and have a distinction
                    between the text-big -->
                <p class="text-small">
                    You can Contact Us if you face any problem
                </p>

                <!-- To make the text appear little below
                    the text that has the class of
                    text-small -->
                <br>
                <p class="center" style=
                    "text-decoration:none;color:white;">
                    Click on the below options to Contact us
                </p>

            </div>
        </div>
    </section>

    <section class="service">

        <!-- Heading-->
        <h1 class="h-primary center"
            style="margin-top:30px;">
            Options to Contact
        </h1>

        <div id="service">
            <div class="box">

                <!-- Form -->
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20201231132740/Capture.PNG">
                <!-- To make the text of the image be
                    seprateable we will use br -->
                <br>

                <!-- To make the text to be displayed at
                    the center of the box, we will use
                    center class -->
                <p class="center">
                    People can fill up the form
                    and send us the problem
                </p>

            </div>

            <div class="box">

                <!-- Email -->
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20201231132740/Capture.PNG">
                <!-- To make the text of the image be
                    seperatable we will use br -->
                <br>

                <!-- To make the text to be displayed at
                    the center of the box, we will use
                    center class -->
                <p class="center">
                    Use this Email to send us
                    about the problem faced
                </p>

            </div>

            <div class="box">

                <!-- Toll Free Number -->
                <img src=
"https://media.geeksforgeeks.org/wp-content/uploads/20201231132740/Capture.PNG">
                <!-- To make the text of the image
                    be seperatable we will use br -->
                <br>

                <!-- To make the text to be displayed at
                    the center of the box, we will use
                    center class -->
                <p class="center">
                    Toll Free Number:+1800 200 300 400
                </p>

            </div>
        </div>
    </section>

    <footer class="background">
        <p class="text-footer">
            Copyright @-All rights are reserved
        </p>

    </footer>
</body>

</html>
```

**CSS 设计:**我们将使用 CSS 来设计简单的界面页面。在这里，创建这个页面有趣的部分是使用相同的背景为导航栏和网页的背景。在页脚中，我们也将使用相同的背景，通过使用我们已经用于给网页和导航栏提供背景图像的类。网页的另一个有趣之处是导航条固定在一个点上，所以当用户滚动网页时，他们会发现导航条固定在一个地方。

**CSS 代码:**

## 半铸钢ˌ钢性铸铁(Cast Semi-Steel)

```html
<style>

    /* Here * is used to make the margin
    and padding to be at 0*/
    * {
        margin: 0;
        padding: 0;
    }

    html {
        scroll-behaviour: smooth;
    }

    :root {
        --navbar-height: 59px;
    }

    /* This is for the logo of the company */
    .logo {
        width: 20%;

        /* It is used to make the logo to
        be displayed along with the ul
        list horizontally */
        display: flex;
        justify-content: center;
        align-items: center;
    }

    .logo img {
        width: 33%;

        /* The logo image will have a border,
        that has a width of 2px and the
        color of the border is white */
        border: 2px solid white;

        /* Now we will add a border radius of
        5px to make the logo image circular*/
        border-radius: 50px;
    }

    .navbar {

        /* To make all those logo image and
        the list to be displayed horizontally */
        display: flex;
        align-items: center;
        justify-content: center;
        position: sticky;
        top: 0;

        /* When we will take our mouse to
        those lists or image the cursor will
        be pointer */
        cursor: pointer;
    }

    .nav-list {
        width: 70%;

        /* It is to display the list in
            horizontal*/
        display: flex;
    }

    .nav-list li {

        /* This will remove the style
        of bulleted list */
        list-style: none;

        /* This will create a space
        between the items */
        padding: 2px 6px;
    }

    .nav-list li a {

        /* This is to remove the underline
        of the text that appears when we
        use the anchor tag */
        text-decoration: none;

        /* This is to display the color
        of those anchor text white*/
        color: white;
    }

    /* When the user will point their
    mouse towards any anchor text they
    will find a different color */

    .nav-list li a:hover {
        color: grey;
    }

    .rightNav {
        width: 50;

        /* We will find the search box along
        with the search button will be shifted
        to right */
        text-align: right;
    }

    #search {
        padding: 5px;

        /* The size of the font that will be
        appearing in the search box when the
        user will try to search something */
        font-size: 17px;

        /* The border of the search box has
        a width of 2px and the type of the
        border is solid. The color of the
        border will be grey */
        border: 2px solid grey;

        /* We will use a border-radius to make
        the search box give a better looking
        shape than rectangular shape */
        border-radius: 9px;
    }

    .background {

        /* The background image will change
        whenever we load the page */
        background-color: grey;

        /* This will make the background that
        have been added will be darken */
        background-blend-mode: darken;
        background-size: cover;
    }

    .firstsection {

        /* It is to make the height of the
        viewport to be 100 */
        height: 100vh;
    }

    .box-main {

        /* This is to display the contact us
        and the sentences below it to be
        displayed in flex */
        display: flex;
        justify-content: center;
        align-items: center;

        /* This is to display the text to have
        a color of white */
        color: white;
        max-width: 50%;

        /* Now we will set the margin to auto */
        /* This will make all the text to be
        displayed at the center of the page */
        margin: auto;

        /* This will make the text to display
        at the center of the page vertically */
        height: 80%;
    }

    .firstHalf {
        width: 75%;
        display: flex;

        /* It is to specify the direction of
        the flexible items */
        flex-direction: column;
        justify-content: center
    }

    .firstHalf img {
        display: flex;
        border-radius: 9050px;
    }

    /* This is used to make the text
    to appear bigger */

    /* Now we have used a font here to
    distinguish itself from the next text */
    .text-big {
        font-family: 'Piazzolla', serif;

        /* The text to have a style of bold */
        font-weight: bold;

        /* The size of the text to be appearing
        as bigger to distinguish itself from
        the text in the class text-small */
        font-size: 41px;

        /* The text to be aligned at center */
        text-align: center;
    }

    .text-small {
        font-family: 'Sansita Swashed', cursive;
        font-size: 18px;
        text-align: center;
    }

    #service {
        margin: 34px;
        display: flex;
    }

    #service .box {

        /* This is for the background of the box */
        /* To make all the boxes seperatable
        from each other */
        padding: 45px;
        margin: 3px 6px;

        /* To make the box have a better
        looking than rectangular shape */
        border-radius: 28px;
    }

    /* This is for the image that we have
    used in the box */
    #service .box img {
        margin-top: 20px;

        /* This is for the height of the image
        that is required for the page */
        height: 100px;
        margin: auto;
        display: block;

        /* This is to make the image obtain
        a circular shape */
        border-radius: 200px;
    }

    #service .box p {

        /* This is for the text that we have
        written to define the image that we
        have used */
        font-family: sans-serif;

        /* This is to make the text to be
        aligned at center */
        text-align: center;
    }

    .btn {
        padding: 8px 20px;
        margin: 7px 0;

        /* The radius of the border will have
        a width of 2px and the type of border
        will be solid. The border will have a
        border of white depending on what type
        of image we have used as background */
        border: 2px solid white;

        /* Here we have used border-radius to
        make the search button appear better */
        border-radius: 8px;

        /* To make the button have the color
        of background */
        background: none;

        /* To make the text of the button
        have the color of white */
        color: white;
        cursor: pointer;
    }

    .btn-sm {
        padding: 6px 10px;
        vertical-align: middle;
    }

    /* This is used here in case if we want
    to make the text appear at center */

    .center {
        text-align: center;
    }

    .text-footer {
        text-align: center;
        padding: 30px 0;
        font-family: 'Ubuntu', sans-serif;
        display: flex;
        justify-content: center;
    }
</style>
```

结合以上两段代码，使用 HTML 和 CSS 制作一个联系我们的页面。

**输出:**

![](img/257ad3adab777c761399366459e04caf.png) ![](img/4ce1ba93fb8f3ce505d81f0738173e74.png)

**运行代码的支持浏览器:**

*   谷歌 Chrome
*   微软边缘
*   火狐浏览器
*   歌剧
*   旅行队