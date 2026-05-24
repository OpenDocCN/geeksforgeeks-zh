# 如何使用 CSS 自动调整字体大小？

> 原文:[https://www . geesforgeks . org/how-auto-adjust-font-size-use-CSS/](https://www.geeksforgeeks.org/how-to-auto-adjust-font-size-using-css/)

CSS 的 *[【字体大小-调整】](https://www.geeksforgeeks.org/css-font-size-adjust-property/)* 属性告诉浏览器将文本的字体大小调整为相同大小，而不考虑字体系列。当第一个选择的字体不可用时，font-size-adjust 属性允许您更好地控制字体大小。如果字体不可用，窗口默认为定义的第二种字体。这可能会导致字体大小的显著变化。使用 font-size-adjust 属性停止此操作。小写字母“X”和大写字母“X”之间的大小差异是所有字体的“长宽值”。当浏览器知道第一种字体的“纵横比”时，它将决定在查看第二种字体的文本时使用什么字体大小。

**语法:**

```html
font-size-adjust: number|none|initial|inherit;
```

以下是说明使用*字体大小调整*属性的示例。

**示例:**

## HTML

```html
<!DOCTYPE html>
<html>

<head>
   <style>
    div.a {font-family: Helvetica;}
    div.b {font-family: 'sans-serif';}
    #div1, #div2 {font-size-adjust: 0.74;}
   </style>
</head>

<body>
  <h1 style = "color:green;text-align:center;"> 
    GeeksforGeeks 
  </h1>

  <h2 style = "color:blue;text-align:left;">
    Font Size Adjust Property
  </h2>

  <h2 style ="color:orange;text-align:left;">
    Divs with same Font Size Adjust Property:
  </h2>

  <div id="div1" class="a">
    We offer a range of services to help you learn, 
    develop, and have fun! Free tutorials, millions 
    of posts, live, online, and classroom classes, 
    regular coding contests, industry expert webinars, 
    internships, and career openings are all available.
  </div><br>

  <div id="div2" class="b">
    Sandeep Jain is the founder of 'GeeksforGeeks,'
    an IIT Roorkee alumni group. He enjoys finding 
    the most effective solutions to programming problems. 
  </div>

  <h2 style = "color:red;text-align:left;">
    Divs without same Font Size Adjust Property:
  </h2>

  <div class="a">
    Apart from GeeksforGeeks, he has worked as a web 
    developer for DE Shaw and Co. and as an assistant 
    professor at JIIT Noida. 
  </div><br>

  <div class="b">
    GeeksforGeeks.org was founded with the aim of 
    providing well-written, well-considered, and 
    well-explained answers to specific questions. 
    If you're interested in mastering algorithms, 
    data structures, or just the programming language itself, 
    GeeksforGeeks has you covered!
  </div>
</body>

</html>
```