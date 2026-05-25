# Laravel Artisan 命令指南

> 原文：[https://www.geeksforgeeks.org/laravel-artisan-commands-to-know-in-laravel/](https://www.geeksforgeeks.org/laravel-artisan-commands-to-know-in-laravel/)

## Artisan 简介

[Artisan](https://www.geeksforgeeks.org/laravel-artisan-console-introduction/) 是 Laravel 提供的命令行界面，旨在简化开发流程。它类似于 Linux 命令行，但其命令专为构建 Laravel 应用程序而设计。通过这个工具，我们可以创建模型、控制器、执行数据迁移等。首先，你需要将命令行控制台（Windows 上的 `cmd` 或 Linux/Mac 上的终端）或其他 CLI 软件的当前目录更改为你的 Laravel 应用程序目录。

## 创建命令

### 创建控制器
以下命令将创建一个控制器：

```php
php artisan make:controller ArticleController
```

**输出：**
![](img/bf9c4f8a72271bd1d0bf5a7e3e9746f9.png)

下面的命令将同时创建一个控制器和一个模型：

```php
php artisan make:controller ArticleController -m Article
```

**输出：**
![](img/697d8c8c1f1821cccda69f80a2c803f7.png)

### 创建模型
以下命令将创建一个 Eloquent 模型：

```php
php artisan make:model Article
```

**输出：**
![](img/bfb29545f646deab0de25aa9eeb810aa.png)

## 前端脚手架

### 创建前端脚手架
以下命令将为 Bootstrap 创建前端脚手架：

```php
php artisan ui bootstrap
```

**输出：**
![](img/a8f8b2c6467818d770583f4cebfe9abe.png)

以下命令将为 Vue 创建前端脚手架：

```php
php artisan ui vue
```

**输出：**
![](img/3dc5fd9a09c91c56ec732f93c73f6a90.png)

以下命令将为 React 创建前端脚手架：

```php
php artisan ui react
```

**输出：**
![](img/9b12c9cb9aceaa614c433513e5e9a6c6.png)

要移除脚手架，请使用以下命令：

```php
php artisan preset none
```

**输出：**
![](img/b4d93d3701ca5aa38e2ba706f14c8ea8.png)

**注意：** 在使用上述命令之前，你需要运行 `composer require laravel/ui --dev` 来安装 `laravel/ui` 包。

### 认证配置
以下命令将创建一个完整的认证系统：

```php
php artisan ui vue --auth
```

**输出：**
![](img/3ba662c5ff9ad8e28f4345073a5ecf68.png)

## 数据库与路由

### 创建数据迁移
以下命令将创建一个迁移文件：

```php
php artisan make:migration create_articles_table
```

**输出：**
![](img/f8a8eab6d81c846b3eeb80cbc376cb4e.png)

要对所有表执行数据库迁移，请运行以下命令：

```php
php artisan migrate
```

**输出：**
![](img/ecc0271e44baecfbdcce5c400da0fa6b.png)

### 查看路由列表
以下命令将显示所有路由的列表：

```php
php artisan route:list
```

**输出：**
![](img/690d3d33398a4c36117510b04697cf64.png)

## 开发与维护

### 启动 Tinker
以下命令将启动 Tinker：

```php
php artisan tinker
```

**输出：**
![](img/383dfecca362cb212a25613154b4ad93.png)

### 启动开发服务器
以下命令将启动 Laravel 开发服务器，并提供一个 URL 以访问正在运行的 Laravel 应用程序：

```php
php artisan serve
```

**输出：**
![](img/852cd45ac893e9401c4cde48ca8a3c4e.png)

### 维护模式
以下命令可用于将 Laravel 应用程序切换至或退出维护模式：

**进入维护模式：**

```php
php artisan down
```

**输出：**
![](img/4251f799b1c57e62166e2fcffd26bcb5.png)

**退出维护模式：**

```php
php artisan up
```

**输出：**
![](img/0b30358d669f6aff26ad121bd4d7b3b8.png)

## 其他实用命令

### 列出所有命令
以下命令将显示所有可用命令的列表：

```php
php artisan list
```

**输出：**
![](img/fa7fec300f36a2bfd640311556863d47.png)

你也可以只写 `php artisan` 而不带 `list` 参数，效果相同，会列出所有 Artisan 命令。

**注意：** 要了解任何命令的更多信息，请在命令末尾使用 `-h` 或 `--help` 选项。