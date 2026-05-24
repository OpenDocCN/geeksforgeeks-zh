# jQuery |垂直点导航插件

> 原文:[https://www . geesforgeks . org/jquery-竖线-点-导航-插件/](https://www.geeksforgeeks.org/jquery-vertical-dot-navigation-plugin/)

jQuery 为程序员提供了一个漂亮、轻量级、单页且响应迅速的**垂直点导航**插件，帮助他们在长网页中导航或滚动。该插件识别网站中的页面或部分的数量，并相应地添加点以供点击来滚动相应的内容。

请下载**垂直点导航**插件，并在您的工作文件夹中包含所需的文件库，如以下代码的标题部分所示。
**下载链接**:https://github . com/maiamachine/jquery-竖线-点-导航

**示例 1:** 在下面的示例中， **verticalDotNav()** 方法的非常基本的调用是使用 jQuery 显示的。HTML 页面的不同部分提供了不同的页面内容。

```html
<!doctype html>
<html lang="en">
<head>
  <meta charset="utf-8">

  <title>jQuery Vertical Dot Navigation Plugin</title> 
  <link rel="stylesheet" href="bootstrap.css"> 
  <link rel="stylesheet" href="styles.css">

  <!--required stylesheet file of plugin-->
  <link rel="stylesheet"
        href="jq-vertical-dot-navigation.css">

  <!--Required javascript file dependencies-->
  <script src="jquery.min.js"></script>
  <script src="jq-vertical-dot-nav.js"></script>

    <script>
           $(document).ready(function(){
               $('section').verticalDotNav(); 

           })
    </script>
</head>
<body>

<section id="section-1" class="row">
    <div class="col-xs-10 col-xs-offset-1">
    <h3>jQuery Vertical Dot Navigation Plugin</h3>

    </div>
</section>
<section id="section-2" class="row">
    <div class="col-xs-8 col-xs-offset-2 col-md-6 col-md-offset-3">
    <p>Amazon… “Hire and Develop the Best”. 
One of the Big Four Tech Companies founder
 Jeff Bezos is now the richest person on this planet.
 Jeff was an engineer and 25 years ago when Jeff pitched 
his idea of starting a business online to his boss 
David (Founder of DE Shaw) it was rejected indirectly.
 Well, Jeff quit the job and started Amazon from his 
garage in Seattle Washington.Today the company is making
 billions of dollars and fulfilling the customer’s 
needs worldwide in various areas.</p>
    </div>
</section>
<section id="section-3" class="row">
    <div class="col-xs-10 col-xs-offset-1 col-md-6 col-md-offset-3">
    <p>As the placement season is back so are we to help you ace
 the interview. We have selected some most commonly asked and 
must do practice problems for you. You can also take part in our
mock placement contests which will help you learn different topics and 
practice at the same time, simulating the feeling of a real placement
 test environment.</p>
    </div>    
</section>
</body>
</html>
```

**输出:**
![](img/9b454cdb2f42c2990f06cd76c7c7aaec.png "Vertical dot navigation output basic")

**示例 2:** 在以下示例中， **verticalDotNav()** 方法的各种选项设置如下。只需注意图像输出中的点对齐和滚动速度，并根据要求在代码中进行相应的定制。

```html
<!doctype html>

<html lang="en">
<head>
  <meta charset="utf-8">

  <title>jQuery Vertical Dot Navigation Plugin</title> 
  <link rel="stylesheet" href="bootstrap.css"> 
  <link rel="stylesheet" href="styles.css">

  <!--required stylesheet file of plugin-->
  <link rel="stylesheet" href="jq-vertical-dot-navigation.css">

  <!--Required javascript file dependencies-->
  <script src="jquery.min.js"></script>
  <script src="jq-vertical-dot-nav.js"></script>

    <script>
           $(document).ready(function(){
               $('section').verticalDotNav({
               align : "left", // Options are 'right' or 'left'
               scroll_speed : 2500, // The time in milliseconds
               dot_size: 30,
               dot_style: 'circle', // Options are 'circle' or 'square'
               dot_color: "#e9e9e9",
               nav_color: "#000000"

            });            
           })
    </script>
</head>
<body>

<section id="section-1" class="row">
    <div class="col-xs-10 col-xs-offset-1">
    <h3>jQuery Vertical Dot Navigation Plugin</h3>

    </div>
</section>
<section id="section-2" class="row">
    <div class="col-xs-8 col-xs-offset-2 col-md-6 col-md-offset-3">
    <p>Amazon… “Hire and Develop the Best”. One of the Big Four
 Tech Companies founder Jeff Bezos is now the richest person 
on this planet.
    Jeff was an engineer and 25 years ago when Jeff pitched 
his idea of starting a business online to his boss David 
(Founder of DE Shaw) 
    it was rejected indirectly. Well, Jeff quit the job and
 started Amazon from his garage in Seattle Washington.
    Today the company is making billions of dollars and
 fulfilling the customer’s needs worldwide in various areas.</p>
    </div>
</section>
<section id="section-3" class="row">
    <div class="col-xs-10 col-xs-offset-1 col-md-6 col-md-offset-3">

    <p> As the placement season is back so are we to help you ace 
the interview.
        We have selected some most commonly asked and must do 
practice problems for you.
        You can also take part in our mock placement contests 
which will help you learn different topics and practice at the same time,
        simulating the feeling of a real placement test environment.</p>
    </div>    
</section>
</body>
</html>
```

![](img/7f58a463662fe5ee27f574dce99a12e3.png "Vertical dot navigation with options")