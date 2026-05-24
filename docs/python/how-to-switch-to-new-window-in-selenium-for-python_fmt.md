# Python 如何在 Selenium 中切换到新窗口？

> 原文: [https://www.geeksforgeeks.org/how-to-switch-to-new-window-in-selenium-for-python/](https://www.geeksforgeeks.org/how-to-switch-to-new-window-in-selenium-for-python/)

Selenium 是用于网络测试和自动化的最常用的 Python 工具。但是当用户需要在 chrome 中的窗口之间切换时，问题就出现了。因此，硒也得到了保护。Selenium 将这些方法用于此任务-

*   `Window_handles` 用于处理不同的窗口。它存储用于切换的窗口 ID。
*   `Switch_to.window` 方法是通过 `window_handles` ID 在窗口之间切换。

## 步骤覆盖

*   设置 URL 并导入 selenium

### Python 3

```py
# import modules
from selenium import webdriver
import time

# provide the path for chromedriver
PATH = "C:/chromedriver.exe"

# pass on the path to driver for working
driver = webdriver.Chrome(PATH)
```