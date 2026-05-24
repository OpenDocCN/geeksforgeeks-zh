# 如何用 jQuery 实现带分页的表格可搜索可排序？

> 原文:[https://www . geeksforgeeks . org/如何使用-jquery/](https://www.geeksforgeeks.org/how-to-make-table-searchable-and-sortable-with-pagination-using-jquery/) 通过分页来制作可搜索和可排序的表格

jQuery fancyTable 插件帮助开发人员设计带有分页功能的可搜索和可排序的 HTML 表。这个插件完全基于 JavaScript 和 HTML。

**插件官网:**执行代码时请注意文件路径。

```html
https://github.com/myspace-nu/jquery.fancyTable
```

**示例 1:** 下面的代码演示了使用 jQuery **fancyTable** 插件进行分页的简单搜索和排序。

## HTML

```html
<!DOCTYPE html>
<html lang="en">
    <head>
        <meta charset="utf-8">
        <meta name="viewport" 
              ontent="width=device-width, 
                 initial-scale=1, shrink-to-fit=no">

        <link href=
"https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.1.3/css/bootstrap.min.css"
         rel="stylesheet">
    </head>
    <body><br/>

        <div class="container">
            <h3 style="">
              Table with search and sortable headings 
            </h3>
            <table id="mytableID" style="width:100%" 
                   class="table table-striped sampleTable"> 
            <tr> 
                <th>Firstname</th> 
                <th>Lastname</th> 
                <th>Age</th> 
            </tr> 
            <tr> 
                <td>Priya</td> 
                <td>Sharma</td> 
                <td>24</td> 
            </tr> 
            <tr> 
                <td>Arun</td> 
                <td>Singh</td> 
                <td>32</td> 
            </tr> 
            <tr> 
                <td>Samy</td> 
                <td>Watson</td> 
                <td>41</td> 
            </tr> 
            <tr> 
                <td>Samsamder</td> 
                <td>Watra</td> 
                <td>42</td> 
            </tr> 
            <tr> 
                <td>Samantha</td> 
                <td>Challa</td> 
                <td>31</td> 
            </tr> 
            <tr> 
                <td>Samuel</td> 
                <td>Miranda</td> 
                <td>45</td> 
            </tr> 
            <tr> 
                <td>Samy</td> 
                <td>Joseph</td> 
                <td>37</td> 
            </tr> 
                  </table> 

        </div>
        <script  src=
"https://cdnjs.cloudflare.com/ajax/libs/jquery/3.3.1/jquery.min.js">
        </script>
        <script src=
"https://cdnjs.cloudflare.com/ajax/libs/twitter-bootstrap/4.1.3/js/bootstrap.min.js">
        </script>
        <script src="fancyTable.js">
        </script>
        <script type="text/javascript">

            $(document).ready(function() {
                $(".sampleTable").fancyTable({
                  /* Column number for initial sorting*/
                   sortColumn:0,
                   /* Setting pagination or enabling */
                   pagination: true,
                   /* Rows per page kept for display */
                   perPage:3,
                   globalSearch:true
                   });

            });
        </script>
    </body>
</html>
```