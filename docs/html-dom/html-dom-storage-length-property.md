# HTML | DOM 存储长度属性

> 原文:[https://www . geesforgeks . org/html-DOM-storage-length-property/](https://www.geeksforgeeks.org/html-dom-storage-length-property/)

HTML DOM 中的**存储长度属性**用于**返回** *存储对象*中存储的项数。存储对象包括**本地存储**或**会话存储**。

**语法:**
获取存储长度属性。

```html
object.length
```

**返回值:**返回一个数字，表示存储对象中当前的项目数。

**示例-1:** 在 localStorage 对象上使用。

```html
<!DOCTYPE html>
<html>

<head>
    <title>DOM Storage length</title>
</head>

<body>
    <h1 style="color: green">
      GeeksForGeeks
  </h1>
    <b>DOM Storage length</b>
    <p>Click on the buttons below to add/clear
      items and check the current number 
      of items in localStorage
  </p>
    <p>Total Items: <span class="output"></span></p>
    <button onclick="addItem(50)">
      Add 50 items
  </button>
    <button onclick="clearItems()">
      Clear all items
  </button>
    <button onclick="getStorageLength()">
      Get Storage length
  </button>
    <div class="items"> </div>
    <script>
        // To set item.
        function addItem(values) {
            for (i = 0; i < values; i++)
                localStorage.setItem(i, 'item ' + i);
        }

        // To clear item.      
        function clearItems() {
            localStorage.clear();
        }

        // To return the number of items.
        function getStorageLength() {
            totalItems = localStorage.length;
            document.querySelector('.output').textContent = 
            totalItems;
        }
    </script>
</body>

</html>
```

**输出:**添加 50 个元素后点击按钮。
T3】

**示例-2:** 在会话存储对象上使用

```html
<!DOCTYPE html>
<html>

<head>
    <title>DOM Storage length</title>
</head>

<body>
    <h1 style="color: green">
      GeeksForGeeks
  </h1>
    <b>DOM Storage length</b>
    <p>
      Click on the buttons below to add/clear
      items and check the current number of
      items in sessionStorage
  </p>
    <p>Total Items: <span class="output"></span></p>
    <button onclick="addItem(10)">Add 10 items</button>
    <button onclick="clearItems()">Clear all items</button>
    <button onclick="getStorageLength()">
      Get Storage length
  </button>
    <div class="items"> </div>

    <script>
        function addItem(values) {
            for (i = 0; i < values; i++)
                sessionStorage.setItem(i, 'item ' + i);
        }

        function clearItems() {
            sessionStorage.clear();
        }

        function getStorageLength() {
            totalItems = sessionStorage.length;
            document.querySelector('.output').textContent = 
              totalItems;
        }
    </script>
</body>

</html>
```

**输出:**添加 10 个元素后点击按钮。
T3】

**支持的浏览器:**支持的浏览器*存储长度*属性如下:

*   谷歌 Chrome 4.0
*   Internet Explorer 8.0
*   Firefox 3.5
*   歌剧 10.5
*   Safari 4.0