# 在 GitLab 上使用 Shell 和 Docker 执行器在 C/C++ 应用程序(Linux)中实现 CI/CD

> 原文:[https://www . geesforgeks . org/implementation-of-ci-CD-in-c-c-application Linux-using-shell-and-docker-executor-on-git lab/](https://www.geeksforgeeks.org/implementation-of-ci-cd-in-c-c-applicationlinux-using-shell-and-docker-executor-on-gitlab/)

有很多执行器可以用 GitLab Runner 实现 CI/CD。然而，Shell 和 Docker 在其中更受欢迎，我们可以很容易地用这些 runners 配置一个存储库。可以根据资源的需求和可用性来选择这些跑步者。本文主要研究 C/C++ Linux 应用程序的 Shell 和 Docker 执行器，代码采用 bash 脚本编写。应用程序可以使用 bash 脚本进行构建和测试。

**Shell Executor:**Shell Executor 是一个非常简单的执行器，有助于在安装了 GitLab Runner 的机器上本地构建解决方案。在这种情况下，GitLab Runner 安装在 Linux Machine 上，因此需要在同一个系统中安装所需的软件。

**Docker Executor:** 它是一个功能强大的工具，包含很多软件，可以通过图像访问。这个执行器的优点是，我们不需要手动安装任何软件，一切都将通过 docker 来处理，所需的映像将从 docker hub 下载。然而，不利的是，由于安全目的，这种通信在一些组织中被阻止。所以，如果是这种情况，Shell Executor 是最好的选择。

### **C/c++ 在 Shell 执行器上的实现**

**要求**:这些是需要安装在 Linux 机器上的基础软件。但是，它可以根据编译脚本进行更改，如果需要，需要下载其他软件。

<figure class="table">

| 

软件

 | 

描述

 |
| --- | --- |
| 饭桶 | 这是第一个要求，在 GitLab 上提交变更。这是一个版本控制软件，跟踪文件的变化 |
| cmake | 要构建自动化、测试和打包 c/c++ 应用程序，需要在 Linux 机器上安装 cmake。 |
| （同 groundcontrolcenter）地面控制中心 | 它是一个需要编译 c/c++ 程序的编译器 |
| g++ | 它也是一个需要编译 c/c++ 程序的编译器。可以根据书写的脚本进行选择。 |
| 可做文件内的字符串查找 | 如果程序搜索纯文本，请安装它。 |

</figure>

**路径配置:**以上安装成功后，如果没有设置，需要在机器中设置该安装软件的路径。在机器上运行以下命令。

<figure class="table">+T29T31gitlab-ci.yml

| 

变量/文件

 | 

路径

 |
| --- | --- |
| G++ | 导出 GCC =/usr/bin/G+ |
| 抄送 | 导出 CC =/usr/bin/GCC |
| 可做文件内的字符串查找 | This file should be in the root directory of the project containing all CI/CD configurations (including software and script paths). Here, you can mention how this repository should work. Before adding this file to the root directory, you should check whether it is a valid yml file. |

</figure>

**GitLab Runner 设置**:按照以下步骤下载并配置 GitLab Runner。

**1。使用以下命令在 Linux 机器上下载 gitrab Runner**

```cpp
sudo curl -L --output /usr/local/bin/gitlab-runner https://gitlab-runner-downloads.s3.amazonaws.com/latest/binaries/gitlab-runner-linux-amd64
```

**2。使用以下命令授予它执行**的权限

```cpp
sudo chmod +x /usr/local/bin/gitlab-runner
```

**3。使用以下命令创建一个 GitLab CI**

```cpp
sudo useradd --comment 'GitLab Runner' --create-home gitlab-runner --shell /bin/bash
```

**4。使用以下命令安装并作为服务运行**

```cpp
sudo gitlab-runner install --user=gitlab-runner --working-directory=/home/gitlab-runner
```

**5。使用以下命令启动 gitrab Runner**

```cpp
sudo gitlab-runner start
```

**6。注册存储库前停止 gitlb Runner**

```cpp
sudo gitlab-runner stop
```

**7。一旦 GitLab Runner 成功停止**在终端输入以下命令进行存储库注册。

```cpp
sudo gitlab-runner register
```

**8。**当你在 GitLab Runner 做仓库注册时，下面的问题必须回答。

*   **输入你的 GitLab 实例 URL** :每个组织可以不同，格式会像 http://gitlab.example.com 一样
*   **路径**:转到 GitLab 账号→选择要注册到 runner 的存储库→设置→ CI/CD →展开 Runner
*   **输入此 runner 的 gitlab-ci 令牌**:这将是注册时需要的每个项目的唯一令牌，可以在**找到**路径:转到 gitlab 帐户→选择要向 runner 注册的存储库→设置→ CI/CD →展开 Runner
*   **输入该跑步者的 gitlab-ci 描述**:输入跑步者名称(任何名称)，这将帮助您记住哪个跑步者在跑步
*   **输入此跑步者的 gitlab-ci 标签**:当 yml 文件中有特定标签可用时，如果您想启动 gitlab 跑步者，这是可选的。
*   **进入执行器:**会有几个执行器的列表，输入 shell(因为 GitLab Runner 会运行我们的系统)

**9。**注册成功后，使用以下命令启动 GitLab Runner。

```cpp
sudo gitlab-runner start
```

**10。**验证 GitLab Runner 已经注册了相应的存储库，并且 Runner 已经启动。转到 GitLab 帐户→选择要向跑步者注册的存储库→设置→配置项/光盘→展开跑步者，将有绿色圆圈可用，并显示消息“跑步者将为此项目激活”。注意:如果圆圈是灰色的，表示跑步者还没有开始，再次开始。

### Linux GitLab Runner 命令

遵循更多的 GitLab Runner 命令来熟悉自己。

<figure class="table">T21T28】sudo git lab-Runner 停止

| 

命令

 | 

描述

 |
| --- | --- |
| sudo git 实验室-run nery | Register the project with GitLab Runner |
| sudo git 实验室-run Neri | 启动跑步者 |
| Stop the Runner of the project and replace the test runner with your runner name, which can be found in the config.toml file (where your gitlab-runner is located). |
| sudo git 实验室跑步者注销–网址 http://gitlab.example.com/–令牌 t0k3n | Remove Runner by URL and token |
| sudo git 实验室-Runner 注销–所有跑步者 | To log off all Runner |
| sudo git 实验室-run nerj | This command stops and then starts the GitLab Runner service. |
| sudo git 实验室-run neru | Actuator, running |
| sudo git lab-runner-昂基 | By execution |
| sudo git 实验室 | You can see the name of the environment variable |
| sudo git lab runner-什么 | Run commands in debug mode. |

</figure>

**。gitlab-ci.yml_ shell 执行者:**

以下是的内容。外壳执行器模式下的 gitlab-ci.yml。但是，如果需要，可以更改它。

```cpp
stages:
 - build
 - test

build_job:
 stage: build
 only:
   - master
 script:  
    - cd sourcecode
    - export G++ =/usr/bin/g++  //if not set manually path of g++
    - export GCC=/usr/bin/gcc //if not set manually path of gcc
    - chmod -R 777 *
    - ./BuildPackage.sh
    - pwd  

 artifacts:
   expire_in: 365 days   //save the binary which needed while test the application, and it can be downloaded from GitLab
   paths:
      - sourcecode/binaryfolder_name  // save the binary  

test_job:
 stage: test
 only:
   - master
 script:
    - pwd  
    - cd testdir       //go to test directory for run the test case script  
    - chmod -R 777 *
    - ./tests.sh

 dependencies:
   - build_job
   - build_job
```

**C/c++ 在 Docker Executor 上的实现:**不需要手动安装任何软件，一切都会从 Docker 容器中取出。但是，您可以安装所需的软件，在 yml 文件中输入名称，也可以导出路径。要在 docker 执行器模式下运行 gitlab runner，请转到 GitLab Runner 设置(上图)，并选择 docker 而不是 shell。

**。gitlab-ci.yml_ Docker 执行者**:

以下是的内容。docker 执行器模式下的 gitlab-ci.yml。但是，如果需要，可以更改它。

```cpp
image: ubuntu:latest

stages:
 - build
 - test

before_script:
 - echo "Before script install this on ubuntu image "
 - apt-get update && apt-get -y install cmake && apt-get -y install gcc &&  apt-get -y install g++

build_job:
 stage: build
 only:
   - master
 script:  
    - cd sourcecode
    - export G++ =/usr/bin/g++  //if not set manually path of g++
    - export GCC=/usr/bin/gcc //if not set manually path of gcc
    - chmod -R 777 *
    - ./BuildPackage.sh
    - pwd  

 artifacts:
   expire_in: 365 days   //save the binary which needed while test the application, and it can be downloaded from GitLab
   paths:
      - sourcecode/binaryfolder_name  // save the binary  

test_job:
 stage: test
 only:
   - master
 script:
    - pwd  
    - cd testdir       //go to test directory for run the test case script  
    - chmod -R 777 *
    - ./tests.sh

 dependencies:
   - build_job
```