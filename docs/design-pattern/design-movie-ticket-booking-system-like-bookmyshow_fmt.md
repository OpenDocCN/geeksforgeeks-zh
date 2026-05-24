# 设计一个像 Bookmyshow 一样的电影票预约系统

> 原文: [https://www.geeksforgeeks.org/design-movie-ticket-booking-system-like-bookmyshow/](https://www.geeksforgeeks.org/design-movie-ticket-booking-system-like-bookmyshow/)

我们需要设计一个在线电影票预订系统，用户可以在该系统中搜索给定城市的电影并预订。本文将向您解释预订系统的体系结构。

## 如何实施座位预订流程？

解决方案:

用于用户角色的主要类:

*   `User`
*   `Movie`
*   `Theater`
*   `Booking`
*   `Address`
*   `Facility`

### Java 语言

```
// Java skeleton code to design an online movie
// booking system.
Enums :

public enum SeatStatus {
    SEAT_BOOKED,
    SEAT_NOT_BOOKED;
}

public enum MovieStatus {
    Movie_Available,
    Movie_NotAvailable;
}

public enum MovieType {
    ENGLISH,
    HINDI;
}

public enum SeatType {
    NORMAL,
    EXECUTIVE,
    PREMIUM,
    VIP;
}

public enum PaymentStatus {
    PAID,
    UNPAID;
}

class User {
    int userId;
    String name;
    Date dateOfBirth;
    String mobNo;
    String emailId;
    String sex;
}

class Movie {
    int movieId;
    int theaterId;
    MovieType movieType;
    MovieStatus movieStatus;
}

class Theater {
    int theaterId;
    String theaterName;
    Address address;
    List<Movie> movies;
    float rating;
}

class Booking {
    int bookingId;
    int userId;
    int movieId;
    List<Movie> bookedSeats;
    int amount;
    PaymentStatus status_of_payment;
    Date booked_date;
    Time movie_timing;
}

class Address {
    String city;
    String pinCode;
    String state;
    String streetNo;
    String landmark;
}
```

这是一个 OOP 设计问题，所以不需要完整的代码。上面的代码只有类和属性。在上面的代码中，您可以看到枚举是不言自明的。
我们有一个 `User` 类，里面保存着用户的详细信息。
`Theater` 类，保留剧院名称、地址和当前正在播放的电影列表。
`Booking` 类让你预订特定剧院的座位。它保留了电影，支付类的参考。

## 如何处理两个人试图同时进入同一个座位的情况？

让我们来看看将从主类中调用的 `SeatBook` 和 `Transaction` 类。在上面的代码中，我们稍微扩展了一下上面代码中没有显示的支付过程。在 `SeatBook` 类中，我们也将引用 `Transaction` 类。

现在，为了确保两个人几乎同时访问同一个座位，我们将使用 `Thread` 类的同步方法，并调用属于每个登录用户的线程。

### Java 语言

```
class SeatBook {
    Transaction transaction_obj;
    bool seats[total_seats];
    String place;
    String ticketType;

    bool check_availability();

    int position_of_seat() {
        return seat_pos_in_theater;
    }

    void multiple_tickets();

    void final_booking() {
        place = position_of_seat();
        if (single_ticket)
            continue;
        else
            multiple_ticket_booking();

        transaction_obj.pay(ticketType, seats_booked, place);
    }
}
```