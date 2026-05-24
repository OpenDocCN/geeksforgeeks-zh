# Docker Compose 工具运行多容器应用程序

> 原文：[https://www.geeksforgeeks.org/docker-compose-tool-to-run-multi-container-applications/](https://www.geeksforgeeks.org/docker-compose-tool-to-run-multi-container-applications/)

本文的目标是展示如何使用单个命令运行多容器应用程序。Compose 是一个定义和运行多容器 Docker 应用程序的工具。通过 Compose，您可以使用配置文件（YAML 文件）来配置您的 Docker 容器。然后，使用一个命令，从您的配置中创建并启动所有服务（容器）。我举个例子解释一下。

本文期待您熟悉 [Docker](https://www.geeksforgeeks.org/containerization-using-docker/)，并对 [Flask](https://www.geeksforgeeks.org/dockerize-your-flask-app/) 有一定的使用经验。

假设我们有一个简单的应用程序，它有两个组件，Flask app 和 Redis 数据库。我将通过运行完整的应用程序，使用和不使用 `docker-compose` 工具，这将使您了解主要使用这个 Compose 工具。

## 创建项目

创建目录保存我们的项目：

```bash
$ mkdir gfg_docker_compose
```

移到那个目录：

```bash
$ cd gfg_docker_compose
```

创建需求文件：

```bash
gfg_docker_compose/ $ touch requirements.txt
```

复制以下内容到 `requirements.txt`：

```text
flask
redis
```

创建文件 `app.py`，它将包含我们的 Flask 应用程序的代码：

```bash
gfg_docker_compose/ $ touch app.py
```

将以下代码复制到 `app.py`：

```python
from flask import Flask, request, jsonify
from redis import Redis

# initializing a new flask app
app = Flask(__name__)

# initializing a new redis database
# Hostname will be same as the redis service name
# in the docker compose configuration
redis = Redis(host="localhost", db=0, socket_timeout=5,
              charset="utf-8", decode_responses=True)

# Our app has a single route allowing two methods POST and GET.

@app.route('/', methods=['POST', 'GET'])
def animals():

    if request.method == 'POST':
        # Take the name of the animal
        name = request.json['name']
        # push the name to the end of animals list in the redis db
        redis.rpush('animals', {'name': name})
        # return a success
        return jsonify({'status': 'success'})

    if request.method == 'GET':
        # return complete list of names from animals
        return jsonify(redis.lrange('animals', 0, -1))
```

### 解释：

我们只是简单地接受了 `/` 路由的 `GET` 和 `POST` 请求。当用这个名字完成一个 `POST` 请求时，这个名字会被添加到 `animals` 列表的末尾。对于 `GET` 请求，我们将从 `animals` 列表中返回名称列表。

创建 `Dockerfile` 文件：

```bash
gfg_docker_compose/ $ touch Dockerfile
```

将以下代码复制到 `Dockerfile`：

```dockerfile
# pulling the base image
FROM python:3.7.0-alpine3.8

# Creating a folder and moving into it
WORKDIR /usr/src/app

# Copying the dependency list
COPY requirements.txt ./

# Installing the python dependencies
RUN pip install --no-cache-dir -r requirements.txt

# Copying the flask code into the container
COPY . .

ENV FLASK_APP=app.py

EXPOSE 5000

# Starting the server
CMD flask run --host=0.0.0.0
```

### 解释：

我们将从基础镜像 `python:3.7.0-alpine3.8` 开始。我们将复制 `requirements.txt` 文件并安装我们所有的 Flask 应用程序依赖项。然后我们将 `app.py` 文件复制到容器中，最后运行 Flask 应用程序。

现在我们准备好了 Docker 应用程序。

## 没有 docker-compose 工具

在没有 Compose 工具的情况下启动和使用这个应用程序对于多容器应用程序来说是很繁琐的，因为您需要记住完整的配置，并在运行应用程序时手动使用。让我们看看在没有 Compose 工具的情况下它是如何工作的。

现在您将有一个项目树，如下所示：

```text
gfg_docker_compose
--- app.py
--- requirements.txt
--- Dockerfile
```

现在将运行并启动我们的 Redis 服务器容器：

```bash
gfg_docker_compose/ $ docker run --name=redis redis:4.0.11-alpine
```

![](img/1f10bb41d9b84f3c12170e5316a0ad43.png)

Redis 服务器已启动。

因此，使用该命令，我们将拉取 `redis:4.0.11-alpine` 镜像并运行一个 Redis 容器。现在我们的 Redis 已经开始了，所以你应该获取它的容器 IP 地址：

```bash
gfg_docker_compose/ $ docker inspect --format='{{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' redis
```

![](img/6703eb65a347beed2b3e9bddff5cce5b.png)

提取 Redis 容器 IP 地址。

这给了你一个 IP 地址，你需要把它放到 `app.py` 的 `host` 参数中。

现在 `app.py` 中的这一行看起来像是：

```python
redis = Redis(host="IPAddress", db=0, socket_timeout=5,
              charset="utf-8", decode_responses=True)
```

其中 `IPAddress` 是您从 Redis 容器中获得的 IP 地址。

构建 Flask 应用程序：

```bash
gfg_docker_compose/ $ docker build -t gfg/flask-app .
```

![](img/b5c5f3d9ba56f22d8fda24a075e87ec5.png)

我们的 `gfg/flask-app` 镜像已成功构建。

等待一段时间，应用程序镜像将被构建。

现在我们也将启动我们的 Flask 应用程序容器。

打开一个新的终端选项卡，并运行以下命令：

```bash
gfg_docker_compose/ $ docker run -p 5000:5000 gfg/flask-app
```

![](img/5aa2527799058f056abed4f29cc98440.png)

我们的 Flask 应用程序已经启动。

因此，使用该命令，我们将拉取我们之前构建的 `gfg/flask-app` 镜像，并运行我们的 Flask app 容器。此外，`-p` 用于将端口 `5000` 从容器映射到主机。

最后，当你在浏览器上转到 Flask 应用程序时，你应该会看到类似这样的内容。

![](img/eca45ec57606212a6c680b419ed5998a.png)

我们的应用程序正在运行。

## 使用 docker-compose 工具

使用 `docker-compose` 工具，多容器 Docker 应用程序的设置过程将变得相当容易。简单地说，我们将在一个名为 `docker-compose.yml` 的 YAML 文件中编写完整的容器配置，然后使用简单的命令启动和停止应用程序。通过简单地共享 `docker-compose` 文件和项目，这种方法还将帮助我们轻松地将 Docker 应用程序共享给其他开发人员。

创建 `docker-compose.yml` 文件：

```bash
gfg_docker_compose/ $ touch docker-compose.yml
```

现在项目树看起来像：

```text
gfg_docker_compose
--- app.py
--- requirements.txt
--- Dockerfile
--- docker-compose.yml
```

现在将下面的 YAML 代码复制到文件中。

```yaml
version: '3'

services:
  app:
    build: .
    image: gfg/flask-app
    environment:
      - FLASK_ENV=development
    ports:
      - 5000:5000

  redis:
    image: redis:4.0.11-alpine
```

### 解释：

- `version`：说明要使用的 `docker-compose` 版本，这里我们使用的是版本 3。
- `services`：保存我们所有的应用服务（容器）配置。
- `app`：我们已经将我们的 Flask app 命名为 `app` 服务，您可以随意给它起任何其他的名字。
- `build`：Dockerfile 的相对路径。
- `image`：最终 Docker 应用镜像的名称。
- `environment`：环境变量列表。
- `ports`：要从容器映射到主机的端口列表。
- `redis`：我们 Redis 服务的名称。
- `image`：镜像的名称。

**注意：** 服务名称 `app` 和 `redis` 也是我们运行的服务（容器）的主机名，因为 `docker-compose` 会自动创建一个网络并将我们的容器添加到该网络中，这样每个容器都可以通过它们的服务名称将其他容器识别为该网络中的主机名。所以这就是我们将 `app.py` 文件中的 `host` 参数保留为 `redis` 本身的原因。

启动应用程序：

```bash
gfg_docker_compose/ $ docker-compose up --build
```

![](img/6f610988e878a4b448972a75c2d3c096.png)

一个成功的 `docker-compose` 输出如下所示。

`--build` 用于明确提及在启动应用程序之前构建镜像。

您可以看到应用程序的工作原理如下：

![](img/eca45ec57606212a6c680b419ed5998a.png)

我们的 Docker 应用程序正在工作。

停止整个应用程序：

```bash
gfg_docker_compose/ $ docker-compose down
```

![](img/084461f9f0f403db2679c974ada9cb61.png)

一个成功的 `docker-compose down` 是这样的。

使用 `docker-compose` 工具，我们可以使多容器 Docker 应用程序的设置过程比通常的方式更快更容易。