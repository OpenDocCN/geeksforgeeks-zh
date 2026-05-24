# MySQL数据库备份

> 原文：[https://www.geeksforgeeks.org/database-backup-from-mysql/](https://www.geeksforgeeks.org/database-backup-from-mysql/)

在日常工作中，创建的数据库非常重要。这些从MySQL创建的数据库可以在系统之间转移，并保护数据免受破坏。有时系统会因某些错误而损坏，因此需要确保创建的数据库备份是完好的。所以，可以选择从MySQL Wamp服务器创建数据库备份。

以下是从Wamp服务器创建备份的步骤：

1.  进入C盘。
2.  打开名为`Wamp`的服务器文件夹。
3.  打开名为`bin`的文件夹，然后打开`MySQL`文件夹。
4.  现在打开`mysql5.7.19`文件夹（这里，`5.7.19`是Wamp服务器的版本，不同用户的版本可能不同，但你应该进入对应版本的文件夹）。
5.  然后再次打开`bin`文件夹。
6.  然后在文件资源管理器的地址栏输入`CMD`并按回车。

然后会出现一个命令提示符窗口，其路径已定位到上述地址。接着输入：

```shell
mysqldump -u root -p harshitdb > harshitbackup.sql
```

在这里，`harshitdb`表示`harshit`是创建的数据库名称，`db`表示数据库。执行后，它会创建一个数据库备份文件，您可以共享这个文件，它不会被损坏或丢失。

打开命令提示符（CMD）并定位到以下地址：

```shell
C:\wamp\bin\mysql\mysql5.7.19\bin>mysqldump -u root -p harshitdb > harshitbackup.sql
```

然后按回车键。

![](img/6b261f52e5ddd1b7b278268f11d19798.png)