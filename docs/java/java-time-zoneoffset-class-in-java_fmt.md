# java 中的 `java.time.ZoneOffset` 类

> 原文: [https://www.geeksforgeeks.org/java-time-zoneoffset-class-in-java/](https://www.geeksforgeeks.org/java-time-zoneoffset-class-in-java/)

时区偏移量是指时区与格林威治时间/世界协调时之间的时间差。这通常是一个固定而快速的小时数和分钟数。从 java 的[时间包](https://www.geeksforgeeks.org/tag/java-time-package/page/3/)开始，使用 `ZoneOffset` 类表示从 UTC 区域的固定区域偏移，继承 [`ZoneId` 类](https://www.geeksforgeeks.org/tag/java-zoneid/)，实现[可比接口](https://www.geeksforgeeks.com/comparable-vs-comparator-in-java/)。

> `public final class ZoneOffset extends ZoneId`
>
> `implements TemporalAdjuster, TemporalAccessor, Comparable<ZoneOffset>, Serializable`

`ZoneOffset` 类有三个字段:
*   `MAX_VALUE`: 这是支持的最大区域偏移量。
*   `MIN_VALUE`: 这是支持的最小区域偏移量。
*   `UTC`: 是世界协调时的时区偏移常数。

## 区域偏移类的方法

| **方法** | **描述** |
| --- | --- |
| `adjustInto(Temporal temporal)` | 此方法用于调整指定的时间对象，使其具有与此对象相同的偏移量。 |
| `compareTo(ZoneOffset other)` | 此方法按降序将此偏移量与另一个偏移量进行比较。 |
| `equals(Object obj)` | 此方法检查该偏移量是否等于另一个偏移量。 |
| `from(TemporalAccessor temporal)` | 此方法从时态对象获取 `ZoneOffset` 的实例。 |
| `get(TemporalField field)` | 此方法用于从该偏移量中获取指定字段的值作为 `int`。 |
| `getId()` | 此方法获取规范化的区域偏移量标识。 |
| `getLong(TemporalField field)` | 此方法从该偏移量中获取指定字段的值作为 `long`。 |
| `getRules()` | 此方法获取关联的时区规则。 |
| `getTotalSeconds()` | 此方法以秒为单位获取总区域偏移量。 |
| `hashCode()` | 此偏移量的哈希代码。 |
| `isSupported(TemporalField field)` | 此方法检查指定的字段是否受支持。 |
| `of(String offsetId)` | 此方法用于使用标识获取区域偏移量的实例。 |
| `ofHours(int hours)` | 此方法用于使用以小时为单位的偏移量来获取区域偏移量的实例。 |
| `ofHoursMinutes(int hours, int minutes)` | 此方法用于使用以小时和分钟为单位的偏移量来获取区域偏移量的实例。 |
| `ofHoursMinutesSeconds(int hours, int minutes, int seconds)` | 此方法使用以小时、分钟和秒为单位的偏移量来获取 `ZoneOffset` 的实例。 |
| `ofTotalSeconds(int totalSeconds)` | 此方法获取 `ZoneOffset` 的一个实例，该实例以秒为单位指定总偏移量。 |
| `query(TemporalQuery<R> query)` | 此方法使用指定的查询来查询此偏移量。 |
| `range(TemporalField field)` | 此方法获取指定字段的有效值范围。 |
| `toString()` | 此方法使用规范化的标识将该偏移量输出为字符串。 |

## 方法示例

### 1. `ofHoursMinutes()` 方法

> **语法:**
>
> `public static ZoneOffset ofHoursMinutes(int hours, int minutes)`

此方法用于使用以小时和分钟为单位的偏移量来获取 `ZoneOffset` 的实例。

```java
// Example of ofHoursMinutes() Method
import java.time.ZoneOffset;
public class GFG {
  public static void main(String[] args) {
    ZoneOffset zone = ZoneOffset.ofHoursMinutes(7,15);
    System.out.println(zone);
  }
}
```

**Output**

```java
+07:15
```

### 2. `ofHours()` 方法

> **语法:**
>
> `public static ZoneOffset ofHours(int hours)`

使用以小时为单位的偏移量获取 `ZoneOffset` 的实例。

```java
//Example of ofHours() Method
import java.time.*;
import java.time.ZoneOffset;
public class GFG {
  public static void main(String[] args) {
    ZoneOffset zone = ZoneOffset.ofHours(4);
    System.out.println(zone);
  }
}
```

**Output**

```java
+04:00
```