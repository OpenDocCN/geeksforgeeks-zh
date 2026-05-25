# ES6 字符串

> 原文: [https://www.geeksforgeeks.org/es6-string/](https://www.geeksforgeeks.org/es6-string/)

ES6 JavaScript 中有两种字符串类型：**字符串原语**和**字符串对象**。它通过助手方法包装了 JavaScript 的字符串原语。有一些辅助方法。

*   **字符串原语:** 当包装类型的方法被调用时，原语自动装箱到其包装类型。它没有助手方法，它不过是指向原始数据内存引用的指针。所以这里它包装成一个字符串包装器。 (`var i = 1`) 这里它包装成一个整数包装器。
*   **字符串对象:** 这是一个字符串对象。字符串对象是在字符串类的帮助下创建的。它用许多辅助方法包装字符串基元数据类型。

**语法:** ES6 JavaScript 中有三个属性提到并描述如下:

```javascript
var stringobject = new String(string);
```

**字符串属性:**

| 属性 | 描述 |
| --- | --- |
| `Constructor` | 此属性返回对创建实例原型的字符串函数的引用。 |
| `长度` | 此属性返回字符串的长度。 |
| `prototype` | 此属性是一个全局属性，几乎可被所有对象使用。它允许您向对象添加属性和方法，其中原型对象的行为与字符串原语的自动装箱不同。 |

以下示例说明了这些属性:

**示例:**

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <script>
        function hero(id, name) {
            this.id = id;
            this.name = name;
        }

        // Object e
        var e = new hero(123, "GeeksforGeeks");

        // Object e1
        var e1 = new hero(124, "Courses");

        // This prototype property is constant for all objects.
        hero.prototype.group = "Edutech";

        // Returns object reference
        document.write("Constructor Property = " + e.constructor);

        // Returns length
        document.write("<br>Length of emp.name(GeeksforGeeks) = " + e.name.length);

        // Returns the new property(group)
        document.write("<br>Prototype(emp1.name=Courses) group = " + e1.group);

        // Returns the new property(group)
        document.write("<br>Prototype(emp.name=GeeksforGeeks) group = " + e.group);
    </script>
</head>

<body>
</body>

</html>
```

**输出:**

```
Constructor Property = function hero(id, name) { this.id = id; this.name = name; }
Length of emp.name(GeeksforGeeks) = 13
Prototype(emp1.name=Courses) group = Edutech
Prototype(emp.name=GeeksforGeeks) group = Edutech
```

**字符串对象的方法:** 这些是字符串对象中可用的方法列表。

| 方法 | 描述 |
| --- | --- |
| `charAt(索引)` | 此方法返回指定索引处的字符。 |
| `charCodeAt(字符)` | 此方法返回指定索引处字符的 ASCII 码。 |
| `Concatenation(字符串)` | 此方法返回连接后的字符串。 |
| `Index(字符串)` | 此方法返回给定字符串的起始索引。 |
| `lastIndexOf(字符串)` | 此方法返回给定字符串最后一次出现的起始索引。 |
| `localeCompare(字符串)` | 根据排序顺序，如果比较的字符串相等则返回 0，否则返回 1 或 -1。 |
| `match(正则表达式，字符串)` | 返回正则表达式的匹配结果。 |
| `replace(正则表达式，字符串)` | 返回字符串中替换后的正则表达式结果。 |
| `search(RegExp)` | 此方法搜索给定的单词或正则表达式。如果传递字符串作为参数，它将使用 `new RegExp(obj)` 转换为正则表达式。 |
| `slice(startIndex，endIndex)` | 此方法返回从 `startIndex` 到 `endIndex`（不包括）的指定索引处的字符串。 |
| `substring(起始索引，长度)` | 返回从 `startIndex` 到 `startIndex+length`（包含）的指定索引处的字符串。 |
| `substr(startIndex，endIndex)` | 返回从 `startIndex` 到 `endIndex` 的指定索引处的字符串（包含）。 |
| `Split("separator", 分割份数)` | 返回按分隔符分割的数组，给定 `b` = 分割份数，如果未提及分割则返回整个数组。 |
| `toLocaleLowerCase()` | 返回当前区域设置的小写字符串。 |
| `toLocaleUpperCase()` | 返回当前区域设置的大写字符串。 |
| `toLowerCase()` | 返回转换为小写的字符串值。 |
| `toUpperCase()` | 返回转换为大写的字符串值。 |
| `toString()` | 返回转换为大写的字符串值。 |
| `valueOf()` | 返回字符串对象的原始值。 |

下面的例子将说明这些方法:

**示例:**

## HTML

```html
<!DOCTYPE html>
<html>

<head>
    <script>
        var str = new String("A Online Computer Science Portal");
        var str1 = new String("Computer Science Portal for Geeks");

        document.write("str.charAt(0) is = " + str.charAt(0));
        document.write("<br>str.charCodeAt(0) is = " + str.charCodeAt(0));

        document.write("<br>");
        document.write("<br>str1.concat('=>Geeks?') = " + str1.concat('=>Geeks?'));

        document.write("<br>");
        document.write("<br>str.indexOf('of') = " + str.indexOf('of'));
        document.write("<br>str.lastIndexOf('of') = " + str.lastIndexOf('of'));

        document.write("<br>");
        document.write("<br>str.localeCompare( 'A Online Computer Science Portal') = "
            + str.localeCompare('A Online Computer Science Portal'));
        document.write("<br>str.localeCompare( 'Computer Science Portal for Geeks') = "
            + str.localeCompare('Computer Science Portal for Geeks'));
        document.write("<br>str.localeCompare( 'A Computer Science Portal') = "
            + str.localeCompare('A Computer Science Portal'));

        document.write("<br>");
        if (str.search("Geeksfor") != -1) {
            document.write("<br>Geeks exist in str.");
        } else {
            document.write("<br>Geeks doesn't exist in str.");
        }

        document.write("<br>");
        document.write("<br>str.slice(5, -1) = " + str.slice(5, -1));
        document.write("<br>str.substr(2, 9) = " + str.substr(2, 9));
        document.write("<br>str.substring(2, 9) = " + str.substring(2, 9));

        document.write("<br>");
        document.write("<br>str.split(' ') = " + JSON.stringify(str.split(' ')));
        document.write("<br>str.split(':', 4) = " + JSON.stringify(str.split(':', 4)));
        document.write("<br>str.split('of', 4) = " + JSON.stringify(str.split('of', 4)));

        document.write("<br>")
        document.write("<br>str1.toLocaleLowerCase( ) = " + str1.toLocaleLowerCase());
        document.write("<br>str1.toLocaleUpperCase() = " + str1.toLocaleUpperCase());
        document.write("<br>str1.toLowerCase( ) = " + str1.toLowerCase());
        document.write("<br>str1.toUpperCase() = " + str1.toUpperCase());

        document.write("<br>")
        document.write("<br>str1.toString() = " + str1.toString());
        document.write("<br>str1.valueOf( ) = " + str1.valueOf());
    </script>
</head>

</html>
```

**输出:**

```
str.charAt(0) is = A
str.charCodeAt(0) is = 65

str1.concat('=>Geeks?') = Computer Science Portal for Geeks=>Geeks?

str.indexOf('of') = -1
str.lastIndexOf('of') = -1

str.localeCompare( 'A Online Computer Science Portal') = 0
str.localeCompare( 'Computer Science Portal for Geeks') = -1
str.localeCompare( 'A Computer Science Portal') = 1

Geeks doesn't exist in str.

str.slice(5, -1) = ine Computer Science Porta
str.substr(2, 9) = Online Co
str.substring(2, 9) = Online

str.split(' ') = ["A","Online","Computer","Science","Portal"]
str.split(':', 4) = ["A Online Computer Science Portal"]
str.split('of', 4) = ["A Online Computer Science Portal"]

str1.toLocaleLowerCase( ) = computer science portal for geeks
str1.toLocaleUpperCase() = COMPUTER SCIENCE PORTAL FOR GEEKS
str1.toLowerCase( ) = computer science portal for geeks
str1.toUpperCase() = COMPUTER SCIENCE PORTAL FOR GEEKS

str1.toString() = Computer Science Portal for Geeks
str1.valueOf( ) = Computer Science Portal for Geeks
```