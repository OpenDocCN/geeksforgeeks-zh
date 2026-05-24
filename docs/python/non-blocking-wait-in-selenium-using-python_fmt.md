# 使用 Python 在 Selenium 中进行非阻塞等待

> 原文: [https://www.geeksforgeeks.org/non-blocking-wait-in-selenium-using-python/](https://www.geeksforgeeks.org/non-blocking-wait-in-selenium-using-python/)

**先决条件:** [使用 Selenium 的浏览器自动化](https://www.geeksforgeeks.org/browser-automation-using-selenium/)

当我们想要进行 web 自动化时，我们需要等待一些 javascript 元素加载后才能执行一些操作。就此而言，人们通常使用 `time.sleep(in_seconds)`。

这是一个阻塞呼叫。我所说的阻塞调用是指，无论发生什么，它都会等待或者更确切地说是让程序休眠所提到的几秒钟。这不是一个好主意，因为它会让程序变得更慢，从而增加延迟。

对此的可能解决方案是等到一个元素出现，并且不要等待超过那个时间。

**先决条件:** Python 已安装，Selenium 与 web 驱动程序一起作为包安装（`.exe` 文件）。对于带有 Selenium 的 Python Web 自动化，这可以通过以下方式实现:

假设您希望通过 web 自动化在 GeeksForGeeks 上登录，并在用户名和密码元素在网页上可见时立即填写登录凭据，而不是等到整个页面加载完毕。

**步骤 1:**
您可以按如下方式配置网络驱动程序:

```py
from selenium import webdriver

options = webdriver.ChromeOptions()
options.add_argument("--start-maximized")
options.add_argument("disable-infobars")

chrome = webdriver.Chrome(the_path_of_webdriver_which_is_an_exe,
                          chrome_options = options, service_args =['--ignore-ssl-errors = true'])

login_uri = 'https://auth.geeksforgeeks.org/'
username = 'something'
password = 'anything'
username_xpath = '//*[@id ="luser"]'
password_xpath = '//*[@id ="password"]'
sign_in_xpath = '//*[@id ="Login"]/button'

chrome.get(login_uri)
```

在这里，我使用了 `chrome` 网络驱动程序，它将开始最大化（全窗口），没有信息栏，也就是说，它不会说 `chrome` 是由自动化代码控制的，加载 GFG 的标志页没有任何麻烦。

**请注意，为了找到这些元素的 `xpath`，您需要进入开发人员模式并检查这些元素。**

**步骤 2:**

```py
# return True if element is visible within 30 seconds, otherwise False
def is_visible(locator, timeout = 30):
    try:
        ui.WebDriverWait(chrome, timeout).until(EC.visibility_of_element_located((By.XPATH, locator)))
        return True
    except TimeoutException:
        return False
```

上述函数 `is_visible` 是我们打算在此讨论的非阻塞调用的促进者。
解释:
1) `locator` – 元素的 `xpath`
2) `timeout` – 直到何时等待元素出现（因为我们不想永远等待）
3) `chrome` – 我们之前初始化的 `webdriver` 对象
4) 它利用 `ui` 的 `inbuild` 实用程序使 web 驱动程序等待直到元素可见（由 `XPath` 标识）
5) 如果它确实在超时内出现，它返回 `True` 否则返回 `False`

**步骤 3:**
这是我们如何利用函数:

```py
if not is_visible(username_xpath): raise RuntimeError("Something went wrong with the username field :(")
username_field = chrome.find_element_by_xpath(username_xpath)
username_field.send_keys(username)

if not is_visible(password_xpath): raise RuntimeError("Something went wrong with the password field :(")
password_field = chrome.find_element_by_xpath(password_xpath)
password_field.send_keys(password)

if not is_visible(sign_in_xpath): raise RuntimeError("Something went wrong with the sign in field :(")
sign_in_btn = chrome.find_element_by_xpath(sign_in_xpath)
sign_in_btn.click()
```

这里我们调用 `is_visible` 函数，分别传递 `username`、`password` 和 `sign_in` 按钮的 `xpath`，等待元素在超时（这里是 30s）内出现。如果不可见，那么我们会用适当的消息引发 `RuntimeError`。
如果它在 30s 之前的任何时间出现，它继续并通过 `xpath` 找到元素（因为现在它在网页上可见，所以这个调用不会抛出异常错误）。

然后，我们发送数据并点击登录，您可以享受在 GFG 学习的乐趣，而无需任何阻止呼叫😛