# 如何在 Java 中将一个流转换成一个地图

> 原文: [https://www.geeksforgeeks.org/how-to-convert-a-stream-into-a-map-in-java/](https://www.geeksforgeeks.org/how-to-convert-a-stream-into-a-map-in-java/)

Java 8 中引入的 [Stream API](https://www.geeksforgeeks.org/stream-in-java/) 用于处理对象的集合。流是支持各种方法的对象序列，这些方法可以通过流水线来产生所需的结果。

本文讨论了将一个流转换成一个 [Map](https://www.geeksforgeeks.org/map-interface-java-examples/) 的方法。

## 方法一: 使用 `Collectors.toMap()` 功能

`Collectors.toMap()` 方法以两个参数作为输入:

1.  **关键点映射器:** 该功能用于从流值中提取映射的关键点。
2.  **值映射器:** 该函数用于提取给定键的映射值。

以下是将给定流转换为地图的 `toMap` 函数的示例:

### 示例 1

Here, we will convert a string into a [Map](https://www.geeksforgeeks.org/map-interface-java-examples/) with the keys as the words of the string and the value as the length of each word.

```java
// Program to convert
// the Stream to Map

import java.io.*;
import java.util.stream.*;
import java.util.Arrays;
import java.util.Map;

class GFG {

    // Function to convert the string
    // to the map
    public static Map toMap(String input)
    {
        Map<String, Integer> lengthMap
            = Arrays.stream(input.split(" "))
                  .collect(Collectors.toMap(
                      value -> value,
                      value -> value.length()));

        return lengthMap;
    }

    public static void main(String[] args)
    {
        String input = "Geeks for Geek";

        System.out.println(toMap(input));
    }
}
```

**Output:**

```java
{Geek=4, for=3, Geeks=5}
```

在上例中，`toMap` 收集器采用两个λ函数作为参数:

1.  `(value -> value)`: 读取当前流值，作为地图的关键字返回。
2.  `(value -> value.length)`: 它读取当前流值，找到其长度，并将该值返回给定键的映射。

### 示例 2

现在，让我们使用 `toMap` 功能来执行更复杂的地图转换。在这里，我们将把用户列表转换成一个映射，其中用户标识是键，用户是值。

```java
// Program to convert User[] into
// Map<userId, User>

import java.util.Arrays;
import java.util.Map;
import java.util.stream.*;

// Implementing the User class
public class User {

    // Attributes of the user class
    private int userId;
    private String name;
    private String city;

    // Constructor
    public User(int userId, String name,
                String city)
    {
        this.userId = userId;
        this.name = name;
        this.city = city;
    }

    // Getters of the user class
    public int getUserId() { return userId; }
    public String getName() { return name; }
    public String getCity() { return city; }

    // Overriding the toString method
    // to return the custom string
    @Override
    public String toString()
    {
        return "User [userId = "
            + userId + ", name = "
            + name + ", city = "
            + city + "]";
    }
}

class GFG {

    // Function to convert the User
    // to the map
    public static Map toMap(User user1, User user2,
                            User user3)
    {
        Map<Integer, User> userMap
            = Arrays.asList(user1, user2, user3)
                  .stream()
                  .collect(Collectors.toMap(
                      user -> user.getUserId(),
                      user -> user));

        return userMap;
    }

    // Driver code
    public static void main(String[] args)
    {
        // Creating users
        User user1
            = new User(1, "User1", "Pune");
        User user2
            = new User(2, "User2", "Mumbai");
        User user3
            = new User(3, "User3", "Nagpur");

        System.out.println(toMap(user1, user2,
                                 user3));
    }
}
```

**输出:**

> { 1 = User [userId = 1, name = User1, city = Pune], 2 = User [userId = 2, name = User2, city = Mumbai], 3 = User [userId = 3, name = User3, city = Nagpur] }

## 方法二: 使用采集器 `groupingBy`

`groupingBy` 收集器将一个函数作为输入，并使用该函数创建一组流对象。以下是使用 `groupingBy` 收集器将流转换为地图的示例。

### 示例 1

In this example, we will convert a user stream into a map whose key is the city and the value is the users living in that city.

```java
// Java program to convert the User[]
// into Map<city, List<User>>

import java.util.Arrays;
import java.util.Map;
import java.util.List;
import java.util.stream.*;

// Implementing the User class
public class User {

    // Parameters of the user class
    private int userId;
    private String name;
    private String city;

    // Constructor of the User class
    public User(int userId, String name,
                String city)
    {
        this.userId = userId;
        this.name = name;
        this.city = city;
    }

    // Getter functions
    public int getUserId() { return userId; }
    public String getName() { return name; }
    public String getCity() { return city; }

    // Overriding the toString() method
    // to create a custom function
    @Override
    public String toString()
    {
        return "User [userId = "
            + userId + ", name = "
            + name + ", city = "
            + city + "]";
    }
}

class GFG {

    // Function to convert the user
    // object to the map
    public static Map toMap(User user1,
                            User user2,
                            User user3,
                            User user4,
                            User user5)
    {
        Map<String, List<User> >
            cityUserListMap
            = Arrays.asList(user1, user2, user3,
                            user4, user5)
                  .stream()
                  .collect(Collectors.groupingBy(
                      User::getCity));

        return cityUserListMap;
    }

    // Driver code
    public static void main(String[] args)
    {
        // Creating new users
        User user1
            = new User(1, "User1", "Pune");
        User user2
            = new User(2, "User2", "Mumbai");
        User user3
            = new User(3, "User3", "Nagpur");
        User user4
            = new User(4, "User4", "Pune");
        User user5
            = new User(5, "User5", "Mumbai");

        System.out.println(toMap(user1, user2,
                                 user3, user4,
                                 user5));
    }
}
```

**Output:**

> { Nagpur = [User [userId = 3, name = User3, city = Nagpur]], Pune = [User [userId = 1, name = User1, city = Pune], User [userId = 4, name = User4, city = Pune]] }

### 示例 2

如果我们需要比实际对象更多的信息，我们还可以通过为 `groupingBy` 提供一个额外的收集器。在这个例子中，我们将看到如何获得属于每个城市的用户数。

```java
// Java program to convert User[]
// into Map<city, countOfUser>

import java.util.Arrays;
import java.util.Map;
import java.util.stream.*;

// Implementing the user class
public class User {

    // Parameters of the user class
    private int userId;
    private String name;
    private String city;

    // Constructor
    public User(int userId, String name,
                String city)
    {
        this.userId = userId;
        this.name = name;
        this.city = city;
    }

    // Getter functions
    public int getUserId() { return userId; }
    public String getName() { return name; }
    public String getCity() { return city; }

    // Overriding the toString() method
    // to create a custom function
    @Override
    public String toString()
    {
        return "User [userId = "
            + userId + ", name = "
            + name + ", city = "
            + city + "]";
    }
}

class GFG {

    public static Map toMap(User user1,
                            User user2,
                            User user3,
                            User user4,
                            User user5)
    {
```

```java
Map<String, Long> cityUserCountMap = Arrays.asList(user1, user2, user3, user4, user5)
        .stream()
        .collect(
            Collectors.groupingBy(
                User::getCity,
                Collectors.counting()));

return cityUserCountMap;
    }

// Driver code
    public static void main(String[] args) {

// Creating new users
        User user1 = new User(1, "User1", "Pune");
        User user2 = new User(2, "User2", "Mumbai");
        User user3 = new User(3, "User3", "Nagpur");
        User user4 = new User(4, "User4", "Pune");
        User user5 = new User(5, "User5", "Mumbai");

System.out.println(toMap(user1, user2, user3, user4, user5));
    }
}
```

**输出:**

`{Nagpur=1, Pune=2, Mumbai=2}`