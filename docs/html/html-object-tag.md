# HTML 对象标签

> 原文:[https://www.geeksforgeeks.org/html-object-tag/](https://www.geeksforgeeks.org/html-object-tag/)

<object>标签是一个 HTML 标签，用于在网页中显示音频、视频、图像、pdf 和 Flash 等多媒体。它还可以用于在 HTML 页面中显示另一个网页。
参数<标签也与该标签一起用于定义各种参数。在<对象>和</对象>标签中写入的任何文本都被视为浏览器不支持指定数据时出现的替代文本。
这个标签支持 HTML 的所有全局和事件属性。
**例:**</object> 

## 超文本标记语言

```html
<!DOCTYPE html>

<html>

    <body>
        <h1>HTML Object Tag</h1>
        <!--HTML object tag starts here-->
        <object data=
"https://media.geeksforgeeks.org/wp-content/cdn-uploads/Geek_logi_-low_res.png"
width="550px" height="150px">GeeksforGeeks
        <!--HTML object tag ends here-->
        </object>
    </body>

</html>                   
```

**输出:**

![](img/f2877bfababc3bc1de737011b6601dd1.png)

<object>标签有以下属性:

<figure class="table">

| attribute | value | describe |
| --- | --- | --- |
| [data](https://www.geeksforgeeks.org/html-object-data-attribute/) | 统一资源定位器 | It specifies the URL of the data in the object. |
| [Type](https://www.geeksforgeeks.org/html-object-type-attribute/) | 媒体类型 | It specifies the media type of the data specified in the data attribute. |
| 类型必须匹配 | 布尔 | Indicates that the resource should be embedded only when the value of the type attribute matches the resource type provided on the data attribute. |
| [Alignment](https://www.geeksforgeeks.org/html-object-align-attribute/) | Up and down | It defines the alignment of objects. |
| [border](https://www.geeksforgeeks.org/html-object-border-attribute/) | pixel | It specifies the border around the object. |
| [Height](https://www.geeksforgeeks.org/html-height-attribute/) | pixel | It specifies the height of the object. |
| hspace | pixel | It specifies the white space on the left and right sides of the object. |
| [vs 步速](https://www.geeksforgeeks.org/html-object-vspace-attribute/) | pixel | It specifies the white space at the top and bottom of the object. |
| [Height](https://www.geeksforgeeks.org/html-object-height-attribute/) | pixel | It specifies the height of the object. |
| [Width](https://www.geeksforgeeks.org/html-object-width-attribute/) | pixel | It specifies the width of the object. |
| [Name](https://www.geeksforgeeks.org/html-object-name-attribute/) | name | It specifies a name for an object. |
| [Form](https://www.geeksforgeeks.org/html-object-form-attribute/) | 表单 id | It specifies the form id to which the object element belongs. |

</figure></object> 

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队