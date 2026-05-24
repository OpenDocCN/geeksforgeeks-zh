# 设计一个类似OYO客房的在线酒店预订系统

> 原文：[https://www.geeksforgeeks.org/design-online-hotel-booking-system-like-oyo-rooms/](https://www.geeksforgeeks.org/design-online-hotel-booking-system-like-oyo-rooms/)

我们需要设计一个在线酒店预订系统，用户可以在给定城市搜索酒店并预订。这是一个面向对象的设计问题，所以我没有在这个解决方案中写完整的代码。我只创建了类和属性。

解：
主类：
1. `User`
2. `Room`
3. `Hotel`
4. `Booking`
5. `Address`
6. `Facilities`

## Java代码框架

```java
// Java code skeleton to design an online hotel
// booking system.
Enums:

public enum RoomStatus {
    EMPTY,
    NOT_EMPTY;
}

public enum RoomType {
    SINGLE,
    DOUBLE,
    TRIPLE;
}

public enum PaymentStatus {
    PAID,
    UNPAID;
}

public enum Facility {
    LIFT,
    POWER_BACKUP,
    HOT_WATER,
    BREAKFAST_FREE,
    SWIMMING_POOL;
}

class User {
    int userId;
    String name;
    Date dateOfBirth;
    String mobNo;
    String emailId;
    String sex;
}

// For the room in any hotel
class Room {
    int roomId; // roomNo
    int hotelId;
    RoomType roomType;
    RoomStatus roomStatus;
}

class Hotel {
    int hotelId;
    String hotelName;
    Address address;

    // hotel contains the list of rooms
    List<Room> rooms;
    float rating;
    Facilities facilities;
}

// a new booking is created for each booking
// done by any user
class Booking {
    int bookingId;
    int userId;
    int hotelId;

    // We are assuming that in a single
    // booking we can book only the rooms
    // of a single hotel
    List<Room> bookedRooms;

    int amount;
    PaymentStatus status_of_payment;
    Date bookingTime;
    Duration duration;
}

class Address {
    String city;
    String pinCode;
    String state;
    String streetNo;
    String landmark;
}

class Duration {
    Date from;
    Date to;
}

class Facilities {
    List<Facility> facilitiesList;
}
```

让我解释一下这些类以及它们之间的关系。

这里定义的枚举是不言自明的。`User`、`Room`和`Address`类也是不言自明的。`Facilities`类包含酒店提供的设施列表（枚举）。如果需要，我们可以在`Facility`枚举中添加更多设施。`Duration`类有两个属性“从”和“到”，这是显而易见的。

现在，“`Hotel`”类包含：
1. `List<Room>` // 这是酒店的房间列表
2. `Address`类 // 其地址
3. `Facilities` // 其拥有的设施

“`Booking`”类包含：
1. `User` // 关于用户的信息
2. `Hotel` // 酒店信息
3. `List<Room>` // 房间列表
4. 付款状态等。

本类其他字段也不言自明。

本文由 [**Pooja Kamal**](https://www.facebook.com/pooja.kamal.338) 供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [write.geeksforgeeks.org](https://write.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 review-team@geeksforgeeks.org。看到你的文章出现在极客博客主页上，帮助其他极客。

如果发现有不正确的地方，或者想分享更多关于上述话题的信息，请写评论。