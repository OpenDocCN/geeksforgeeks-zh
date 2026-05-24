# 异常–硒蟒

> 原文:[https://www.geeksforgeeks.org/exceptions-selenium-python/](https://www.geeksforgeeks.org/exceptions-selenium-python/)

Selenium Python 中的异常是当其中一个方法失败或发生意外事件时发生的错误。Python 中的所有实例都必须是从 `BaseException` 派生的类的实例。通过子类化不相关的两个异常类从来都不是等价的，即使它们有相同的名字。内置异常可以由解释器或内置函数生成。本文围绕运行 Selenium 程序期间可能发生的多个异常展开。

## 示例–

让我们通过尝试找到一个不存在的元素并在 geeksforgeeks.org 点击它来演示异常。

```py
# import webdriver
from selenium import webdriver

# create webdriver object
driver = webdriver.Firefox()

# get geeksforgeeks.org
driver.get("https://www.geeksforgeeks.org/")

# get element 
element = driver.find_element_by_link_text("abrakadabra")

# click the item
print(element.click())
```

现在，让我们运行这个程序，它首先打开 geeksforgeeks.org，然后引发异常–`selenium.common.exceptions.NoSuchElementException`，这意味着该元素在网站上不存在。

## 硒蟒中的异常

当您正在编写开发就绪代码时，异常是最主要的用途，尤其是在导致特定类型异常的高风险中。这里列出了 Selenium Python 中的所有异常。

| 例外 | 描述 |
| --- | --- |
| `ElementClickInterceptedException` | 无法完成元素单击命令，因为接收事件的元素遮挡了被请求单击的元素。 |
| `ElementNotInteractableException` | 当一个元素出现在 DOM 中，但是与该元素的交互会影响另一个元素的绘制顺序时抛出 |
| `ElementNotSelectableException` | 试图选择不可选择的元素时引发。 |
| `ElementNotVisibleException` | 当一个元素出现在 DOM 上，但它不可见，因此无法与之交互时抛出。 |
| `ErrorRespondedException` | 当服务器端发生错误时引发。 |
| `ImeActivationFailedException` | 激活 IME 引擎失败时抛出。 |
| `ImeNotAvailableException` | 当 IME 支持不可用时抛出。 |
| `InsecureCertificateException` | 导航导致用户代理遇到证书警告，这通常是由于 TLS 证书过期或无效造成的。 |
| `InvalidArgumentException` | 传递给命令的参数无效或格式不正确。 |
| `InvalidCookieDomainException` | 尝试在不同于当前 URL 的域下添加 cookie 时引发。 |
| `InvalidCoordinatesException` | 为交互操作提供的坐标无效。 |
| `InvalidElementStateException` | 当命令无法完成时引发，因为元素处于无效状态。 |
| `InvalidSelectorException` | 当用于查找元素的选择器没有返回 `WebElement` 时抛出。 |
| `InvalidSessionIdException` | 如果给定的会话 id 不在活动会话列表中，这意味着该会话不存在或不活动，则会发生此事件。 |
| `InvalidSwitchToTargetException` | 当要切换的框架或窗口目标不存在时引发。 |
| `MoveTargetOutOfBoundsException` | 当提供给 `ActionsChains` `move()` 方法的目标无效时抛出，即文档外。 |
| `NoAlertPresentException` | 切换到不显示警报时引发。 |
| `NoSuchAttributeException` | 找不到元素的属性时引发。 |
| `NoSuchCookieException` | 在当前浏览上下文的活动文档的相关 cookie 中找不到与给定路径名匹配的 cookie。 |
| `NoSuchFrameException` | 当要切换的帧目标不存在时抛出。 |
| `NoSuchWindowException` | 当要切换的窗口目标不存在时引发。 |
| `StaleElementReferenceException` | 当对元素的引用现在“过时”时引发。 |
| `TimeoutException` | 当命令没有在足够的时间内完成时抛出。 |
| `UnableToSetCookieException` | 当驱动程序未能设置 cookie 时引发。 |
| `UnexpectedAlertPresentException` | 出现意外警报时引发。 |
| `UnexpectedTagNameException` | 当一个支持类没有得到预期的网络元素时抛出。 |