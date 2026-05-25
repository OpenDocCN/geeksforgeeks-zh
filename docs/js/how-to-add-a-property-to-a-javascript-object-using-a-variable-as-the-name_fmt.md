# 如何用变量作为名称给JavaScript对象添加属性？

> 原文：[https://www.geeksforgeeks.org/how-to-add-a-property-to-a-javascript-object-using-a-variable-as-the-name/](https://www.geeksforgeeks.org/how-to-add-a-property-to-a-javascript-object-using-a-variable-as-the-name/)

我们可以用对象文字创建一个JavaScript对象：

**示例：**

```javascript
var obj = { firstname : "Romy", lastname : "kumari", age : 20}
```

名称：JavaScript对象中的值对称为属性。我们可以通过使用点符号或括号符号，使用变量作为名称，将属性添加到JavaScript对象中。

以下示例说明了两种不同的方法：

## 示例1：使用点符号

在本例中，我们将使用点符号。

### HTML示例代码

```html
<!DOCTYPE html>
<html>
    <body>
        <p style="font-size: 30px; color: green;" ;>
          GeeksforGeeks
        </p>

        <p id="add"></p>

        <script>
            // Variable a and b
            var a = "string1";
            var b = "string2";
            var object1 = { firstname: "Romy", 
                            lastname: "Kumari" };

            // Property using variable name
            object1.a = "first property";
            object1.b = "Second Property";

            document.getElementById("add").innerHTML = 
              "Added peoperty are : " + object1.a + 
              " and " + object1.b;
        </script>
    </body>
</html>
```

**输出：**

![](img/eb2e4538f6c88e9ad8bd08def44f3382.png)

## 示例2：使用括号运算符

如果要将属性与变量中存储的值相加，可以使用括号运算符。`object1.a`与`object1[a]`不同。

### HTML示例代码

```html
<!DOCTYPE html>
<html>
    <body>
        <p style="font-size: 30px; color: green;";>
          GeeksforGeeks
        </p>

        <p id="add"></p>

        <script>
            var myObj = new Object();

            var a = "string1";
            var b = "string2";
            // This can be accesses with
            // the value stored in b.
            myObj.b = "somewhere";
            // This can be accessed with the 
            // value stored in a that is string1
            myObj[a] = "whatever";

            document.getElementById("add").innerHTML = 
              "Added peoperty are : " + myObj.string1 +
              " and " + myObj.b;
        </script>
    </body>
</html>
```

**输出：**

![](img/a0f3efb827224a97387936a55b9b42ae.png)