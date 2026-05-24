# 计算戈朗两个日期之间的小时、天、分、秒总数

> 原文:[https://www . geesforgeks . org/computing-golang 中两个日期之间的总小时数-天-分-秒/](https://www.geeksforgeeks.org/calculating-total-number-of-hours-days-minutes-and-seconds-between-two-dates-in-golang/)

为了得到两个日期之间的天数，我们可以计算从开始的 0/0/0000 到第一个日期和第二个日期之间的天数，并计算它们的差值。

**示例:**

```go
Input: 2020-04-27 23:35:00, 2018-5-12 12:43:23
Output: 716 days, 10 hours, 51 minutes, 37 seconds

Input: 2014-02-25 05:50:20, 2003-12-13 21:42:12
Output: 3726 days, 8 hours, 8 minutes, 8 seconds

```

为了计算时间差，我们可以计算小时 2-小时 1、分钟 2-分钟 1、秒 2-秒 1，并执行一些操作(如代码中从第 65 行到第 80 行所示)以避免负值。

```go
// Golang program for Calculating the total number
// of Hours, Days, Minutes and Seconds 
// between two dates
package main

import (
    "fmt"
    "time"
)

// This function counts the
// number of leap years
// since the starting of time
// to the current year that
// is passed
func leapYears(date time.Time) (leaps int) {

    // returns year, month,
    // date of a time object
    y, m, _ := date.Date()

    if m <= 2 {
        y--
    }
    leaps = y/4 + y/400 - y/100
    return leaps
}

// The function calculates the
// difference between two dates and times
// and returns the days, hours, minutes,
// seconds between two dates

func getDifference(a, b time.Time) (days, hours, minutes, seconds int) {

    // month-wise days
    monthDays := [12]int{31, 28, 31, 30, 31,
                 30, 31, 31, 30, 31, 30, 31}

    // extracting years, months,
    // days of two dates
    y1, m1, d1 := a.Date()
    y2, m2, d2 := b.Date()

    // extracting hours, minutes,
    // seconds of two times
    h1, min1, s1 := a.Clock()
    h2, min2, s2 := b.Clock()

    // totalDays since the 
    // beginning = year*365 + number_of_days
    totalDays1 := y1*365 + d1

    // adding days of the months 
    // before the current month
    for i := 0; i < (int)(m1)-1; i++ {
        totalDays1 += monthDays[i]
    }

    // counting leap years since
    // beginning to the year "a"
    // and adding that many extra 
    // days to the totaldays
    totalDays1 += leapYears(a)

    // Similar procedure for second date
    totalDays2 := y2*365 + d2

    for i := 0; i < (int)(m2)-1; i++ {
        totalDays2 += monthDays[i]
    }

    totalDays2 += leapYears(b)

    // Number of days between two days
    days = totalDays2 - totalDays1

    // calculating hour, minutes,
    // seconds differences
    hours = h2 - h1
    minutes = min2 - min1
    seconds = s2 - s1

    // if seconds difference goes below 0,
    // add 60 and decrement number of minutes
    if seconds < 0 {
        seconds += 60
        minutes--
    }

    // performing similar operations
    // on minutes and hours
    if minutes < 0 {
        minutes += 60
        hours--
    }

    // performing similar operations
    // on hours and days
    if hours < 0 {
        hours += 24
        days--
    }

    return days, hours, minutes, seconds

}

// Driver code

func main() {

    // Syntax for time date:
    // d := time.Date(year, month, days, hours,
    // minutes, seconds, nanoseconds, timeZone)

    date1 := time.Date(2020, 4, 27, 23, 35, 0, 0, time.UTC)
    date2 := time.Date(2018, 5, 12, 12, 43, 23, 0, time.UTC)

    // if date1 occurs after date2 then 
    // swap days since absolute 
    // difference is being calculated
    if date1.After(date2) {
        date1, date2 = date2, date1
    }
    // Calling function and getting
    // difference between two dates
    days, hours, minutes, seconds := getDifference(date1, date2)

    // Printing the difference
    fmt.Printf("%v days, %v hours, %v minutes, %v seconds",
                             days, hours, minutes, seconds)

}
```

**输出:**

```go
716 days, 10 hours, 51 minutes, 37 seconds

```