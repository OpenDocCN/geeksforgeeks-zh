# 使用 PHP 编写程序设计棋盘

> 原文: [https://www.geeksforgeeks.org/write-a-program-to-design-a-chess-board-using-php/](https://www.geeksforgeeks.org/write-a-program-to-design-a-chess-board-using-php/)

国际象棋是两个玩家之间进行的娱乐性和竞争性的棋盘游戏。它是在一个正方形棋盘上进行的，64 个正方形交替排列在一个 8 乘 8 的黑白网格中。在本文中，我们将学习如何使用 PHP 设计一个棋盘。

## 方法

使用 PHP 创建棋盘；我们必须运行 2 个循环，每个循环创建 8 个方块。
内部循环将根据一个值生成一个具有黑色/白色背景颜色的表格行。
如果该值是偶数，则生成黑色背景。
如果该值是奇数，则生成白色背景。

## 棋盘使用 For-Loop

### PHP

```php
<!DOCTYPE html>
<html>

<body>
    <table width="400px" border="1px" cellspacing="0px">
        <?php
        echo "Chess by GeeksforGeeks";
        $value = 0;

        for($col = 0; $col < 8; $col++) {
            echo "<tr>";
            $value = $col;

            for($row = 0; $row < 8; $row++) {
                if($value%2 == 0) {
                    echo "<td height=40px width=20px bgcolor=black></td>";
                    $value++;
                }
                else {
                    echo "<td height=40px width=20px bgcolor=white></td>";
                    $value++;
                }
            }
            echo "</tr>";
        }
        ?>
    </table>
</body>

</html>
```