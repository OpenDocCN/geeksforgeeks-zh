# PHP 中如何进行异步 HTTP 请求？

> 原文:[https://www . geesforgeks . org/how-to-make-异步-http-requests-in-php/](https://www.geeksforgeeks.org/how-to-make-asynchronous-http-requests-in-php/)

异步 HTTP 请求帮助我们在不同的线程中使用非阻塞输入或输出来处理 HTTP 请求。有人称之为 COMET 能力。异步 HTTP 请求的主要用途是当客户端请求服务器延迟响应时。一个常见的例子是 AJAX 聊天客户端，我们从客户端和服务器推或拉。这些场景会在服务器的套接字上长时间阻止客户端等待新消息。

PHP 同步服务请求。这意味着每一行代码都以脚本的同步方式执行。从一行获得结果后，它执行下一行，或者在跳转到下一行代码之前等待结果。有些情况下，我们应该向网址发出请求，但它们并不相互依赖。在这种情况下，我们不希望等待一个请求的结果来执行其他请求。因此，我们发出异步请求。

**Guzzle 6:** Guzzle 是一个帮助发送 HTTP 请求的 PHP HTTP 客户端。这些方法可以用来发送异步 HTTP 请求。

*   RequestAsync，
*   路径异步，
*   GetAsync，
*   HeadAsync，
*   PutAsync，
*   PostAsync，
*   DeleteAsync，
*   patchaasync

下载 Guzzle php 包。可以通过 composer 安装。

```htmlhtml
php composer.phar require guzzlehttp/guzzle:~6.0
```

或者

```htmlhtml
composer require guzzlehttp/guzzle:~6.0
```

请在代码的脚本部分包含“自动加载”文件，以便它加载所有的类和方法。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```htmlhtml
<?php

require_once(__DIR__ . '/vendor/autoload.php');
$client = new GuzzleHttp\Client();

$promises = [
    $client->getAsync('http://localhost')
            ->then(function ($response)
    { echo '10'; }),

    $client->getAsync('http://www.google.com')
            ->then(function ($response)
    { echo '20'; }),

    $client->getAsync('http://localhost')
            ->then(function ($response)
    { echo '30'; }),

    $client->getAsync('http://localhost')
            ->then(function ($response)
    { echo '40'; }),

    $client->getAsync('http://localhost')
            ->then(function ($response)
    { echo '50'; }),

    $client->getAsync('http://localhost')
            ->then(function ($response)
    { echo '60'; }),

    $client->getAsync('http://localhost')
            ->then(function ($response)
   { echo '70'; }),
];

$results = GuzzleHttp\Promise\unwrap($promises);

// Please wait for a while to complete 
// the requests(some of them may fail)
$results = GuzzleHttp\Promise\settle(
        $promises)->wait();

print "finish/over." . PHP_EOL;
?>
```

在上面的代码中，包含了“自动加载”文件，然后创建了 Guzzle Http 客户端对象，该对象存储在“客户端”变量中，并且对于每个 Http 请求**GetSync()**方法都与 URL 一起使用。
获得第一个响应的请求将打印号码。请求的顺序无关紧要。

**使用承诺的异步 HTTP 请求:**异步操作的单个结果代表一个**承诺**。异步请求用于 HTTP 操作的非阻塞。当异步 HTTP 请求发送一个承诺时，它会被返回。

**使用 HTTPlug 执行请求:**

```htmlhtml
$request = $messageFactory->createRequest(
    'GET', 'http://php-http.org');
$promise = $client->sendAsyncRequest($request);
echo  'Non-blocking!';

```

**等待:**从上面返回的“承诺”实现 *http\Promise\Promise* 。目前还不知道对此的反应。等待回复。

```htmlhtml
try {
  $response = $promise->wait();
} catch (\Exception $exception) {
  echo $exception->getMessage();
}  

```

**然后:**不用等待，我们可以异步执行步骤。调用**然后用两个参数调用**方法。

1.  如果请求成功，将执行一次回调。
2.  如果请求导致错误，将执行的回调。

```htmlhtml

// Success Callback
function (ResponseInterface $response) {

    echo 'New response!';

    // Write status code to the log file
    file_put_contents('responses.log', 
        $response->getStatusCode() . "\n", FILE_APPEND);
    return $response;
},

// Failure Callback
function (\Exception $exception) {
    echo 'We have a problem';
    throw $exception;
}
```

**Concurrency in Promise:**Concurrency 表示多个计算同时发生。当我们同时处理许多请求时，这是很好的。对于并发性，我们必须使用“每个承诺”类和收益生成器，最后在程序的末尾添加 **wait()** 。

## 服务器端编程语言（Professional Hypertext Preprocessor 的缩写）

```htmlhtml
<?php

use GuzzleHttp\Promise\EachPromise;
use GuzzleHttp\Psr7\Response;

$users = ['one', 'two', 'three'];

$promises = (function () use ($users) {
    foreach ($users as $user) {

        // Using generator
        yield $this->getAsync(
   'https://api.demo.com/v1/users?username='
        . $user);        
    }
})();

$eachPromise = new EachPromise($promises, [

    // Number of concurrency
    'concurrency' => 4,
    'fulfilled' => function (Response $response) {
        if ($response->getStatusCode() == 200) {
            $user = json_decode(
                $response->getBody(), true);

            // processing response of the user
        }
    },

    'rejected' => function ($reason) {
    // handle promise rejected 
    }
]);

$eachPromise->promise()->wait();
?>
```

**构建多线程 cURL 请求:**一般来说，我们可以处理多个请求。首先，我们触发第一个并处理响应，然后是第二个和第三个，以此类推。但是，这个过程既缓慢又耗时。但是 cURL 提供了 **curl_multi_*** 功能来处理任何 asnyc 请求。

```htmlhtml
$running = null;
$mh = curl_multi_init();

$ch1 = curl_init();
curl_setopt($ch1, CURLOPT_URL, 'https://endpoint.com');

// Other curl options....
curl_multi_add_handle($mh, $ch1);

$ch2 = curl_init();
curl_setopt($ch2, CURLOPT_URL, 'https://endpoint.com');

// Other curl options....  
curl_multi_add_handle($mh, $ch2);

do {
   curl_multi_exec($mh, $running);
   curl_multi_select($mh);
} while ($running > 0);

$r1 = curl_multi_getcontent($ch1);
$r2 = curl_multi_getcontent($ch2);
curl_multi_remove_handle($mh, $ch1);
curl_multi_remove_handle($mh, $ch2);
curl_multi_close($mh);

```

响应收集在“r1”和“r2”变量中。在这些 cURL 函数的帮助下，我们可以并行触发请求，以节省时间并更快地处理响应。