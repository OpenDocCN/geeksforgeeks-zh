# 在中实施 CI/CD。在 GitLab 上使用外壳执行器的. NET 应用程序

> 原文:[https://www . geesforgeks . org/implementation-of-ci-CD-in-net-application-use-shell-executor-on-git lab/](https://www.geeksforgeeks.org/implementation-of-ci-cd-in-net-application-using-shell-executor-on-gitlab/)

Shell Executor 是一个非常简单的执行器，它有助于在安装了 GitLab Runner 的机器上本地构建解决方案。但是，它也有助于运行 Bash 和 Windows PowerShell 脚本，并且不推荐使用 Windows Batch。将 GitLab Runner 设置为 Shell Executor 模式并在其上开始实现需要一些需求和路径配置。

**Shell Executor:**Shell Executor 是一个非常简单的执行器，有助于在安装了 GitLab Runner 的机器上本地构建解决方案。在这种情况下，GitLab Runner 安装在 Linux Machine 上，因此需要在同一个系统中安装所需的软件。

**要求:**

<figure class="table">

| 

软件

 | 

描述

 |
| --- | --- |
| 饭桶 | 这是在 GitLab 上提交变更的第一个要求。这是一个版本控制软件，可以跟踪文件的变化。 |
| 吉塔实验室信差 | GitLab Runner 的工作是获取并执行作业(当新的提交发生时)。 |
| MSBuild.exe | 下载 MSBuild.exe 并将其保存在您的本地目录中，当 GitLab Runner 获得该工作时，它有助于构建项目。如果在机器上已经安装了 Visual Studio，则不需要安装。可以在 C:\ Program Files(x86)\ Microsoft Visual Studio \ 2019 \ Enterprise \ MSBuild \ Current \ Bin \ MSBuild . exe(基于 Visual Studio 版本查找)中找到 |
| 纽吉特. exe | 下载 Nuget.exe 并保存在 MSBuild 可用的目录中。 |

</figure>

**路径配置:**

<figure class="table">

| 

软件/文件

 | 

路径描述

 |
| --- | --- |
| 饭桶 | 在机器上成功安装 Git 后。需要设置以下路径来与 GitLab 存储库通信。转到系统环境变量，用用户变量路径添加这两个变量

*   c:\程序文件\Git
*   c:\程序文件\Git\bin

 |
| MSBuild.exe | MSBuild.exe 路径将需要在 Yml 文件，而配置与 GitLab。例如，C:\程序文件(x86)\ Microsoft Visual Studio \ 2019 \企业\ MSBuild \ Current \ Bin \ MSBuild . exe 或您的 MSBuild 可用的位置。 |
| 纽吉特. exe | Nuget.exe 路径也将需要在 Yml 文件，而配置与 GitLab。例如，C:\Tools\Nuget\nuget.exe 或您的 Nuget 可用的地方。 |
| mstest . exe | 这对于运行的测试用例非常有用。Net，在 Visual Studio 2019 中，它在 C:\ Program file(x86)\ Microsoft Visual Studio \ 2019 \ Enterprise \ common 7 \ IDE \ mstest . exe 中可用 |
| 。吉塔实验室 | 这个文件应该在包含所有配置项/光盘配置(包括软件和脚本路径)的项目根目录中。在这里，您可以提到这个存储库应该如何运行。在将此文件添加到根目录之前，应该检查它是否是有效的 yml 文件。 |

</figure>

**GitLab Runner 设置:**按照以下步骤下载并配置 GitLab Runner。

**1。**为 Windows 下载 GitLab Runner

**2。**下载成功后，保存在你的目录下(例如:C:\ Tools \ gitlb-Runner)，用以下命令重命名

```cs
gitlab-runner.exe
```

**3。**在管理模式下打开命令提示符，转到 GitLab-Runner 目录，并使用检查其状态

```cs
gitlab-runner status
```

**4。**如果它已经在运行，请在向 GitLab Runner 注册存储库之前停止它

```cs
gitlab-runner.exe stop
```

**5。**一旦 GitLab Runner 成功停止，则使用以下命令进行存储库注册

```cs
gitlab-runner.exe register
```

**6。**当你在 GitLab Runner 做仓库注册时，下面的问题必须回答。

*   **输入你的 GitLab 实例 URL:** 每个组织可以不同，格式会像 http://gitlab.example.com 一样
*   **路径**:转到 GitLab 账号→选择要注册到 runner 的存储库→设置→ CI/CD →展开 Runner
*   **输入该跑者的 gitlab-ci 令牌:**注册时需要的每个项目的唯一令牌可以找到
*   **路径**:转到 GitLab 账号→选择要注册到 runner 的存储库→设置→ CI/CD →展开 Runner
*   **输入该跑步者的 gitlab-ci 描述:**输入跑步者名称(任何名称)，这将帮助您记住哪个跑步者在跑步
*   **输入此跑步者的 gitlab-ci 标签:**如果想要在 yml 文件中有特定标签可用时启动 gitlab 跑步者，这是可选的。
*   **进入执行器:**会有几个执行器的列表，输入 shell(因为 GitLab Runner 会运行我们的系统)

**7。**注册成功后，启动 GitLab Runner

```cs
gitlab-runner start
```

**8。**验证 GitLab Runner 已经注册了相应的存储库，并且 Runner 已经启动。转到 GitLab 账号→选择要注册跑步者的库→设置→ CI/CD →展开跑步者，会有一个绿色圆圈可用，显示信息为**为该项目激活的跑步者。**

**注意:**如果圆圈是灰色的，表示跑者还没有出发，再次出发。

**Windows GitLab Runner 命令**

<figure class="table">

| 命令 | 

描述

 |
| --- | --- |
| gitlab-runner.exe 登记册 | 向 GitLab Runner 注册该项目 |
| gitlab-runner.exe 开始 | 启动跑步者 |
| gitlab-runner.exe 站 | 拦住跑者 |
| gitlab-runner.exe 地位 | 了解 gitlab-runner 的状态 |
| gitlab-runner 注销-测试运行程序名称 | 注销一个项目的 runner，用你的 runner 名字替换测试 Runner，这个名字可以在 config.toml 文件(你的 gitlab.exe 所在的地方)中找到。 |
| gitlab-runner 注销–URL http://gitlab.example.com/–令牌 t0k3n | 通过网址和令牌删除跑步者 |
| git lab-跑步者取消注册-所有跑步者 | 注销所有跑步者 |
| gitlab-runner 重启 | 该命令停止，然后启动 GitLab Runner 服务 |
| gitlab-runner 卸载 | 该命令停止并卸载作为服务运行的 GitLab Runner |
| gitlab-runner exec | 要查看可用执行者的列表，请运行 |
| git lab-runner–帮助 | 通过执行以下命令来检查最近的命令列表 |
| git lab-runner run–帮助 | 可以看到环境变量的名称 |
| gitlab runner-除错 | 要在调试模式下运行命令 |
| gitlab-runner exec shell | 要查看 shell 执行器所有可用选项的列表，请运行 |

</figure>

**。**这是。gitlab-ci.yml 并根据需求进行更改

```cs
variables:
 NUGET_PATH: 'C:\Tools\Nuget\nuget.exe'
 MSBUILD_PATH: 'C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise\MSBuild\Current\Bin\MSBuild.exe'
 MSTEST_PATH: 'C:\Program Files (x86)\Microsoft Visual Studio\2019\Enterprise\Common7\IDE\mstest.exe'
 TEST_FOLDER: '.\test\bin\Release'

stages:
 - build
 - test
 - deploy

before_script:  
     - '& "$env:NUGET_PATH" restore sourcecode\project.sln'  # sourcecode\project.sln-This path includes project solution where is available and restoring
     - '& "$env:NUGET_PATH" restore test\test.sln'     # This path includes test solution where is available.  and restoring      

build_job:
 stage: build
 only:
   - developer # this branch will run on GitLab Runner and can change it.  
 script:  
    - '& "$env:MSBUILD_PATH" sourcecode\project.sln /p:DeployOnBuild=true /p:Configuration=Release  /p:Platform="Any CPU" /P:PublishProfile=FolderProfile.pubxml'  
    - '& "$env:MSBUILD_PATH" test\test.sln /p:DeployOnBuild=true /p:Configuration=Release /p:Platform="Any CPU" /P:PublishProfile=FolderProfile.pubxml'  

 artifacts:
   expire_in: 365 days  # artifcats will be stored only 365 days after this it will expire  
   paths:
     - '.\sourcecode\project.sln\bin\Release\Publish\'
     - '.\sourcecode\project.sln\bin\Publish\'
     - '$env:TEST_FOLDER'
     - '.\$env:MSTEST_PATH\*.*'

test_job:
 stage: test
 only:
   - developer # this branch will run on GitLab Runner and can change it.  
 script:
   - .\test\test.bat  # This is bat file, if the test are written in script format  

 dependencies:
   - build_job

deploy_job:
 stage: deploy
 only:
   - developer # this branch will run on GitLab Runner and can change it.  
 script:
    - 'xcopy /y /s ".\sourcecode\project.sln\bin\Release\Publish\*.*" "C:\solutionDir"'  # Path where you want to store the solution  

 dependencies:    # after successfully build, only test stage will run  
   - build_job
   - test_job
```

**代码提交:**配置成功后，进行提交，查看 GitLab 上的作业状态。转到项目存储库→选择配置项/光盘菜单