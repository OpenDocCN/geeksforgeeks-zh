# 语义-UI |手风琴

> 原文:[https://www.geeksforgeeks.org/sementic-ui-accordion/](https://www.geeksforgeeks.org/sementic-ui-accordion/)

语义 UI 是一个开源框架，它使用 CSS 和 jQuery 来构建出色的用户界面。它和引导程序一样，有很大的不同元素，可以让你的网站看起来更加惊艳。它使用一个类向元素添加 CSS。

手风琴是交互式用户界面，允许我们切换隐藏和显示等部分的显示。

## jQuery Code

```html
$('.ui.accordion').accordion();
```

## 示例 1

本示例使用 Sementic 创建手风琴。

```html
<!DOCTYPE html>
<html>

<head>
    <title>Semantic-UI Accordian</title>

<link href=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css"
            rel="stylesheet" />

<script src="https://code.jquery.com/jquery-3.1.1.min.js" integrity=
"sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8="
            crossorigin="anonymous">
    </script>

<script src=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.js">
    </script>
</head>

<body>
    <div style="margin-top: 20px" class="ui container">
        <div class="ui accordion">
            <div class="active title">
                <i class="dropdown icon"></i>
                What is Geeksforgeeks?
            </div>
            <div class="active content">
                <p>
                    Geeksforgeeks is a platform where 
                    you can find solution to any king 
                    of computer science related problem
                </p>
            </div>
            <div class="title">
                <i class="dropdown icon"></i>
                What is Internshala?
            </div>
            <div class="content">
                <p>
                    It's an online platform which 
                    provide opportunity for student 
                    to get internship.
                </p>
            </div>
            <div class="title">
                <i class="dropdown icon"></i>
                What is Semantic-ui:
            </div>
            <div class="content">
                <p>
                    It's a really cool framework
                    by which you can do cool stuff
                </p>
            </div>
        </div>
    </div>

<script>
        $('.ui.accordion').accordion();
    </script>
</body>

</html>
```

**输出:**
![](img/1120528b223c8dd4182782eeba675bc7.png)

但是上面例子的输出看起来很简单。为了让它看起来非常酷，就像在一个正方形的盒子里一样，你只需要添加一个风格化的类，比如“用户界面风格的手风琴”。

## 示例 2

本示例使用 Sementic 创建了一个时尚的手风琴。

```html
<!DOCTYPE html>
<html>

<head>
    <title>Semantic UI Stylish Accordian</title>

<link href=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css"
            rel="stylesheet" />

<script src="https://code.jquery.com/jquery-3.1.1.min.js" integrity=
"sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8=" 
            crossorigin="anonymous">
    </script>

<script src=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.js">
    </script>
</head>

<body>
    <div style="margin-top: 20px" class="ui container">
        <div class="ui styled accordion">
            <div class="active title">
                <i class="dropdown icon"></i>
                What is Geeksforgeeks?
            </div>
            <div class="active content">
                <p>
                    Geeksforgeeks is a platform where 
                    you can find solution to any king
                    of computer science related problem
                </p>
            </div>
            <div class="title">
                <i class="dropdown icon"></i>
                What is Internshala?
            </div>
            <div class="content">
                <p>
                    It's an online platform which
                    provide opportunity for student
                    to get internship.
                </p>
            </div>
            <div class="title">
                <i class="dropdown icon"></i>
                What is Semantic-ui:
            </div>
            <div class="content">
                <p>
                    It's a really cool framework by
                    which you can do cool stuff
                </p>
            </div>
        </div>
    </div>

<script>
        $('.ui.accordion').accordion();
    </script>
</body>

</html>
```

**输出:**
![](img/f116da7ccbce5d492f32aef0131ca92b.png)

## 示例 3

本示例使用 Sementic 创建嵌套手风琴。

```html
<!DOCTYPE html>
<html>

<head>
    <title>Semantic UI Nested Accordian</title>

<link href=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css"
            rel="stylesheet" />

<script src="https://code.jquery.com/jquery-3.1.1.min.js" integrity=
"sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8="
            crossorigin="anonymous">
    </script>

<script src=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.js">
    </script>
</head>

<body>
    <div style="margin-top: 20px" class="ui container">
        <div class="ui styled accordion">
            <div class="active title">
                <i class="dropdown icon"></i>
                Geeksforgeeks Articles
            </div>
            <div class="active content">
                Data Structure
                <div class="accordion">
                    <div class="active title">
                        <i class="dropdown icon"></i>
                        Link-List
                    </div>
                    <div class="active content">
                        <p>Types of Link-List</p>
                        <div class="accordion">
                            <div class="title">
                                <i class="dropdown icon"></i>
                                Singly Link-List
                            </div>
                            <div class="content">
                                It contain data part and next pointer.
                            </div>
                            <div class="title">
                                <i class="dropdown icon"></i>
                                Doubly Link-List
                            </div>
                            <div class="content">
                                It contain data part, next and prev pointer.
                            </div>
                        </div>
                    </div>
                    <div class="title">
                        <i class="dropdown icon"></i>
                        Tree
                    </div>
                    <div class="content">
                        Binary Tree
                    </div>
                </div>
            </div>
            <div class="title">
                <i class="dropdown icon"></i>
                Geekforgeeks Courses
            </div>
            <div class="content">
                <p>Courses</p>
                <div class="accordion">
                    <div class="active title">
                        <i class="dropdown icon"></i>
                        Web Technologies
                    </div>
                </div>
            </div>
        </div>
    </div>

<script>
        $('.ui.accordion').accordion();
    </script>
</body>

</html>
```

**输出:**
![](img/c68607558ae66378641121b538fb3698.png)

## 示例 4

本示例使用 Semantic-UI 创建一个手风琴式菜单。这里我们将使用复选框和单选按钮。

### jQuery Code

```html
$('.ui.accordion').accordion();
$('.ui.radio.checkbox').checkbox();
$('.ui.checkbox').checkbox();
```

### 完整代码

```html
<!DOCTYPE html>
<html>

<head>
    <title>Semantic UI Accordian Menu</title>

<link href=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.css"
            rel="stylesheet" />

<script src="https://code.jquery.com/jquery-3.1.1.min.js" integrity=
"sha256-hVVnYaiADRTO2PzUGmuLJr8BLUSjGIZsDYGmIJLv2b8=" 
            crossorigin="anonymous">
    </script>

<script src=
"https://cdnjs.cloudflare.com/ajax/libs/semantic-ui/2.4.1/semantic.min.js">
    </script>
</head>
```

# 测试选择界面

## 测试类型选择

在 `ui container` 中，有一个 `ui vertical accordion menu`。

第一个可折叠的 `item` 默认是展开的（`active`），其标题为 **Choose Test**。

在 `active content` 中，有一个 `ui form`，其中包含一个 `grouped fields` 组。组内有三个 `field`，每个 `field` 包含一个 `ui radio checkbox`。

单选按钮的 `name` 属性均为 `test`，`value` 属性和对应的 `label` 分别如下：
*   `value="ds"`，标签为 **Data Structure**
*   `value="web"`，标签为 **Web Technology**
*   `value="programming"`，标签为 **Programming**

## 难度级别选择

第二个可折叠的 `item` 默认是收起的，其标题为 **Level (Atleast 1)**。

在其 `content` 中，同样有一个 `ui form` 和 `grouped fields`。组内有三个 `field`，每个 `field` 包含一个 `ui checkbox`。

复选框的 `name` 属性和对应的 `label` 分别如下：
*   `name="easy"`，标签为 **Easy**
*   `name="intermediate"`，标签为 **Intermediate**
*   `name="diff"`，标签为 **Difficult**

## 脚本初始化

页面底部的 `<script>` 标签内包含初始化脚本：

```javascript
$('.ui.accordion').accordion();
$('.ui.radio.checkbox').checkbox();
$('.ui.checkbox').checkbox();
```

输出:
![](img/58d85d8367dd54ea85ea49825166061b.png)