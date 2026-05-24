# 如何在 Bootstrap 中更改表格行或单个单元格的背景色？

> 原文:[https://www . geeksforgeeks . org/如何更改引导中表格行或单个单元格的背景颜色/](https://www.geeksforgeeks.org/how-to-change-background-color-of-table-rows-or-individual-cells-in-bootstrap/)

在本文中，我们将讨论设置表格行的背景色&如何使用 Bootstrap 设置单个单元格的背景色。Bootstrap 提供了一系列类，可用于对表格应用各种样式，如更改标题外观、剥离行、添加或删除边框、使行可悬停等。Bootstrap 还提供了使表响应的类。

创建表格的目的是以简单紧凑的结构化格式显示复杂的大数据，该格式在浏览时提供信息内容。这将节省读取和分析非结构化大数据的时间。引导有助于以标准方式创建和修饰内容。我们将使用引导内置类来创建表结构。可以使用以下语法创建一个简单的 HTML 表:

**语法:**

```html
<table class="table"> Table Contents... <table>
```

在我们继续我们的主要讨论之前，使用 HTML 创建表格的知识将帮助您更好地理解文章。关于 Bootstrap 中表格的许多其他情况，请参考 [Bootstrap 4 |表格](https://www.geeksforgeeks.org/bootstrap-4-tables/)。

**引导 CDN 链接:**我们举个例子来了解如何设置&添加一个[引导 CDN](https://getbootstrap.com/docs/3.3/getting-started/) 链接来应用引导预定义的类来创建表。

> <src 脚本= " https://Ajax . Google APIs . com/Ajax/libs/jquery/3 . 5 . 1/jquery . min . js "></script><src 脚本= " https://cdnjs . cloudflare . com/Ajax/libs/popper . js

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>Geeks For Geeks</title>
    <link href="style.css" rel="stylesheet" type="text/css" />
    <link
      rel="stylesheet"
      href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css"
      integrity=
"sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO"
      crossorigin="anonymous"/>
  </head>

  <body>
    <h1>Tables</h1>
    <h3>Change color of tables</h3>
    <table class="table table-bordered table-hover table-sm">
      <thread>
        <tr>
          <th scope="col">Sl No.</th>
          <th scope="col">Country</th>
          <th scope="col">Capital</th>
        </tr>
      </thread>
      <tbody>
        <tr>
          <th scope="row">1</th>
          <td>India</td>
          <td>New Delhi</td>
        </tr>
        <tr>
          <th scope="row">2</th>
          <td>Canada</td>
          <td>Ottawa</td>
        </tr>
        <tr>
          <th scope="row">3</th>
          <td>Bangladesh</td>
          <td>Dhaka</td>
        </tr>
        <tr>
          <th scope="row">4</th>
          <td>Australia</td>
          <td>Canberra</td>
        </tr>
      </tbody>
    </table>
  </body>
</html>
```

**输出:**

![](img/d3f65addb5c598771758de661d08e3a3.png)

我们已经在代码中添加了引导 CDN 链接，它构成了一个标准且结构良好的内容表。使用预定义的类，我们可以更改表格单元格和表格行的颜色。为了改变表格行的颜色，我们需要在标签中指定所需的类&为了改变表格行的颜色，然后在Tag to specify the required class. Let's study section by section.

**预定义类:**为了改变一行或整个表格的颜色，我们将使用以下任何一个类。

1.  **表格-活动:**此类适用于灰色表格行或单元格的悬停颜色。
2.  **表格-默认:**当选择默认行时，该类用于将颜色更改为白色。
3.  **表-初级:**此类表示重要动作。
4.  **表-次要:**此类表示不太重要的活动。
5.  **表-成功:**此类表示积极或成功的行动。
6.  **表-危险:**该等级表示潜在的负面或危险行为。
7.  **表-警告:**此类表示可能需要注意的警告。
8.  **表格信息:**该类别表示中性的信息变化或动作。
9.  **表光:**此类适用于表行背景或浅灰色表。
10.  **表格-深色:**此类适用于深灰色表格。

**示例:**在这种情况下，我们已经使用了所有预定义的类来更改行的颜色。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>Geeks For Geeks</title>
    <link href="style.css" rel="stylesheet" type="text/css" />
    <link
      rel="stylesheet"
      href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css"
      integrity=
"sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO"
      crossorigin="anonymous"/>
  </head>

  <body>
    <h1>Tables</h1>
    <h3>Different colour of table rows</h3>

    <table class="table">
      <thread>
        <th scope="col">Sl No.</th>
        <th scope="col">Class</th>
      </thread>
      <tbody>
        <tr class="table-active">
          <th scope="row">1</th>
          <td>table-active</td>
        </tr>
        <tr class="table-default">
          <th scope="row">2</th>
          <td>table-default</td>
        </tr>
        <tr class="table-primary">
          <th scope="row">3</th>
          <td>table-primary</td>
        </tr>
        <tr class="table-secondary">
          <th scope="row">4</th>
          <td>table-secondary</td>
        </tr>
        <tr class="table-success">
          <th scope="row">5</th>
          <td>table-success</td>
        </tr>
        <tr class="table-danger">
          <th scope="row">6</th>
          <td>table-danger</td>
        </tr>
        <tr class="table-warning">
          <th scope="row">7</th>
          <td>table-warning</td>
        </tr>
        <tr class="table-info">
          <th scope="row">8</th>
          <td>table-info</td>
        </tr>
        <tr class="table-light">
          <th scope="row">9</th>
          <td>table-light</td>
        </tr>
        <tr class="table-dark">
          <th scope="row">10</th>
          <td>table-dark</td>
        </tr>
      </tbody>
    </table>
  </body>
</html>
```

**输出:**

![](img/6177f9cf8e1f5faf24a1a71f232fd3e1.png)

要更改任何特定单元格的颜色，可以使用以下任一类:

1.  **bg-primary:** 适用于表示积极或成功的行动。
2.  **bg-success:** 适用于表示成功或积极的行动。
3.  **BG-警告:**适用于指示可能需要注意的警告
4.  **BG-危险:**适用于指示潜在的负面或危险行为
5.  **bg-info:** 用于表示中性的信息变化或动作。

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>Geeks For Geeks</title>
    <link href="style.css" rel="stylesheet" type="text/css" />
    <link
      rel="stylesheet"
      href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css"
      integrity=
"sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO"
      crossorigin="anonymous"/>
  </head>

  <body>
    <h1>Tables</h1>
    <h3>Change color of single cells</h3>
    <table class="table">
      <thread>
        <th scope="col">Sl No.</th>
        <th scope="col">Class</th>
      </thread>
      <tbody>
        <tr>
          <th scope="row">1</th>
          <td class="bg-primary">bg-primary</td>
        </tr>
        <tr>
          <th scope="row">2</th>
          <td class="bg-success">bg-success</td>
        </tr>
        <tr>
          <th scope="row">3</th>
          <td class="bg-warning">bg-warning</td>
        </tr>
        <tr>
          <th scope="row">4</th>
          <td class="bg-danger">bg-danger</td>
        </tr>
        <tr>
          <th scope="row">5</th>
          <td class="bg-info">bg-info</td>
        </tr>
      </tbody>
    </table>
  </body>
</html>
```

**输出:**

![](img/c966a9f7cf973670f02efe7d28b70e6b.png)

为了改变特定表格单元格的颜色，我们需要在特定单元格的Specify it in the tag. The following example shows how to declare for a specific cell.

**示例:**

## 超文本标记语言

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <meta name="viewport" content="width=device-width" />
    <title>Geeks For Geeks</title>
    <link
      rel="stylesheet"
      href=
"https://stackpath.bootstrapcdn.com/bootstrap/4.1.3/css/bootstrap.min.css"
      integrity=
"sha384-MCw98/SFnGE8fJT3GXwEOngsV7Zt27NXFoaoApmYm81iuXoPkFOJwJ8ERdknLPMO"
      crossorigin="anonymous"
    />
  </head>

  <body>
    <h1>Tables</h1>
    <h3>Change color of tables</h3>
    <table class="table table-bordered table-hover table-sm">
      <thread>
        <tr>
          <th scope="col">Sl No.</th>
          <th scope="col">Country</th>
          <th scope="col">Capital</th>
        </tr>
      </thread>
      <tbody>
        <tr class="bg-primary">
          <th scope="row">1</th>
          <td>India</td>
          <td>New Delhi</td>
        </tr>
        <tr>
          <th scope="row">2</th>
          <td class="bg-success">Canada</td>
          <td>Ottawa</td>
        </tr>
        <tr>
          <th scope="row">3</th>
          <td>Bangladesh</td>
          <td>Dhaka</td>
        </tr>
        <tr>
          <th scope="row">4</th>
          <td>Australia</td>
          <td>Canberra</td>
        </tr>
      </tbody>
    </table>
  </body>
</html>
```

**输出:**

![](img/10a2e0f28e1ca1e859959d010e69a9fd.png)

自定义颜色