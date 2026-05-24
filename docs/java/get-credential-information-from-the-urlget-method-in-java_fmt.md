# 从 Java 中的 URL(GET 方法)获取凭证信息

> 原文: [https://www.geeksforgeeks.org/get-credential-information-from-the-urlget-method-in-java/](https://www.geeksforgeeks.org/get-credential-information-from-the-urlget-method-in-java/)

给定一个字符串形式的网址，任务是在 `GET 方法`中从网址中提取用户名、密码、配置文件、角色和密钥。

### 示例:

**输入:**
```
http://www.geeksforgeeks.com/signin/service?username=test&pwd=test&profile=developer&role=ELITE&key=manager
```

**输出:**
```
username: test
pwd: test
profile: developer
role: ELITE
key: manager
```

**输入:**
```
http://www.geeksforgeeks.com/signin/service?username=Vikas&pwd=1@@2&profile=developer&role=SoftwareDeveloper&key=Assitant
```

**输出:**
```
username: Vikas
pwd: 1@@2
profile: developer
role: SoftwareDeveloper
key: Assitant
```

### 进场:

*   首先，使用 `split` 方法从给定的网址中删除网络链接。
*   其次，拆分找到 `&` 运算符的网址。
*   最后，将每个索引值从 `=` 替换为 `:`。

下面是上述方法的实现:

## Java 语言

```java
// Java Program to Get Credential
// Information From the URL(GET Method)
import java.util.*;
import java.io.*;
public class ExchangeCharacter {

    public static void main(String args[]) throws Exception
    {
        BufferedReader scan = new BufferedReader(
            new InputStreamReader(System.in));

        // taking url as a string
        String url = "http://www.geeksforgeeks.com/signin/service?username=Vikas&pwd=1@@2&profile=developer&role=SoftwareDeveloper&key=Assitant";
        String str[] = url.split("\\?");
        String arr[] = str[1].split("&");
        for (String s : arr) {
            System.out.println(s.replace("=", ": "));
        }
    }
}
```

### 输出:

```java
username: Vikas
pwd: 1@@2
profile: developer
role: SoftwareDeveloper
key: Assitant
```