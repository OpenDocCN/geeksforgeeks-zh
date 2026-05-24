# HTML DOM 图像使用地图属性

> 原文:[https://www . geesforgeks . org/html-DOM-image-usemap-property/](https://www.geeksforgeeks.org/html-dom-image-usemap-property/)

HTML DOM Image **usemap** 属性用于设置或返回 Image 元素的 usemap 属性值。**使用地图**属性将图像定义为客户端图像地图。图像地图是可点击的图像区域。它用于创建图像和地图之间的关系。该属性值与地图元素的名称属性值相同。

**语法:**

*   它返回 usemap 属性。

```html
imageObject.useMap
```

*   它用于设置 image usemap 属性。

```html
imageObject.useMap *=* #mapname
```

**属性值:**

*   **#地图名称:**用于保存包含哈希(#)字符的地图名称。

**返回值:**它返回一个字符串值，代表包含哈希字符(“#”)的 *usemap* 属性的值。

**示例 1:** 本示例返回一个 *useMap* 属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body style="text-align:center">
    <h2 style="color:green">
        GeeksforGeeks
    </h2>
    <b>
        HTML Dom Image useMap Property
    </b><br />

    <map name="Geeks1">
        <area id="Geeks" shape="rect" 
            coords="0, 0, 110, 100" alt="Geeks"
            href=
https://manaschhabra:manaschhabra499@www.geeksforgeeks.org />
    </map>

    <img id="GFG" src=
"https://media.geeksforgeeks.org/wp-content/uploads/a1-25.png"
        width="300" height="100"
        alt="geeksforgeeks" usemap="#Geeks1">
    </br>

    <button onclick="GFG()">
        Click Here!
    </button>

    <p id="GEEK!"></p>

    <script>
        function GFG() {

            // Return value of usemap attribute.
            var x = document.getElementById("GFG").useMap;
            document.getElementById("GEEK!").innerHTML = x;
        }
    </script>
</body>

</html>
```

**输出:**

![](img/117e2ff37e33b396af20808e15219103.png)

返回 usemap 属性

**示例 2:** 本示例设置 *useMap* 属性。

## 超文本标记语言

```html
<!DOCTYPE html>
<html>

<body style="text-align:center">
    <h2 style="color:green">
        GeeksforGeeks
    </h2>
    <b>
        HTML Dom Image useMap Property
    </b>

    <map name="Geeks1">
        <area id="Geeks" shape="rect" 
            coords="0, 0, 110, 100" alt="Geeks"
            href=
https://manaschhabra:manaschhabra499@www.geeksforgeeks.org />
    </map>

    <img id="GFG" src=
"https://media.geeksforgeeks.org/wp-content/uploads/a1-25.png"
        width="300" height="100"
        alt="Geeksforgeeks" usemap="#Geeks1">
    </br>

    <button onclick="GFG()">
        Click Here!
    </button>

    <p id="paraID"></p>

    <script>
        function GFG() {

            // Return value of usemap attribute.
            var x = document.getElementById(
                    "GFG").useMap = "#Geeks2";
            document.getElementById("paraID")
                .innerHTML = "The value of the useMap "
                + "attribute was changed to: " + x;
        }
    </script>
</body>

</html>
```

**输出:**

![](img/3ecf5ce70bce9b55db0c67a50777f885.png)

设置 usemap 属性

**支持的浏览器:**

*   谷歌 Chrome
*   微软公司出品的 web 浏览器
*   火狐浏览器
*   歌剧
*   旅行队