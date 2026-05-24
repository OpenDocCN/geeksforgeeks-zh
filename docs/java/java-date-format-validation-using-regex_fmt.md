# Java 使用 Regex 的日期格式验证

> 原文：[https://www.geeksforgeeks.org/java-date-format-validation-using-regex/](https://www.geeksforgeeks.org/java-date-format-validation-using-regex/)

我们使用[`Pattern.compile()`](https://www.geeksforgeeks.org/regular-expressions-in-java/)方法将给定的正则表达式编译成一个模式。这里正则表达式是要编译的表达式。

```java
// Java program to check if given date is
// valid or not.
import java.util.regex.Matcher;
import java.util.regex.Pattern;

public class GeeksforGeeks {

    // Returns true if d is in format
    // dd/mm/yyyy
    public static boolean isValidDate(String d)
    {
        String regex = "^(1[0-2]|0[1-9])/(3[01]"
                     + "|[12][0-9]|0[1-9])/[0-9]{4}$";
        Pattern pattern = Pattern.compile(regex);
        Matcher matcher = pattern.matcher((CharSequence)d);
        return matcher.matches();
    }

    public static void main(String args[])
    {
        System.out.println(isValidDate("10/12/2016"));
        System.out.println(isValidDate("10/02/18"));
    }
}
```

输出：
```
true
false
```

## 验证日期的更多方法：

1.  [`SimpleDateFormat`](https://www.geeksforgeeks.org/java-text-simpledateformat-class-set-1/)类。我们可以使用这个类的解析方法来验证日期。
2.  [编写我们自己的方法来检查日期是否有效。](https://www.geeksforgeeks.org/program-check-date-valid-not/)