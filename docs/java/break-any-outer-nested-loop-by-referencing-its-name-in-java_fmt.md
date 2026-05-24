# 通过在 Java 中引用其名称来中断任何外部嵌套循环

> 原文：[https://www.geeksforgeeks.org/break-any-outer-nested-loop-by-referencing-its-name-in-java/](https://www.geeksforgeeks.org/break-any-outer-nested-loop-by-referencing-its-name-in-java/)

一个[嵌套循环](https://www.geeksforgeeks.org/java-nested-loops-with-examples/)是一个循环内的循环，一个内循环体内的一个外循环。

## 工作

- 外循环的第一次触发内循环，内循环执行直到完成。
- 然后外循环第二次再次触发内循环。
- 重复此过程直到外循环结束。
- 在[Java 中的 `break` 语句](https://www.geeksforgeeks.org/break-statement-in-java/)会中断此过程。

## 嵌套循环的功能

```java
// Nested for loop

import java.io.*;
class GFG {

    public static void main(String[] args)
    {
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                System.out.print("GFG! ");
            }
            System.out.println();
        }
    }
}
```

**输出**

```java
GFG! GFG! GFG! 
GFG! GFG! GFG! 
GFG! GFG! GFG! 
```