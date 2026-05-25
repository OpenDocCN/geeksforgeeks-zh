
# HTML 禁用属性

> 原文: [https://www.geeksforgeeks.org/html-disabled-attribute-2/](https://www.geeksforgeeks.org/html-disabled-attribute-2/)

## HTML `<keygen>` 禁用属性

`<keygen>` 禁用属性是一个布尔属性，表示 `<keygen>` 元素是否禁用。它用于阻止用户使用输入字段，直到对其应用了某些条件。

**注意:**我们可以用 JavaScript 改变禁用的 `<keygen>` 元素的值。

## 语法

```html
<keygen disabled>
```

## 示例

```html
<!DOCTYPE html>
<html>

<body>
    <center>
        <h1 style="color:green;">
            GeeksforGeeks
        </h1>

<h2>HTML Keygen disabled attribute</h2>

<form>
            Username: <input type="text" name="uname">
            <br><br>

Password: <input type="text"><br>
            Encryption Element Value:
            <keygen form="myGeeks" name="secure" disabled>
            <br><input type="submit">
        </form>
    </center>
</body>

</html>
```

## 输出

![输出示例](img/1233d67f658e2a87aa8b11c83ec352d5.png)

## 支持的浏览器

*   谷歌 Chrome
*   火狐浏览器
*   歌剧
*   苹果 Safari
