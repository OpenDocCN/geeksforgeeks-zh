# Python - API.create_friendship() in Tweepy

> 原文: [https://www.geeksforgeeks.org/python-api-create_friendship-in-tweepy/](https://www.geeksforgeeks.org/python-api-create_friendship-in-tweepy/)

`Twitter`是一个流行的社交网络，用户在这里分享被称为推文的消息。`Twitter`允许我们使用`Twitter API`或`Tweepy`挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从`Twitter Developer`获取`consumer key`、`consumer secret`、`access key`和`access secret`，每个用户都可以轻松获得。这些密钥将帮助`API`进行身份验证。

## API.create_friendship()

`Tweepy`模块中`API`类的`create_friendship()`方法用于在经过身份验证的用户和目标用户之间创建友谊(跟随)。

> **语法:** `API.create_friendship(id/user_id/screen_name)`
>
> **参数:** 仅使用3个选项之一:
>
> *   `id`: 指定用户的`id`或屏幕名称。
> *   `user_id`: 指定用户的`id`，当有效的用户`ID`也是有效的屏幕名称时，用于区分帐户。
> *   `screen_name`: 指定用户的屏幕名称，当有效的屏幕名称也是用户`id`时，用于区分帐户。
>
> **返回:** `User`类的一个对象

**示例1:** 使用屏幕名称创建友谊。考虑以下账户:
![](img/a67cc9fb38edfd1453359824a88d14fd.png)

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

# screen name of the account to be followed
screen_name = "geeksforgeeks"

# creating the friendship
api.create_friendship(screen_name)
```

**输出:**
![](img/e7cf1ad934584233b1453c35e4386fcb.png)

**示例2:** 使用用户`id`创建友谊。考虑以下账户:
![](img/8c3e11832dd86970de6b8f8b388da378.png)

```py
# user id of the account to be followed
user_id = 103770785

# creating the friendship
api.create_friendship(user_id)
```

**输出:**

```py
The user id 57741058 corresponds to the user with the name : GeeksforGeeks

The screen name geeksforgeeks corresponds to the user with the name : GeeksforGeeks
```

**输出:**
![](img/8743affc0a5c89f3ea9b5558f1d3a9ea.png)