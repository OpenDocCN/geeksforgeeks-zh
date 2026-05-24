# CSS 频率值

> 原文:[https://www.geeksforgeeks.org/css-frequency-value/](https://www.geeksforgeeks.org/css-frequency-value/)

频率是 CSS 值的数据类型。它像说话频率一样代表声音的频率维度。该值当前未被任何 CSS 属性使用。回到它被用来测量声波频率之前。它保存一个带有单位(赫兹或千赫)的数字。

**语法:**

```html
frequency: number Hz | kHz
```

**单位:**该 CSS 值接受两种类型的单位，如上所述，如下所述:

*   **Hertz:** This unit represents the frequency in Hertz (20Hz).
*   **kHz:** This unit represents the frequency in kHz.

**注:**这两个单位有关系(1kHZ = 1000Hz)。

以下示例说明了 CSS 值频率单位:

**例:**

```html
Valid: 120Hz
         14.44kHz or 14440 Hz
         160Khz (It is case insensitive)
         +-0Hz

Invalid: 180 (Unit is missing)
         48 Hz (Space between the number and unit)
         0 (Invalid, it can be unitless but not allowed)
```

**示例:**下面的代码在任何浏览器中都不起作用，因为该属性已被弃用，不再被任何浏览器支持。

## HTML

```html
<!DOCTYPE html>
<html>

<body style="text-align: center;">
    <h1 style="color: green;">
        GeekSforGeeks
    </h1>

<p>CSS Value | Frequency </p>

    <audio>
        <source src="sample.mp3"
            type="audio/mpeg"
            frequency="120Hz">
    </audio>
</body>

</html>
```

**支持的浏览器:**目前任何浏览器都不支持该值。