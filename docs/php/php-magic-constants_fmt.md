# PHP 魔术常量

> 原文：[https://www.geeksforgeeks.org/php-magic-constants/](https://www.geeksforgeeks.org/php-magic-constants/)

**魔术常量：** 魔术常量是 PHP 中的预定义常量，根据使用情况使用。这些常量由各种扩展创建。PHP 中有九个魔术常量，所有常量都是在编译时解析的，与在运行时解析的常规常量不同。有八个以双下划线(`__`)开头和结尾的魔术常量。
下面列出了所有常量，示例代码如下：

## `__LINE__`

这个魔术常量返回文件的当前行号。如果您在程序文件中的某个地方使用了这个魔术常量，那么这个常量将在编译时显示行号。

**语法：**

```php
__LINE__
```

**示例：**

```php
<?php

echo "The Line number is : ". __LINE__;

?>
```

**输出：**

```php
The Line number is : 3
```

## `__FILE__`

此魔术常量返回已执行文件的完整路径和文件名。

**语法：**

```php
__FILE__
```

**示例：**

```php
<?php

echo "The file name is : ". __FILE__;

?>
```

**输出：**

```php
The file name is : /home/3d27a639c57aaed9efa5880e613bc273.php
```

## `__DIR__`

这个魔术常量返回执行文件的目录。

**语法：**

```php
__DIR__
```

**示例：**

```php
<?php

echo "The directory is : ". __DIR__;

?>
```

**输出：**

```php
The directory is : /home
```

## `__FUNCTION__`

此魔术常量返回包含此魔术常量的函数的名称。

**语法：**

```php
__FUNCTION__
```

**示例：**

```php
<?php
function Geeks(){
    echo "The function name is : ". __FUNCTION__;
}
Geeks();
?>
```

**输出：**

```php
The function name is : Geeks
```

## `__CLASS__`

此魔术常量返回包含此魔术常量的类名。

**语法：**

```php
__CLASS__
```

**示例：**

```php
<?php
class Geeks
{
    public function getClassName(){
        return __CLASS__;
    }
}
$obj = new Geeks();
echo $obj->getClassName();
?>
```

**输出：**

```php
Geeks
```

## `__METHOD__`

此魔术常量返回包含此魔术常量的方法名。

**语法：**

```php
__METHOD__
```

**示例：**

```php
<?php
class Company
{
    public function GeeksforGeeks(){
        return __METHOD__;
    }
}
$obj = new Company();
echo  $obj->GeeksforGeeks();
?>
```

**输出：**

```php
Company::GeeksforGeeks
```

## `__NAMESPACE__`

此魔术常量返回包含此魔术常量的当前命名空间。

**语法：**

```php
__NAMESPACE__
```

**示例：**

```php
<?php
namespace GeeksforGeeks;

class Company {
    public function gfg() {
        return __NAMESPACE__;
    }
}

$obj = new Company();
echo  $obj->gfg();

?>
```

**输出：**

```php
GeeksforGeeks
```

## `__TRAIT__`

此魔术常量返回包含此魔术常量的特征名称。

**语法：**

```php
__TRAIT__
```

**示例：**

```php
<?php
trait GeeksforGeeks{ 
    function gfg(){ 
        echo __TRAIT__; 
        } 
    } 
    class Company{ 
        use GeeksforGeeks; 
        } 
    $a = new Company; 
    $a->gfg(); 
?>
```

**输出：**

```php
GeeksforGeeks
```

## `ClassName::class`

这个魔术常量返回完全限定的类名。

**语法：**

```php
ClassName::class
```

**示例：**

```php
<?php

namespace Computer_Science_Portal;
class Geeks{ }

echo Geeks::class;//ClassName::class

?>
```

**输出：**

```php
Computer_Science_Portal\Geeks
```

**引用：** [https://www.php.net/manual/en/language.constants.predefined.php](https://www.php.net/manual/en/language.constants.predefined.php)