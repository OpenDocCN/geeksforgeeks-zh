# jQuery | menu-aim 插件

> 哎哎哎::1230【https://www . geeksforgeeks . org/jquery-menu-aim 插件/

jQuery 提供了**菜单-aim** 插件，帮助程序员开发有效的下拉菜单以及子菜单内容的简单导航。该插件可以很好地区分用户悬停在下拉项目和导航子菜单内容。该插件还支持 JS 事件处理功能，如鼠标进入或退出，激活或停用子菜单。

请[下载菜单-aim](https://github.com/kamens/jQuery-menu-aim) 插件，并将所需文件保存在您的工作文件夹中。如下所示，在代码的头部包含所需的文件。

**示例 1:** 在以下示例中，**菜单-目标**插件被演示为下拉菜单。下拉菜单有 HTML *未排序列表*和*列表项*视需要而定。每个*列表项*都有*子菜单*“div”，标题为**内容为*。下拉菜单的 HTML 结构是使用**菜单-aim** 插件的 CSS 和 JS 代码实现的。插件本身也提供了“激活子菜单”和“去激活子菜单”等其他功能。程序员可以根据应用程序的要求更改或增强 JS 代码。*

```html
*<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <title>jQuery-menu-aim Plugin</title>
    <meta name="viewport" 
          content="width=device-width, initial-scale=1.0">
    <meta name="description" content="">
    <meta name="author" content="">

    <link href="css/bootstrap.css" rel="stylesheet">

    <link href="css/bootstrap-responsive.css" 
          rel="stylesheet">

    <style>
        body {
            padding-top: 60px;
        }

        .navbar .popover {
            width: 200px;
            -webkit-border-top-left-radius: 0px;
            -webkit-border-bottom-left-radius: 0px;
            border-top-left-radius: 0px;
            border-bottom-left-radius: 0px;
            overflow: hidden;
        }

        .navbar .popover-content,
        .popover-title {
            text-align: center;
        }

        .navbar .popover-content ul {
            text-align: center;
            height: 200px;
            width: 100px
        }

        .navbar .popover-content p {
            height: 200px;
            max-width: 250px;
            text-align: center;
        }

        .navbar .dropdown-menu {
            -webkit-border-top-right-radius: 0px;
            -webkit-border-bottom-right-radius: 0px;
            border-top-right-radius: 0px;
            border-bottom-right-radius: 0px;
            -webkit-box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2);
            -moz-box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2);
            box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2);
        }

        .navbar .dropdown-menu > li > a:hover {
            background-image: none;
            color: white;
            background-color: rgb(0, 129, 194);
            background-color: rgba(0, 129, 194, 0.5);
        }

        .navbar .dropdown-menu > li > a.maintainHover {
            color: white;
            background-color: green;
        }
    </style>

</head>

<body>

    <div class="navbar navbar-inverse navbar-fixed-top">
        <div class="navbar-inner">
            <div class="container">
                <button type="button" class="btn btn-navbar" 
                 data-toggle="collapse" data-target=".nav-collapse">
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                </button>
                <div>
                    <a href="https://www.geeksforgeeks.org/">
                        <img src="images/gfg1.png" 
                             alt="geeksforgeeks" width="250px"></a>
                </div>

                <div class="nav-collapse collapse">
                    <ul class="nav">
                        <li class="active">
                            <a class="dropdown-toggle" 
                       data-toggle="dropdown" href="#">Tutorials</a>

                        <ul class="dropdown-menu" role="menu">
                            <li data-submenu-id="submenu-algorithms">
                                <a href="#">Algorithms</a>
                               <div id="submenu-algorithms" class="popover">
                                   <h3 class="popover-title">Algorithms</h3>
                                    <div class="popover-content">
                                       <p>Topics like Bubble sort, quick sort
                                 <br/>Brute force method and other notes </p>
                                        </div>
                                    </div>
                                </li>

                            <li data-submenu-id="submenu-data-structures">
                               <a href="#">Data Structures  </a>
                                <div id="submenu-data-structures" class="popover">
                                   <h3 class="popover-title">Data Structures</h3>
                                    <div class="popover-content">
                                        <p>Binary Tree
                                          </br/>Arrays
                                        <br/>Stacks and other DS topics</p>
                                        </div>
                                    </div>
                                </li>
                           <li data-submenu-id="submenu-languages">
                               <a href="#">Languages</a>
                                 <div id="submenu-languages" class="popover">
                                    <h3 class="popover-title">Languages</h3>
                                    <div class="popover-content">
                                       <p>Java
                                           <br/>Python
                                           <br/>C, C++, C#
                                          <br/>COBOL</p>
                               </div>
                             </div>
                            </li>
                       <li data-submenu-id="submenu-interview">
                                <a href="#">Interview Corner</a>
                                <div id="submenu-interview" class="popover">
                                   <h3 class="popover-title">Interview Corner</h3>
                                    <div class="popover-content">
                                            <p>Interview tips
                                                <br/> Questions
                                          <br/> HR round and other notes</p>
                                        </div>
                                    </div>
                                </li>
                                <li data-submenu-id="submenu-gate">
                                    <a href="#">Gate</a>
                                    <div id="submenu-gate" class="popover">
                                        <h3 class="popover-title">Gate</h3>
                                        <div class="popover-content">
                                            <p>Gate CS notes
                                                <br/>GATE CS solved papers
                                                <br/>important topics</p>
                                        </div>
                                    </div>
                                </li>
                                <li data-submenu-id="submenu-isro">
                                    <a href="#">ISRO CS</a>
                                    <div id="submenu-isro" class="popover">
                                        <h3 class="popover-title">ISRO CS</h3>
                                        <div class="popover-content">
                                            <p>ISRO CS solved papers.
                                <br/>ISRO CS original papers and official keys.
                                                <br/>ISRO CS syllabus</p>
                                        </div>
                                    </div>
                                </li>

                                <li data-submenu-id="submenu-web">
                                    <a href="#">Web Technologies </a>
                                    <div id="submenu-web" class="popover">
                                 <h3 class="popover-title">Web Technologies </h3>
                                        <div class="popover-content">
                                 <p>About Web Technologies and its implementation.</p>
                                        </div>
                                    </div>
                                </li>
                            </ul>
                        </li>
                    </ul>
                    <ul class="nav">
                        <li class="active">
                            <a class="dropdown-toggle"
                               data-toggle="dropdown"
                               href="#">Students</a>

                            <ul class="dropdown-menu" role="menu">
                                <li data-submenu-id="submenu-gethired">
                                    <a href="#">Get Hired</a>
                                    <div id="submenu-gethired" class="popover">
                                        <h3 class="popover-title">Get Hired</h3>
                                        <div class="popover-content">
                                     <a href="https://practice.geeksforgeeks.org/jobs/">
                                            Job opportunities in GFG </a>
                                        </div>
                                    </div>
                                </li>

                                <li data-submenu-id="submenu-careers">
                                    <a href="#">Careers  </a>
                                    <div id="submenu-careers" class="popover">
                                        <h3 class="popover-title">Careers</h3>
                                        <div class="popover-content">
                                     <a href="https://www.geeksforgeeks.org/careers/">
                                            Geeks careers</a>
                                        </div>
                                    </div>
                                </li>
                                <li data-submenu-id="submenu-project">
                                    <a href="#">Project</a>
                                    <div id="submenu-project" class="popover">
                                        <h3 class="popover-title">Project</h3>
                                        <div class="popover-content">
                                            <p>Project submenu</p>
                                        </div>
                                    </div>
                                </li>
                                <li data-submenu-id="submenu-internship">
                                    <a href="#">Internship</a>
                                    <div id="submenu-internship" class="popover">
                                        <h3 class="popover-title">Internship</h3>
                                        <div class="popover-content">
                                            <p>Internship tips
                                                <br/> Stipend details
                                                <br/> other notes</p>
                                        </div>
                                    </div>
                                </li>
                            </ul>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <script src="js/jquery-1.9.1.min.js" type="text/javascript"></script>
    <script src="jquery.menu-aim.js" type="text/javascript"></script>
    <script src="js/bootstrap.min.js" type="text/javascript"></script>

    <script>
        var $menu = $(".dropdown-menu");

        // Events handlingon menu row activation.
        $menu.menuAim({
            activate: activateSubmenu,
            deactivate: deactivateSubmenu
        });

        /*  JS is used to show and hide the submenu contents.
            It calls the activate and deactivate*/
        //  events at the right time to show and hide your submenus.
        function activateSubmenu(row) {
            var $row = $(row),
                submenuId = $row.data("submenuId"),
                $submenu = $("#" + submenuId),
                height = $menu.outerHeight(),
                width = $menu.outerWidth();

            // Show the submenu
            $submenu.css({
                display: "block",
                top: -1,
                left: width - 3,
                height: height - 4
            });

            // Currently activated row is highlighted 
            $row.find("a").addClass("maintainHover");
        }

        function deactivateSubmenu(row) {
            var $row = $(row),
                submenuId = $row.data("submenuId"),
                $submenu = $("#" + submenuId);

            // Hide the submenu and remove the highlighted row
            $submenu.css("display", "none");
            $row.find("a").removeClass("maintainHover");
        }

        // Bootstrap's dropdown menus immediately close on document click.
        // This event should not be closed if a submenu is being clicked.

        $(".dropdown-menu li").click(function(e) {
            e.stopPropagation();
        });

        $(document).click(function() {

            $(".popover").css("display", "none");
            $("a.maintainHover").removeClass("maintainHover");
        });
    </script>
</body>

</html>*
```

***输出:**
![](img/5c4156ac242f018238f2cf853fc761cc.png "menu-aim-output")*

***示例 2:** 在上面的示例中，每个*列表项*都有*子菜单*，其“标题”和“内容”以简单的方式显示。下面的例子演示了如何使用**菜单-aim** 插件提供的 HTML“ul”和“li”元素和类来添加另一个*侧子菜单*。每个*侧子菜单*都有列表项，这些列表项带有指向相应标题主题的链接，只是为了对子菜单有一个基本的了解。*

```html
*<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <title>jQuery-menu-aim Plugin</title>
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta name="description" content="">
    <meta name="author" content="">

    <link href="css/bootstrap.css" rel="stylesheet">

    <link href="css/bootstrap-responsive.css" rel="stylesheet">

    <style>
        body {
            padding-top: 60px;
        }

        .navbar .popover {
            width: 200px;
            -webkit-border-top-left-radius: 0px;
            -webkit-border-bottom-left-radius: 0px;
            border-top-left-radius: 0px;
            border-bottom-left-radius: 0px;
            overflow: hidden;
        }

        .navbar .popover-content,
        .popover-title {
            text-align: center;
        }

        .navbar .popover-content ul {
            text-align: center;
            height: 400px;
            width: 200px
        }

        .navbar .popover-content p {
            height: 400px;
            max-width: 250px;
            text-align: center;
        }

        .navbar .dropdown-menu {
            -webkit-border-top-right-radius: 0px;
            -webkit-border-bottom-right-radius: 0px;
            border-top-right-radius: 0px;
            border-bottom-right-radius: 0px;
            -webkit-box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2);
            -moz-box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2);
            box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2);
        }

        .navbar .dropdown-menu > li > a:hover {
            background-image: none;
            color: white;
            background-color: rgb(0, 129, 194);
            background-color: rgba(0, 129, 194, 0.5);
        }

        .navbar .dropdown-menu > li > a.maintainHover {
            color: white;
            background-color: green;
        }

        .side-sub-menu {
            list-style-type: none;
            height: 400px;
            text-align: center;
        }

        .list-style {
            width: 180px;
            text-align: left;
        }
    </style>

</head>

<body>

    <div class="navbar navbar-inverse navbar-fixed-top">
        <div class="navbar-inner">
            <div class="container">
                <button type="button" class="btn btn-navbar"
                        data-toggle="collapse" data-target=".nav-collapse">
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                </button>
                <div>
                    <a href="https://www.geeksforgeeks.org/"> 
                      <img src="images/gfg1.png" alt="geeksforgeeks"
                           width="250px"></a>
                </div>

                <div class="nav-collapse collapse">
                    <ul class="nav">
                        <li class="active">
                            <a class="dropdown-toggle"
                               data-toggle="dropdown" href="#">Tutorials</a>

                            <ul class="dropdown-menu" role="menu">
                                <li data-submenu-id="submenu-algorithms">
                                    <a href="#">Algorithms</a>
                                    <div id="submenu-algorithms" class="popover">
                                        <h3 class="popover-title">Algorithms</h3>
                                        <div class="popover-content">
                                            <ul class="side-sub-menu">
                                                <li class="list-style">
                           <a href=
"https://www.geeksforgeeks.org/searching-algorithms/">Searching algorithms</a></li>
                                                <li class="list-style">
                           <a href=
"https://www.geeksforgeeks.org/sorting-algorithms/">Sorting algorithms</a></li>

                                            </ul>
                                        </div>
                                    </div>
                                </li>

                                <li data-submenu-id="submenu-data-structures">
                                    <a href="#">Data Structures  </a>
                                    <div id="submenu-data-structures" class="popover">
                                        <h3 class="popover-title">Data Structures</h3>
                                        <div class="popover-content">
                                            <ul class="side-sub-menu">
                                                <li class="list-style">
                             <a href=
"https://www.geeksforgeeks.org/array-data-structure/">Arrays structures</a></li>
                                                <li class="list-style">
                             <a href=
"https://www.geeksforgeeks.org/stack-data-structure/">Stack structures</a></li>
                                            </ul>
                                        </div>
                                    </div>
                                </li>
                                <li data-submenu-id="submenu-languages">
                                    <a href="#">Languages</a>
                                    <div id="submenu-languages" class="popover">
                                        <h3 class="popover-title">Languages</h3>
                                        <div class="popover-content">
                                            <ul class="side-sub-menu">
                                                <li class="list-style">
                             <a href=
"https://www.geeksforgeeks.org/java/">Java language</a></li>
                                                <li class="list-style">
<a href="https://www.geeksforgeeks.org/php/">PHP script</a></li>
                                            </ul>
                                        </div>
                                    </div>
                                </li>
                            </ul>
                        </li>
                    </ul>
                    <ul class="nav">
                        <li class="active">
                            <a class="dropdown-toggle" 
                               data-toggle="dropdown" href="#">Students</a>
                            <ul class="dropdown-menu" role="menu">
                                <li data-submenu-id="submenu-gethired">
                                    <a href="#">Get Hired</a>
                                    <div id="submenu-gethired" class="popover">
                                        <h3 class="popover-title">Get Hired</h3>
                                        <div class="popover-content">
                   <a href=
"https://practice.geeksforgeeks.org/jobs/">Job opportunities in GFG </a></div>
                                    </div>
                                </li>

                                <li data-submenu-id="submenu-careers">
                                    <a href="#">Careers  </a>
                                    <div id="submenu-careers" class="popover">
                                        <h3 class="popover-title">Careers</h3>
                                        <div class="popover-content">
                    <a href=
"https://www.geeksforgeeks.org/careers/">Geeks careers</a></div>
                                    </div>
                                </li>
                                <li data-submenu-id="submenu-project">
                                    <a href="#">Project</a>
                                    <div id="submenu-project" class="popover">
                                        <h3 class="popover-title">Project</h3>
                                        <div class="popover-content">
                   <p>Project side-submenu list items will come here</p>
                                        </div>
                                    </div>
                                </li>
                                <li data-submenu-id="submenu-internship">
                                    <a href="#">Internship</a>
                                    <div id="submenu-internship" class="popover">
                                        <h3 class="popover-title">Internship</h3>
                                        <div class="popover-content">
                     <p>Internship side sub menu ulist items will come here</p>
                                        </div>
                                    </div>
                                </li>
                            </ul>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <script src="js/jquery-1.9.1.min.js" type="text/javascript"></script>
    <script src="jquery.menu-aim.js" type="text/javascript"></script>
    <script src="js/bootstrap.min.js" type="text/javascript"></script>

    <script>
        var $menu = $(".dropdown-menu");

        // Events handlingon menu row activation.
        $menu.menuAim({
            activate: activateSubmenu,
            deactivate: deactivateSubmenu
        });

        /*  JS is used to show and hide the submenu contents.
            It calls the activate and deactivate*/
        //  Events at the right time to show and hide your submenus.
        function activateSubmenu(row) {
            var $row = $(row),
                submenuId = $row.data("submenuId"),
                $submenu = $("#" + submenuId),
                height = $menu.outerHeight(),
                width = $menu.outerWidth();

            // Show the submenu
            $submenu.css({
                display: "block",
                top: -1,
                left: width - 3,
                height: height - 4
            });

            // Currently activated row is highlighted 
            $row.find("a").addClass("maintainHover");
        }

        function deactivateSubmenu(row) {
            var $row = $(row),
                submenuId = $row.data("submenuId"),
                $submenu = $("#" + submenuId);

            // Hide the submenu and remove the highlighted row
            $submenu.css("display", "none");
            $row.find("a").removeClass("maintainHover");
        }

        // Bootstrap's dropdown menus immediately close on document click.
        // This event should not be closed if a submenu is being clicked.

        $(".dropdown-menu li").click(function(e) {
            e.stopPropagation();
        });

        $(document).click(function() {

            $(".popover").css("display", "none");
            $("a.maintainHover").removeClass("maintainHover");
        });
    </script>
</body>

</html>*
```

***输出:**
![](img/23116453073b40777530e4353cd1f0d8.png "menu-aim-with-submenu-output")*

***示例 3:** 以下示例演示了**菜单-aim** 插件 javascript 功能的使用。它显示了各种选项设置和功能的简单实现。例如，如果用户进入*子菜单*，背景颜色变为“红色”，离开主下拉菜单后，下拉菜单顶部会显示一条消息。程序员可以根据应用需求为其他选项编写代码。*

```html
*<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="utf-8">
    <title>jQuery-menu-aim Plugin</title>
    <meta name="viewport" 
          content="width=device-width, initial-scale=1.0">
    <meta name="description" content="">
    <meta name="author" content="">

    <link href="css/bootstrap.css" rel="stylesheet">

    <link href="css/bootstrap-responsive.css" 
          rel="stylesheet">

    <style>
        body {
            padding-top: 60px;
        }

        .navbar .popover {
            width: 200px;
            -webkit-border-top-left-radius: 0px;
            -webkit-border-bottom-left-radius: 0px;
            border-top-left-radius: 0px;
            border-bottom-left-radius: 0px;
            overflow: hidden;
        }

        .navbar .popover-content,
        .popover-title {
            text-align: center;
        }

        .navbar .popover-content ul {
            text-align: center;
            height: 200px;
            width: 100px
        }

        .navbar .popover-content p {
            height: 200px;
            max-width: 250px;
            text-align: center;
        }

        .navbar .dropdown-menu {
            -webkit-border-top-right-radius: 0px;
            -webkit-border-bottom-right-radius: 0px;
            border-top-right-radius: 0px;
            border-bottom-right-radius: 0px;
            -webkit-box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2);
            -moz-box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2);
            box-shadow: 5px 5px 10px rgba(0, 0, 0, 0.2);
        }

        .navbar .dropdown-menu > li > a:hover {
            background-image: none;
            color: white;
            background-color: rgb(0, 129, 194);
            background-color: rgba(0, 129, 194, 0.5);
        }

        .navbar .dropdown-menu > li > a.maintainHover {
            color: white;
            background-color: green;
        }

        .side-sub-menu {
            list-style-type: none;
            height: 400px;
            text-align: center;
        }

        .list-style {
            width: 180px;
            text-align: left;
        }
    </style>
</head>

<body>
    <div class="navbar navbar-inverse navbar-fixed-top">
        <div class="navbar-inner">
            <div class="container">
                <button type="button" class="btn btn-navbar" 
             data-toggle="collapse" data-target=".nav-collapse">
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                    <span class="icon-bar"></span>
                </button>
                <div>
                    <a href="https://www.geeksforgeeks.org/">
<img src="images/gfg1.png" alt="geeksforgeeks" width="250px"></a>
                </div>
                <div id="exitMenuMsgboxId" style="background-color:pink"></div>
                <div class="nav-collapse collapse">
                    <ul class="nav">
                        <li class="active">
                            <a class="dropdown-toggle"
                      data-toggle="dropdown" href="#">Tutorials</a>

                            <ul class="dropdown-menu" role="menu">
                                <li data-submenu-id="submenu-algorithms">
                                    <a href="#">Algorithms</a>
                                    <div id="submenu-algorithms" class="popover">
                                        <h3 class="popover-title">Algorithms</h3>
                                        <div class="popover-content">
                                            <ul class="side-sub-menu">
                                                <li class="list-style">
                <a href=
"https://www.geeksforgeeks.org/searching-algorithms/">
                  Searching algorithms</a></li>
                                                <li class="list-style">
                <a href=
"https://www.geeksforgeeks.org/sorting-algorithms/">Sorting algorithms</a></li>
                                            </ul>
                                        </div>
                                    </div>
                                </li>

                                <li data-submenu-id="submenu-data-structures">
                                    <a href="#">Data Structures  </a>
                                    <div id="submenu-data-structures" class="popover">
                                        <h3 class="popover-title">Data Structures</h3>
                                        <div class="popover-content">
                                            <ul class="side-sub-menu">
                                                <li><a href=
"https://www.geeksforgeeks.org/array-data-structure/">Arrays</a></li>
                                                <li><a href=
"https://www.geeksforgeeks.org/stack-data-structure/">Stack</a></li>
                                            </ul>
                                        </div>
                                    </div>
                                </li>
                                <li data-submenu-id="submenu-languages">
                                    <a href="#">Languages</a>
                                    <div id="submenu-languages" class="popover">
                                        <h3 class="popover-title">Languages</h3>
                                        <div class="popover-content">
                                            <ul class="side-sub-menu">
                                                <li><a href=
                  "https://www.geeksforgeeks.org/java/">Java</a></li>
                                                <li><a href=
                 "https://www.geeksforgeeks.org/php/">PHP</a></li>
                                            </ul>
                                        </div>
                                    </div>
                                </li>
                            </ul>
                        </li>
                    </ul>
                </div>
            </div>
        </div>
    </div>

    <script src="js/jquery-1.9.1.min.js" type="text/javascript"></script>
    <script src="jquery.menu-aim.js" type="text/javascript"></script>
    <script src="js/bootstrap.min.js" type="text/javascript"></script>

    <script>
        var $menu = $(".dropdown-menu");

        // Events handling on menu row activation.
        $menu.menuAim({
            activate: activateSubmenu,
            deactivate: deactivateSubmenu,
            enter: enterSubmenu,
            exitMenu: exitMainmenu,
            subMenuDirection: "right"
        });

        /*  JS is used to show and hide the submenu contents.
            It calls the activate and deactivate*/
        //  Events at the right time to show and hide your submenus.
        function activateSubmenu(row) {
            var $row = $(row),
                submenuId = $row.data("submenuId"),
                $submenu = $("#" + submenuId),
                height = $menu.outerHeight(),
                width = $menu.outerWidth();

            // Show the submenu
            $submenu.css({
                display: "block",
                top: -1,
                left: width - 3,
                height: height - 4
            });

            // Currently activated row is highlighted 
            $row.find("a").addClass("maintainHover");
        }

        function deactivateSubmenu(row) {
            var $row = $(row),
                submenuId = $row.data("submenuId"),
                $submenu = $("#" + submenuId);

            // Hide the submenu and remove the highlighted row
            $submenu.css("display", "none");
            $row.find("a").removeClass("maintainHover");
        }

        function enterSubmenu(row) {
            var $row = $(row),
                submenuId = $row.data("submenuId"),
                $submenu = $("#" + submenuId);
            $submenu.css("background-color", "red");
        }

        function exitMainmenu() {
            $("#exitMenuMsgboxId").html(" Main menu left !");
        }
        // Bootstrap's dropdown menus immediately close on document click.
        // This event should not be closed if a submenu is being clicked.

        $(".dropdown-menu li").click(function(e) {
            e.stopPropagation();
        });

        $(document).click(function() {

            $(".popover").css("display", "none");
            $("a.maintainHover").removeClass("maintainHover");
        });
    </script>

</body>

</html>*
```

***输出:**
![](img/a19c846cc68c2d12453e8724d7029d79.png "menu-aim-with-options-output")*