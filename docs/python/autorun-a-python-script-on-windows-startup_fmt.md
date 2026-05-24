# 在 Windows 启动时自动运行 Python 脚本

> 原文：[https://www.geeksforgeeks.org/autorun-a-python-script-on-windows-startup/](https://www.geeksforgeeks.org/autorun-a-python-script-on-windows-startup/)

向 Windows 启动中添加 Python 脚本基本上意味着 Python 脚本将在 Windows 启动时运行。这可以通过两步过程来完成——

## 步骤 1：将脚本添加到 Windows 启动文件夹

在 Windows 启动后，它会运行（相当于双击）其启动目录中的所有应用程序。

**地址：**

> `C:\Users\<current_user>\AppData\Roaming\Microsoft\Windows\Start Menu\Programs\Startup\`

默认情况下 `<current_user>` 下的 `AppData` 文件夹是隐藏的，所以启用隐藏文件来获取它，并将脚本的快捷方式粘贴到给定的地址或脚本本身。此外，`.py` 文件的默认打开方式必须设置为 Python IDE，否则脚本可能会以文本形式打开而不是执行。

## 步骤 2：向 Windows 注册表添加脚本

这个过程如果做得不好可能会有风险，它涉及到从 Python 脚本本身编辑 Windows 注册表项 `HKEY_CURRENT_USER`。该注册表包含用户登录后必须运行的程序列表。就像很少有应用程序会在 Windows 启动时弹出一样，因为它会导致注册表发生变化，并将应用程序路径添加到注册表中。

**注册表路径：**

> `HKEY_CURRENT_USER\Software\Microsoft\Windows\CurrentVersion\Run`

下面是 Python 代码：

### Python 3

```py
# Python code to add current script to the registry

# module to edit the windows registry
import winreg as reg
import os

def AddToRegistry():

    # in python __file__ is the instant of
    # file path where it was executed
    # so if it was executed from desktop,
    # then __file__ will be
    # c:\users\current_user\desktop
    pth = os.path.dirname(os.path.realpath(__file__))

    # name of the python file with extension
    s_name="myScript.py"

    # joins the file name to end of path address
    address=os.path.join(pth,s_name)

    # key we want to change is HKEY_CURRENT_USER
    # key value is Software\Microsoft\Windows\CurrentVersion\Run
    key = reg.HKEY_CURRENT_USER
    key_value = "Software\\Microsoft\\Windows\\CurrentVersion\\Run"

    # open the key to make changes to
    open_key = reg.OpenKey(key, key_value, 0, reg.KEY_ALL_ACCESS)

    # modify the opened key
    reg.SetValueEx(open_key, "any_name", 0, reg.REG_SZ, address)

    # now close the opened key
    reg.CloseKey(open_key)

# Driver Code
if __name__=="__main__":
    AddToRegistry()
```

**注意：** 对于每次启动时要执行的任务，可以在该脚本中添加更多代码，并且该脚本必须**首次以管理员身份运行**。