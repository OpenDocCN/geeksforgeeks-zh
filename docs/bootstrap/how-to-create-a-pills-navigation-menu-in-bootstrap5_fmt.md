# 如何在 Bootstrap5 中创建药丸导航菜单？

> 原文: [https://www.geeksforgeeks.org/how-to-create-a-pills-navigation-menu-in-bootstrap5/](https://www.geeksforgeeks.org/how-to-create-a-pills-navigation-menu-in-bootstrap5/)

在本文中，我们将学习如何在 [Bootstrap 5 中制作药丸导航菜单。](https://www.geeksforgeeks.org/bootstrap-5-introduction/) 药丸是一个很好的导航风格，可以为您的网站实现，因为它增强了用户体验和您网站的导航流。创建药丸导航菜单既简单又容易，您所要做的就是包含正确的引导类，并了解这些类将执行什么功能。我们将讨论药丸导航有利于使用的所有情况。让我们一个接一个地开始。

有两种方法可以在 HTML 中应用引导:

*   通过使用引导 CDN 链接
*   从官方网站下载引导程序。

有关安装和配置过程的更多详细信息，请参考[引导介绍和安装](https://www.geeksforgeeks.org/bootstrap-part-1-introduction-and-installation/)一文。

## 创建简单药丸导航菜单

要创建简单药丸导航菜单，只需添加类`.nav-pills`和`.nav`到你的导航元素。`.nav`类是 bootstrap 中每个可用导航样式的基类。`.nav`类元素包裹在所有`.nav-link`类元素。`.nav-link`类应该赋予 navbar 中存在的所有链接元素。

**示例:** 本示例展示了药丸导航菜单的基本实现。

### HTML

```html
<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="UTF-8" />
      <meta http-equiv="X-UA-Compatible" 
         content="IE=edge" />
      <meta name="viewport" 
         content="width=device-width, 
         initial-scale=1.0" />
      <title>Pills navigation menu</title>
      <link href=
"https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
         rel="stylesheet"
         integrity=
"sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
         crossorigin="anonymous" />
   </head>
   <body>
      <nav class="nav nav-pills p-4 bg-dark">
         <a class="nav-link active bg-warning" 
            aria-current="true" 
            href="#">Home
         </a>
         <a class="nav-link text-warning" 
            href="#">About Us</a>
         <a class="nav-link text-warning" 
            href="#">Careers</a>
         <a class="nav-link text-warning" 
            href="#">Contact Us</a>
      </nav>
      <p class="p-4">
         GeeksforGeeks - A Computer Science portal for geeks. 
         It contains well written, well thought and well 
         explained computer science and programming
         articles, quizzes and practice/competitive 
         programming/company interview Questions.
      </p>

   </body>
</html>
```

**说明:**

*   `.p-4`类为元素实现填充。
*   `.bg-waring`实现了一个黄色阴影的背景颜色。
*   `.bg-dark`实现深色背景。
*   `.active`类描绘了用户当前对你网页的看法。
*   `.text-warning`将文本颜色设为黄色。

**输出:**

![](img/41380584645bafe49e26ef5390e142f9.png)

一个简单的药丸导航菜单

## 创建右对齐的药丸导航

要右对齐元素，可以使用`.ms-auto`类到元素。

**示例:** 在本例中，我们使用了`.ms-auto`类，注册被移到右侧。

### HTML

```html
<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="UTF-8" />
      <meta http-equiv="X-UA-Compatible" 
         content="IE=edge" />
      <meta name="viewport" 
         content="width=device-width, 
         initial-scale=1.0" />
      <title>Pills navigation menu</title>
      <link href=
"https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
         rel="stylesheet"
         integrity=
"sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
         crossorigin="anonymous"/>
   </head>
   <body>
      <nav class="nav nav-pills p-4 bg-dark">
         <a class="nav-link active bg-warning" 
            aria-current="true" 
            href="#">Home
         </a>
         <a class="nav-link text-warning" 
            href="#">About Us
         </a>
         <a class="nav-link text-warning" 
            href="#">Careers
         </a>
         <a class="nav-link text-warning" 
            href="#">Contact Us
         </a>
         <a class="nav-link text-warning ms-auto" 
            href="#">Sign up
         </a>
      </nav>
      <p class="p-4">
         GeeksforGeeks - A Computer Science portal for geeks.
         It contains well written, well thought and well
         explained computer science and programming
         articles, quizzes and practice/competitive
         programming/company interview Questions.
      </p>

   </body>
</html>
```

**输出:**

![](img/6003f6993469f4b4deb526ad1ea38d85.png)

右对齐药丸导航

## 创建横跨全屏的药丸导航

要制作占据整个屏幕宽度的药丸，我们可以使用`.nav-fill`类。这个类通过控制`.nav-link`项的宽度来填充整个屏幕。

**示例:** 在本例中，我们使用了`.nav-fill`类将创建横跨全屏的药丸导航。

### HTML

```html
<!DOCTYPE html>
<html lang="en">
   <head>
      <meta charset="UTF-8" />
      <meta http-equiv="X-UA-Compatible" 
         content="IE=edge" />
      <meta name="viewport" 
         content="width=device-width, 
         initial-scale=1.0" />
      <title>Pills navigation menu</title>
      <link href=
"https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
         rel="stylesheet"
         integrity=
"sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
         crossorigin="anonymous" />
   </head>
   <body>
      <nav class="nav nav-pills nav-fill p-4 bg-dark">
         <a class="nav-link active bg-warning" 
            aria-current="true" 
            href="#">Home
         </a>
         <a class="nav-link text-warning" 
            href="#">About Us
         </a>
         <a class="nav-link text-warning" 
            href="#">Careers
         </a>
         <a class="nav-link text-warning" 
            href="#">Contact Us
         </a>
      </nav>
      <p class="p-4">
         GeeksforGeeks - A Computer Science portal for geeks. 
         It contains well written, well thought and well explained
         computer science and programming articles, quizzes and
          practice/competitive programming/company interview
         Questions.
      </p>

   </body>
</html>
```

**输出:**

![](img/edec6046e2117503945855a65be6cece.png)

全屏显示药丸导航菜单

## 创建一个药丸导航，每个链接采用相同的宽度

从前面的例子来看，虽然导航链接横跨整个屏幕，但每个导航链接采用不同的宽度。在这个例子中，我们将看到如何跨越整个屏幕，每个导航链接占据相等的水平宽度/空间。对于等宽，我们使用类`.nav-justified`在导航元素中，而不是`.nav-fill`类。

**示例:** 本示例显示了对齐药丸导航菜单。

### HTML

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" 
          content="IE=edge" />
    <meta name="viewport" 
          content="width=device-width, 
                   initial-scale=1.0" />
    <title>Pills navigation menu</title>
    <link href=
"https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
            rel="stylesheet"
          integrity=
"sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
          crossorigin="anonymous" />
  </head>
  <body>
    <nav class="nav nav-pills nav-justified p-4 bg-dark">
      <a class="nav-link active bg-warning" 
         aria-current="true" 
         href="#">Home
      </a>
      <a class="nav-link text-warning" 
         href="#">About Us
      </a>
      <a class="nav-link text-warning" 
         href="#">Careers
      </a>
      <a class="nav-link text-warning" 
         href="#">Contact Us
      </a>
    </nav>
    <p class="p-4">
      GeeksforGeeks - A Computer Science portal for geeks. 
      It contains well written, well thought and well explained 
      computer science and programming articles, quizzes and
      practice/competitive programming/company interview
      Questions.
    </p>

  </body>
</html>
```

**输出:**

![](img/f8f1512323f171594b396462a996cb47.png)

对齐药丸导航菜单

**提示:** 使用 Chrome web developer 工具进行模式检查，看看区别。

## 创建固定药丸导航

固定导航是指当您滚动时，导航条将固定在屏幕顶部。要实现此功能，请添加类`.fixed-top`到导航元素。

**示例:** 该示例使用`.fixed-top`级来说明固定药丸导航条。

# 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" 
          content="IE=edge" />
    <meta name="viewport" 
          content="width=device-width, 
                   initial-scale=1.0" />
    <title>Pills navigation menu</title>
    <link href=
"https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
          rel="stylesheet"
          integrity=
"sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
          crossorigin="anonymous"/>
  </head>
  <body>
    <nav class="nav nav-pills fixed-top p-4 bg-dark">
      <a class="nav-link active bg-warning" 
         aria-current="true" 
         href="#">Home
      </a>
      <a class="nav-link text-warning" 
         href="#">About Us
      </a>
      <a class="nav-link text-warning" 
         href="#">Careers
      </a>
      <a class="nav-link text-warning" 
         href="#">Contact Us
      </a>
    </nav>

    <script
      src=
"https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js"
      integrity=
"sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM"
      crossorigin="anonymous" >
    </script>
  </body>
</html>
```

**输出:**

![](img/a4940c3787105334124ef28fe1015e33.png)

## 固定药丸导航

要用下拉导航创建药丸，我们需要包括`.dropdown`类到一个用`.dropdown`包装元素的`div`。`.dropdown-menu`类别和`.dropdown-toggle`类，它被赋予一个包裹在里面的导航链接元素。

`.dropdown-menu`类被赋予一个无序列表，该列表包含下拉菜单中出现的所有菜单内容。它还包括类`.dropdown-item`的元素表示菜单中出现的每个项目。

`data-bs-toggle`属性应赋予`.nav-link`元素的值为“dropdown”，点击时，我们将切换下拉视图。还有，`role`的属性。导航链接元素应设置为“button”。

**示例:** 此示例说明了带有下拉功能的 navbar 药丸。

# 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" 
          content="IE=edge" />
    <meta name="viewport" 
          content="width=device-width, 
                   initial-scale=1.0" />
    <title>Pills navigation menu</title>
    <link href=
"https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
          rel="stylesheet"
          integrity=
"sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
          crossorigin="anonymous"/>
  </head>
  <body>
    <nav class="nav nav-pills p-4 bg-dark">
      <a class="nav-link active bg-warning" 
         aria-current="true" 
         href="#">Home
      </a>
      <a class="nav-link text-warning" 
         href="#">About Us
      </a>
      <div class="dropdown">
        <a
          class="nav-link text-warning"
          role="button"
          data-bs-toggle="dropdown"
          aria-expanded="false"
          href="#">Careers
        </a>
        <ul class="dropdown-menu">
          <li>
            <a class="dropdown-item" 
               href="#">Web dev</a>
          </li>
          <li>
            <a class="dropdown-item" 
               href="#">Mobile dev
            </a>
          </li>
          <li>
            <a class="dropdown-item" 
                 href="#">ML dev
            </a>
          </li>
        </ul>
      </div>
      <a class="nav-link text-warning" 
         href="#">Contact Us
      </a>
    </nav>

    <p class="p-4">
      GeeksforGeeks - A Computer Science 
      portal for geeks. It contains well
      written, well thought and well 
      explained computer science and programming
      articles, quizzes and practice/
      competitive programming/company interview
      Questions.
    </p>

    <script src=
"https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js"
            integrity=
"sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM"
            crossorigin="anonymous">
    </script>
  </body>
</html>
```

**输出:**

![](img/f1fd313a26698552737d164d565d7cb1.png)

## 带下拉菜单的药丸导航

要创建可折叠药丸导航菜单，请使用带类的按钮。`navbar-toggler`带属性`data-bs-toggle`和`data-bs-target`。`button`内跨一个等级为`navbar-toggler-icon`的元素。在这里，我们还使用了 [fontawesome](https://fontawesome.com/) 来获取汉堡菜单图标。然后，包装`.nav-link`元素和类`.navbar-collapse`和`.collapse`并识别`#navbar-collapse`。使用类`.collapse`作为属性`data-bs-toggle`的值，折叠`id`作为`data-bs-target`属性的值。

**示例:** 本示例说明了可折叠药丸导航菜单。

# 超文本标记语言

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta http-equiv="X-UA-Compatible" 
          content="IE=edge" />
    <meta name="viewport" 
          content="width=device-width, 
                   initial-scale=1.0" />
    <title>Pills navigation menu</title>
    <link href=
"https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/css/bootstrap.min.css"
          rel="stylesheet"
          integrity=
"sha384-EVSTQN3/azprG1Anm3QDgpJLIm9Nao0Yz1ztcQTwFspd3yD65VohhpuuCOmLASjC"
      crossorigin="anonymous"/>
    <link rel="stylesheet"
          href=
"https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0-beta2/css/all.min.css"/>
  </head>

  <body>
    <nav class="nav nav-pills p-4 bg-dark">
      <button
        class="navbar-toggler"
        type="button"
        data-bs-toggle="collapse"
        data-bs-target="#navbar-collapse">
        <span class="navbar-toggler-icon">
          <i class="fas fa-bars text-white fa-2x"></i>
        </span>
      </button>
      <div class="collapse navbar-collapse text-white" 
           id="navbar-collapse">
        <ul class="navbar-nav">
          <li class="nav-item mt-4 pl-3">
            <a class="nav-link active bg-warning" 
               aria-current="true" 
               href="#">Home
            </a>
          </li>
          <li class="nav-item">
            <a class="nav-link text-warning" 
               href="#">About Us </a>
          </li>
          <li class="nav-item">
            <a class="nav-link text-warning" 
               href="#">Careers </a>
          </li>
          <li class="nav-item">
            <a class="nav-link text-warning" 
               href="#">Contact Us </a>
          </li>
        </ul>
      </div>
    </nav>

    <p class="p-4">
      GeeksforGeeks - A Computer Science portal 
      for geeks. It contains well written, well 
      thought and well explained computer science 
      and programming articles, quizzes and 
      practice/competitive programming/company 
      interview Questions.
    </p>

    <script src=
"https://cdn.jsdelivr.net/npm/bootstrap@5.0.2/dist/js/bootstrap.bundle.min.js"
            integrity=
"sha384-MrcW6ZMFYlzcLA8Nl+NtUVF0sA7MsXsP1UyJoMp4YLEuNSfAP+JcXn/tWtIaxVXM"
            crossorigin="anonymous">
    </script>
  </body>
</html>
```

**输出:**

![](img/4fe7a8e89cf491b3d56a8d8695b2c046.png)

## 可折叠药丸导航