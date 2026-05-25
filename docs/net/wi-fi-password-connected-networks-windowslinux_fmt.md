# Windows/Linux 中查看所有已连接 Wi-Fi 的密码

> 原文：[https://www.geeksforgeeks.org/wi-fi-password-connected-networks-windowslinux/](https://www.geeksforgeeks.org/wi-fi-password-connected-networks-windowslinux/)

## Windows

命令提示符，也称为 `cmd.exe` 或 `cmd`（以其可执行文件名命名），对于喜欢命令界面而不是图形用户界面的人来说是一个很好的工具。图形用户界面中还有很多功能没有实现，可以通过 CMD 访问。在这篇文章中，我将分享如何使用 CMD 查找所有连接设备的密码。

在继续之前，您应该知道一件事，每当您连接到无线网络并输入密码时，Windows 都会创建该无线网络的无线局域网配置文件。这些无线局域网配置文件与其他所需的无线网络配置文件的详细信息一起存储在计算机中。

我们可以稍后通过简单地使用 Windows CMD 来发现这些无线局域网配置文件。您可以使用简单的命令找出所有连接的网络及其密码。这些命令还可以发现当前未连接但以前连接过的网络的无线密码。因此，即使当您离线或连接到任何其他网络时，它也能工作。

**注意：以下命令只能由管理员执行**

1.  打开命令提示符，以管理员身份运行。
2.  键入 `netsh wlan show profiles` – 它将显示以前连接到计算机的所有无线网络配置文件。
    ![](img/974f6fb8912648ab209726ebc0efa061.png)
3.  键入此命令（不带引号）：`netsh wlan show profile SaDiNeNi key=clear`
    ![](img/f5a0149e1316077eea11f5a227c40e8a.png)

**应采取的预防措施：**

1.  键入 `netsh wlan show profiles`（它将显示连接的不同无线网络）。
2.  键入 `netsh wlan delete profile name="profile name"`（删除所需的配置文件）。

## Linux

要通过命令行找到保存的 Wi-Fi 密码，请按照以下步骤操作：登录 Ubuntu，打开“终端”，输入以下命令。

1.  键入 `cd /etc/NetworkManager/system-connections/` – 它包含 Wi-Fi 的配置文件。
2.  键入 `ls -a`。
    现在，您将获得保存在电脑上的 Wi-Fi 网络名称。现在输入以下命令，并输入您想要查找密码的 Wi-Fi 网络名称。您可以在 `"PSK"="PASSWORD"` 中找到您的密码。
3.  `sudo cat WIFI_SSID_Name`
    ![](img/c4de5e4b00b22efce6237cde8ec65406.png)

**应采取的预防措施：**

1.  `sudo ls -l /etc/NetworkManager/system-connections/` 以列出所有文件。
2.  在找到要删除的网络后，使用以下命令删除它们：`sudo rm /etc/NetworkManager/system-connections/NETWORK_NAME`。

本文由**阿卡什·莎兰**供稿。如果你喜欢 GeeksforGeeks 并想投稿，你也可以使用 [contribute.geeksforgeeks.org](http://www.contribute.geeksforgeeks.org) 写一篇文章或者把你的文章邮寄到 `contribute@geeksforgeeks.org`。看到你的文章出现在极客博客主页上，帮助其他极客。

如果你发现任何不正确的地方，或者你想分享更多关于上面讨论的话题的信息，请写评论。