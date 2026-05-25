# JavaScript 中 `Object.freeze()` 和 `const` 的区别

> 原文: [https://www.geeksforgeeks.org/difference-between-object-freeze-and-const-in-javascript/](https://www.geeksforgeeks.org/difference-between-object-freeze-and-const-in-javascript/)

自发布以来，ES6 为 JavaScript 带来了几个新的特性和方法。这些新功能包括 `Object.freeze()` 方法和 `const` 关键字。有时候人们会把 `Object.freeze()` 方法和 `const` 搞混，但是 `Object.freeze()` 和 `const` 是完全不同的。在本文中，我们将解释这两者之间的区别。

## `const`

`const` 关键字创建一个对值的**只读引用**。由 `const` 关键字创建的变量是不可变的。换句话说，您不能将它们重新分配给不同的值。试图重新分配常量变量将导致**类型错误**。

### Example 1:

```javascript
<script>
    let myName = "Geeksforgeeks"
    console.log(myName)

    // Uncaught TypeError
    myName = "gfg"                   
</script>
```

`const` 关键字确保创建的变量是只读的。但这并不意味着常量变量引用的实际值是不可变的。即使变量是常量，您也可以更改其属性的值。但是您不能为该常量重新分配不同的值。

### Example 2:

```javascript
<script>
    const person = {
        name: "Geeksforgeeks"
    };

    // No TypeError
    person.name = "gfg";
    console.log(person.name);
</script>
```

## `Object.freeze()` 方法

如果要使对象的值不可变，则必须使用 `Object.freeze()` 方法将其冻结。

### Example 1:

```javascript
<script>
    const person = Object.freeze({name: "Geeksfreeze"});

    // TypeError
    person.name = "gfg";
</script>
```

`Object.freeze()` 方法比较浅，意思是可以冻结对象的属性，而不是属性引用的对象。

### Example 2:

```javascript
<script>
    const person = Object.freeze({
        name: 'Geeksforgeeks',
        address: {
            city: "Noida"
        }
    });
</script>
```

然而，`person.address` 对象并不是不可变的，可以向 `person.address` 对象添加新属性，如下所示：

```javascript
// No TypeError
person.address.country = "India";
```

## 结论

*   `const` 防止变量被重新赋值。
*   `Object.freeze()` 防止对象可变。