# 萨斯萨斯萨斯:颜色模块

> 原文:[https://www.geeksforgeeks.org/sass-sasscolor-module/](https://www.geeksforgeeks.org/sass-sasscolor-module/)

SASS 提供了许多内置模块，包含各种有用的功能和一些混合，使其易于使用。所有内置模块都以 sass 开头:表明它们不同于其他模块，是 SASS 本身的一部分。内置模块之一是 **sass:color** 模块。该模块用于从现有颜色创建新颜色。本模块列出了使用 sass 编码时可以直接使用的功能:

*   **color.adjust():** This function increases or decreases different properties of the color by some fixed amount.

    **语法:**

    ```html
    color.adjust($color,
      $red: null, $green: null, $blue: null,
      $hue: null, $saturation: null, $lightness: null,
      $alpha: null)
    adjust-color(...)
    ```

    该函数将为每个关键字参数传递的值添加到颜色的相应属性中，并返回调整后的颜色。当同时指定 RGB 属性和 HSL 属性时，它会引发错误。每个可选参数必须是一个数字。RGB 参数必须是无单位的，并且在 **-255 和 255** 之间(包括这两个值)。`hue`参数必须以`deg`为单位或者没有单位。`saturation`和`lightness`参数必须始终在 **-100%和 100%** 之间(包括这两个参数)，并且可以是无单位的。`alpha`参数必须是无单位的，并且在 **-1 和 1** 之间(包括两者)。

    **示例:**

    ```html
    @debug color.adjust(#2cb890, $green: 20);
    @debug color.adjust(#35785f, $red: -20, $blue: 30);
    @debug color.adjust(#21787d, 
            $lightness: -20%, $alpha: -0.5); 
    ```

    **输出:**

    ```html
    #2ccc91
    #21787d
    rgba(12, 43, 44, 0.5)

    ```

*   **adjust-hue():** This function increases or decreases the color’s hue value.

    **语法:**

    ```html
    adjust-hue($color, $degrees)
    ```

    色调值必须始终是介于**-360 度和 360 度**(两者都包括)之间的数字，才能将其添加到颜色的色调中。它可能是无单位的。

    **示例:**

    ```html
    @debug adjust-hue(#0c2b2c, -50deg);
    ```

    **输出:**

    ```html
    #0c2c12

    ```

*   **color.alpha():** This function returns the alpha channel of a color as a number between 0 and 1.

    **语法:**

    ```html
    color.alpha($color)
    alpha($color)
    opacity($color)
    ```

    **示例:**

    ```html
    @debug color.alpha(#e1d7d2);
    @debug color.opacity(rgb(210, 225, 221, 0.4));
    @debug alpha(opacity=20);
    ```

    **输出:**

    ```html
    1
    0.4
    alpha(opacity=20)

    ```

*   **color.change():** This function sets one or more properties of a color to new color values.

    **语法:**

    ```html
    color.change($color,
      $red: null, $green: null, $blue: null,
      $hue: null, $saturation: null, $lightness: null,
      $alpha: null)
    change-color(...)
    ```

    该函数将每个关键字参数的值传递给颜色的相应属性，然后返回更改后的颜色。当同时指定 RGB 属性和 HSL 属性时，它会引发错误。每个可选参数必须是一个数字。RGB 参数必须是无单位的，并且在 **-255 和 255** 之间(包括这两个值)。`hue`参数必须以`deg`为单位或者没有单位。`saturation`和`lightness`参数必须始终在 **-100%和 100%** 之间(包括这两个参数)，并且可以是无单位的。`alpha`参数必须是无单位的，并且在 **-1 和 1** 之间(包括两者)。

    **示例:**

    ```html
    @debug color.change(#6b717f, $red: 100); 
    @debug color.change(#d2e1dd, $red: 100, $blue: 50); 
    @debug color.change(#998099, $lightness: 30%, $alpha: 0.5); 
    ```

    **输出:**

    ```html
    #64717f
    #64e132
    rgba(85, 68, 85, 0.5)

    ```

*   **color.complement():** This function returns the RGB complement of the color. It is identical to `color.adjust($color, $hue: 180deg)`.

    **语法:**

    ```html
    color.complement($color)
    complement($color)
    ```

    **示例:**

    ```html
    @debug color.complement(#6b717f); 
    @debug color.complement(#d2e1dd);
    @debug color.complement(#036); 
    ```

    **输出:**

    ```html
    #7f796b
    #e1d2d6
    #663300  

    ```

*   **desaturate():** This function makes the color less saturated by the given amount.

    **语法:**

    ```html
    desaturate($color, $amount)
    ```

    金额必须始终是介于 **0%和 100%** 之间的数字(包括两者)。该函数将颜色的 HSL 饱和度降低该数量。

    **示例:**

    ```html
    @debug desaturate(#036, 20%);
    @debug desaturate(#f2ece4, 20%);
    ```

    **输出:**

    ```html
    #0a335c
    #eeebe8 

    ```