# JavaScript 数组 reverse() 方法

> 原文：`https://www.geeksforgeeks.org/javascript-array-reverse-method/`

下面是 `reverse()` 方法的例子。

## 示例

```javascript
<script>
function func() {

// Original Array
    var arr = ['Portal', 'Science', 
               'Computer', 'GeeksforGeeks'];
    document.write(arr);

// Reversed array
    var new_arr = arr.reverse();
    document.write("<br>");
    document.write(new_arr);
}
func();
</script>
```

**输出：**

```
Portal,Science,Computer,GeeksforGeeks
GeeksforGeeks,Computer,Science,Portal
```

`arr.reverse()` 方法用于原地反转数组。数组的第一个元素成为最后一个元素，反之亦然。

## 语法

```
arr.reverse()
```

## 参数

此方法不接受任何参数。

## 返回值

该方法返回反转后的原始数组的引用。

## 示例

以下示例说明了 JavaScript `reverse()` 方法：

**示例 1：** 在此示例中，`reverse()` 方法反转了数组 `arr` 的元素序列。

```javascript
var arr = [34, 234, 567, 4];
print(arr);
var new_arr = arr.reverse();
print(new_arr);
```

**输出：**

```
34, 234, 567, 4
4, 567, 234, 34
```

上述方法的代码如下：

**程序 1：**

```javascript
<script>
function func() {

// Original Array
    var arr = [34, 234, 567, 4];
    document.write(arr);

// Reversed array
    var new_arr = arr.reverse();
    document.write("<br>");
    document.write(new_arr);
}
func();
</script>
```

**输出：**

```
34, 234, 567, 4
4, 567, 234, 34
```

## 支持的浏览器

JavaScript `Array reverse()` 方法支持的浏览器如下：

*   谷歌 Chrome 1.0 及以上版本
*   微软 Edge 12 及以上版本
*   Mozilla Firefox 1.0 及以上版本
*   Safari 1 及以上
*   歌剧 4 及以上