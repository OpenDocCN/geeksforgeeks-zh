# Python - Tweepy 中的 API.lookup_users() 方法

> 原文: [https://www.geeksforgeeks.org/python-api-lookup_users-in-tweepy/](https://www.geeksforgeeks.org/python-api-lookup_users-in-tweepy/)

`Twitter` 是一个流行的社交网络，用户在这里分享被称为推文的消息。`Twitter` 允许我们使用 `Twitter API` 或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 `Twitter Developer` 获取 `consumer key`、`consumer secret`、`access key` 和 `access secret`，每个用户都可以轻松获得。这些密钥将帮助 `API` 进行身份验证。

## API.lookup_users()

`Tweepy` 模块中 `API` 类的 `lookup_users()` 方法用于获取每个请求最多 100 个用户的用户对象列表。

> **语法:** `API.lookup_users(参数)`
>
> **参数:**
>
> *   `user_ids`: 用户标识列表
> *   `screen_names`: 屏幕名称列表
>
> **返回:** `User` 类的对象列表

### 示例 1

使用带有 `user_ids` 参数的 `lookup_users()` 方法。

```py
# import the module
import tweepy

# assign the values accordingly
consumer_key = ""
consumer_secret = ""
access_token = ""
access_token_secret = ""

# authorization of consumer key and consumer secret
auth = tweepy.OAuthHandler(consumer_key, consumer_secret)

# set access to user's access key and access secret
auth.set_access_token(access_token, access_token_secret)

# calling the api
api = tweepy.API(auth)

# list of user_ids
user_ids = [57741058, 4802800777, 1037141442]

# getting the users by user_ids
users = api.lookup_users(user_ids)

# printing the user details
for user in users:
    print("The id is : " + str(user.id))
    print("The screen name is : " + user.screen_name, end = "\n\n")
```

**输出:**

```py
The id is : 57741058
The screen name is : geeksforgeeks

The id is : 4802800777
The screen name is : PracticeGfG

The id is : 1037141442
The screen name is : GeeksQuiz
```

### 示例 2

使用带 `screen_names` 参数的 `lookup_users()` 方法。

```py
# list of screen_names
screen_names = ["geeksforgeeks", "PracticeGfG", "GeeksQuiz"]

# getting the users by screen_names
users = api.lookup_users(screen_names = screen_names)

# printing the user details
for user in users:
    print("The id is : " + str(user.id))
    print("The screen name is : " + user.screen_name, end = "\n\n")
```

**输出:**

```py
The id is : 57741058
The screen name is : geeksforgeeks

The id is : 4802800777
The screen name is : PracticeGfG

The id is : 1037141442
The screen name is : GeeksQuiz
```