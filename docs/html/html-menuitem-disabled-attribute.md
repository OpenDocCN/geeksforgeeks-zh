# HTML menuitem 禁用属性

> 原文:[https://www . geesforgeks . org/html-menuitem-disabled-attribute/](https://www.geeksforgeeks.org/html-menuitem-disabled-attribute/)

**HTML**[**<menuitem>**](https://www.geeksforgeeks.org/html-menuitem-tag/)*****禁用*** 属性是一个布尔属性，用于指定菜单项是否被禁用。*禁用的*菜单项不可选择，通常看起来是灰色的。**

****语法:****

```html
<menuitem disabled> 
```

****示例:**下面的代码演示了在[**<menuitem>**](https://www.geeksforgeeks.org/html-menuitem-tag/)标签中使用 ***禁用*** **属性。****

## **超文本标记语言**

```html
<!DOCTYPE html>
<html>

<body>
    <center>
        <h1 style="color:green;">
            GeeksforGeeks
        </h1>

        <h2>HTML <menuitem> disabled Attribute</h2>

        <div style="background:green;
            border:2px solid black;
            padding: 10px;" contextmenu="geeks">

<p>A Computer Science Portal for Geeks</p>

            <menu type="context" id="geeks">
                <menu label="Share on...">
                    <menuitem label="Twitter" onclick=
        "window.open('//twitter.com/intent/tweet?text='
                    + window.location.href);" disabled>
                    </menuitem>
                    <menuitem label="Pinterest" onclick=
                    "window.open(
        'http://pinterest.com/pin/create/button/?url=' + 
                        window.location.href);">
                    </menuitem>
                </menu>

                <menuitem label="Email This Page" 
                    onclick="window.location='mailto:?body='
                    + window.location.href;">
                </menuitem>
            </menu>
        </div>

<p>A Computer Science Portal for Geeks</p>

        <hr>

<p>Right click on green div and see the menuitem
    </center>
</body>

</html>
```