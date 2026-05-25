# ES6 类

> 原文: [https://www.geeksforgeeks.org/es6-classes/](https://www.geeksforgeeks.org/es6-classes/)

面向对象编程有三个核心概念：**对象**、**类**和**方法**。ES6 JavaScript 支持面向对象编程组件。

*   **对象:** 对象是任何实体的实时呈现。
*   **类:** 类是创建对象的蓝图或计划。
*   **方法:** 方法定义了对象之间的交互行为。

一个类包含**构造函数**和**函数**。构造函数负责为类的对象分配内存。函数则负责定义对象的行为。将构造函数和函数组合在一起，就构成了**类**。

在 ES6 中创建类，需要使用 `class` 关键字。

## 语法

声明类：

```
class Class_name {
}
```

类表达式：

```
var var_name = new Class_name {
}
```

## 示例

以下示例将说明 ES6 类：

```javascript
<script>
class gfg {

    // Constructor
    constructor(name, estd, rank){
        this.n = name;
        this.e = estd;
        this.r = rank;
    }

    // Function
    decreaserank(){
        this.r -= 1;
    }
}
const geeks = new gfg("geeks", 2009, 43)

geeks.decreaserank();

document.write(geeks.r); //Output 42
</script>
```

**输出:**

```
42
```

上面的例子声明了一个类 `gfg`。该类的构造函数接受三个参数——`name`、`estd` 和 `rank`。`this` 关键字引用了类的当前实例。`decreaserank()` 函数在类中，用于减少排名的值。

## 类继承

ES6 类支持继承。继承允许从现有的类创建新的类。ES6 中有两种类型的类：

*   **父类/超类:** 被扩展以创建新类的类称为父类或超类。
*   **子类/子类:** 新创建的类称为子类。子类继承父类的所有属性和方法，但构造函数需要单独处理。

### 语法

```
class child_name extends parent_name
```

### 示例

```javascript
<script>
class geeks {
   constructor(g) {
      this.Character = g
   }
}
class GeeksforGeeks extends geeks {
   disp() {
      console.log("No of Character:  "+this.Character)
   }
}
var obj = new GeeksforGeeks(13);
obj.disp()
</script>
```

**输出:**

```
No of Character: 13
```

继承分为三种类型：

*   **单一继承:** 每个类都可以从一个父类扩展而来。
*   **多重继承:** 一个类可以从多个类继承。ES6 不支持多重继承。
*   **多级继承:** 一个类可以从另一个类（该类本身继承自父类）继承。

```
class Child extends Root
class Leaf extends Child
// So the leaf extends root indirectly
```

## Super 关键字

`super` 关键字帮助子类调用父类的方法或访问父类的属性。

```
super.object
```

### 示例

```javascript
<script>
class GeeksforGeeks {
   doPrint() {
      console.log("This doPrint() from Parent called.")
   }
}
class gfg extends GeeksforGeeks {
   doPrint() {
      super.doPrint()
      console.log("This doPrint() is printing a string.")
   }
}
var obj = new gfg()
obj.doPrint()
</script>
```

**输出:**

```
This doPrint() from Parent called.
This doPrint() is printing a string.
```