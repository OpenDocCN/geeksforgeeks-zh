# self 和 $this 的区别？

> 原文: [https://www.geeksforgeeks.org/what-is-the-difference-between-self-and-this/](https://www.geeksforgeeks.org/what-is-the-difference-between-self-and-this/)

关键字 `self` 仅用于指代该类范围内的当前类本身，而 `$this` 用于指代特定类实例的成员变量和函数。

## self 运算符

`self` 运算符代表当前类，因此用于访问类变量或静态变量，因为这些成员属于某个类，而不是该类的对象。

**语法:**

```php
self::$static_member
```

## $this 运算符

`$this`，正如其名，是一个对象。`$this` 表示类的当前对象。它用于访问类的非静态成员。

**语法:**

```php
$that->$non_static_member;
```

## 在 PHP 中何时使用 self over $this

**例:**

### PHP

```php
<?php
    class StudentDetail{
        public $name;
        public static $age;

        public function getName() {
            return $this->name;
        }

        public static function getAge() {
            return self::$age;
        }

        public function getStudentAge() {
            return self::getAge();
        }
    }

    $obj = new StudentDetail();

    $obj->name = "GFG";

    StudentDetail::$age = "18";

    echo "Name : " .$obj->getName()."\xA";
    echo "Age  : " .StudentDetail::getStudentAge();
?>
```

**Output**

```text
Name : GFG
Age  : 18
```

## self 与 $this 的区别

| self | $this |
| :--- | :--- |
| `self` 关键字前不需要 `$` 符号。 | 当引用类成员时，`$this` 关键字前应加上 `$` 符号。 |
| 为了访问类变量和方法，使用作用域解析运算符 (`::`)。 | 为了访问类变量和方法，使用箭头运算符 (`->`)。 |
| `self` 关键字用于访问程序中存在的类的静态成员。 | `$this` 是一个非静态成员，用于访问程序中存在的类的实例。 |
| `self` 关键字指向类成员，但不指向该类的任何特定对象。 | `$this` 可以指向类的选定实例的成员变量和函数。 |