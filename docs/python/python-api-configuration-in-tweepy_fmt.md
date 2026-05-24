# API.configuration() in Python–Tweepy

> 原文: [https://www.geeksforgeeks.org/python-api-configuration-in-tweepy/](https://www.geeksforgeeks.org/python-api-configuration-in-tweepy/)

**Twitter** 是一个流行的社交网络，用户在这里分享被称为推文的消息。Twitter 允许我们使用 Twitter API 或 **Tweepy** 挖掘任何用户的数据。这些数据将是从用户那里提取的推文。首先要做的是从 Twitter Developer 获取 `consumer_key`、`consumer_secret`、`access_key` 和 `access_secret`，每个用户都可以轻松获得。这些密钥将帮助 API 进行身份验证。

## API.configuration()

Tweepy 模块中 `API` 类的 `configuration()` 方法用于获取 Twitter 使用的当前配置。

> **语法:** `API.configuration()`
>
> **参数:** 无
>
> **返回:** 类字典的一个对象

### 示例

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

# getting the configuration
configuration = api.configuration()

# printing the information
for key, value in configuration.items():
    print(key + " : " + str(value), end = "\n\n")
```

### 输出

> dm_text_character_limit : 10000
>
> characters_per_media : 24
>
> max_media_per_upload : 1
>
> non_username_paths: ['about', 'account', 'activity', 'all', 'notifications', 'anywhere', 'api_rules', 'api_terms', 'apps', 'auth', 'badges', 'blog', 'business', 'buttons', 'contacts', 'devices', 'direct_messages', 'download', 'downloads', 'edit_notifications', 'faq', 'favorites', 'find_sources', 'find_users', 'followers', 'following', 'friend_request', 'friends']
>
> photo_size_limit : 3145728
>
> photo_sizes: {'thumb': {'h': 150, 'resize': 'crop', 'w': 150}, 'small': {'h': 480, 'resize': 'fit', 'w': 340}, 'medium': {'h': 1200, 'resize': 'fit', 'w': 600}, 'large': {'h': 2048, 'resize': 'fit', 'w': 1024}}
>
> short_url_length : 23
>
> short_url_length_https : 23