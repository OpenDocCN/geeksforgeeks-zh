# JavaScript 中的析构赋值

> 原文: [https://www.geeksforgeeks.org/destructuring-assignment-in-javascript/](https://www.geeksforgeeks.org/destructuring-assignment-in-javascript/)

析构赋值是一个 JavaScript 表达式，允许将数组中的值或对象中的属性解包为不同的变量。数据可以从数组、对象、嵌套对象中提取，并赋值给变量。在析构赋值中，左侧定义了应该从源变量中解包哪个值。

一般来说，提取数组的实现方式如下所示:

**例:**

```javascript
<script>
var names = ["alpha", "beta", "gamma", "delta"];

var firstName = names[0];
var secondName = names[1];

console.log(firstName);//"alpha"
console.log(secondName);//"beta"
</script>
```

**输出:**

```
alpha
beta
```

## 语法

### 数组析构

```javascript
var x, y;
[x, y] = [10, 20];
console.log(x); // 10
console.log(y); // 20
```

或者

```javascript
[x, y, ...restof] = [10, 20, 30, 40, 50];
console.log(x); // 10
console.log(y); // 20
console.log(restof); // [30, 40, 50]
```

### 对象析构

```javascript
({ x, y} = { x: 10, y: 20 });
console.log(x); // 10
console.log(y); // 20
```

或者

```javascript
({x, y, ...restof} = {x: 10, y: 20, m: 30, n: 40});
console.log(x); // 10
console.log(y); // 20
console.log(restof); // {m: 30, n: 40}
```

## 数组析构

利用 JavaScript 数组中的析构赋值可能出现的情况，下面列出了所有的例子:

### 示例 1

当使用**析构赋值**时，同样的提取可以通过以下实现完成。

```javascript
<script>
var names = ["alpha", "beta", "gamma", "delta"];
var [firstName, secondName] = names;

console.log(firstName);//"alpha"
console.log(secondName);//"beta"

//Both of the procedure are same
var [firstName, secondName] = ["alpha", "beta", "gamma", "delta"];

console.log(firstName);//"alpha"
console.log(secondName);//"beta
</script>
```

**输出:**

```
alpha
beta
alpha
beta
```

### 示例 2

数组元素也可以使用逗号分隔符跳过。单个逗号可以用来跳过一个数组元素。**扩展运算符**和数组析构之间的一个关键区别是，扩展运算符将所有数组元素解包为一个逗号分隔的列表，这不允许我们选择要分配给变量的元素。要跳过整个数组，可以使用与数组元素数量相同的逗号数量。

```javascript
<script>
var [firstName,,thirdName] = ["alpha", "beta", "gamma", "delta"];

console.log(firstName);//"alpha"
console.log(thirdName);//"gamma"
</script>
```

**输出:**

```
alpha
gamma
```

### 示例 3

为了将一些数组元素分配给变量，而将其余的数组元素分配给单个变量，可以通过使用**剩余运算符（...）**来实现，如下所示。但剩余运算符的一个限制是，它只在最后一个元素上正确工作，这意味着无法在留下最后一个元素的情况下获得一个子数组。

```javascript
<script>
var [firstName,,...lastName] = ["alpha", "beta", "gamma", "delta"];

console.log(firstName);//"alpha"
console.log(lastName);//"gamma, delta"
</script>
```

**输出:**

```
alpha
  0: "gamma"
  1: "delta"
```

### 示例 4

值也可以使用析构赋值进行交换，如下所示:

```javascript
<script>
var names = ["alpha", "beta", "gamma", "delta"];

console.log(firstName);//"alpha"
console.log(secondName);//"beta"

//After swapping
[firstName, secondName] = [secondName, firstName]

console.log(firstName);//"beta"
console.log(secondName);//"alpha"
</script>
```

**输出:**

```
beta
alpha
```

### 示例 5

数据也可以从函数返回的数组中提取。使用析构赋值的一个优点是，不需要在函数中操作整个对象，只需要复制所需的字段。

```javascript
<script>
function NamesList() {
        return ["alpha", "beta", "gamma", "delta"]
    }
var[firstName, secondName] = NamesList();

console.log(firstName);//"alpha"
console.log(secondName);//"beta"
</script>
```

**输出:**

```
alpha
beta
```

### 示例 6

在 *ES5* 中，从对象分配变量的实现是:

```javascript
<script>
var marks = {x: 21, y: -34, z: 47 };

var x = marks.x; // x = 21
var y = marks.y; // y = -34
var z = marks.z; // z = 47

console.log(x);
console.log(y);
console.log(z);
</script>
```

**输出:**

```

```

### 示例 7

在 *ES6* 中使用析构赋值的实现是:

```javascript
<script> 
var marks = {x: 21, y: -34, z: 47 };

const { x, y, z } = marks; // x = 21, y = -34, z = 47

console.log(x); 
console.log(y); 
console.log(z); 
</script> 
```

**输出:**

```

```

## 对象析构

### 示例

嵌套对象也可以使用析构语法进行析构。

```javascript
<script>
const marks = {
  section1: { alpha: 15, beta: 16},
  section2: { alpha: -31, beta: 19 }
};
const { section1 : { alpha: alpha1, beta: beta1 }} = marks;
console.log(alpha1, beta1); // 15, 16
</script>
```

**输出:**

```
15 16
```