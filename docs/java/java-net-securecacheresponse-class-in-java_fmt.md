## Java中的`SecureCacheResponse`类

> 原文：[https://www.geeksforgeeks.org/java-net-securecacheresponse-class-in-java/](https://www.geeksforgeeks.org/java-net-securecacheresponse-class-in-java/)

Java中的`SecureCacheResponse`类表示最初通过安全方式检索的缓存响应。

**语法：** 类声明

```java
public abstract class SecureCacheResponse
extends CacheResponse
```

此类的构造函数如下：

```java
SecureCacheResponse()
```

现在，这个类的方法如下：

<figure class="table">

| 方法 | 描述 |
| --- | --- |
| `getCipherSuite()` | 此方法用于返回在原始检索网络资源的连接上使用的密码套件。 |
| `getLocalCertificateChain()` | 此方法用于返回在原始连接握手期间发送给服务器的证书链。 |
| `getLocalPrincipal()` | 此方法用于返回在原始检索网络资源的连接握手期间发送给服务器的主体。 |
| `getPeerPrincipal()` | 此方法用于返回服务器的主体，该主体是在为检索网络资源而建立的原始连接会话中确定的。 |
| `getServerCertificateChain()` | 此方法用于从缓存中返回服务器的证书链，该链是在为检索网络资源而建立的原始连接会话中确定的。 |

</figure>

### 示例

```java
// Java program to demonstrate SecureCacheResponse class
// Implementation and its methods

// Importing IOException and InputStream classes from
// java.io package
import java.io.IOException;
import java.io.InputStream;
// Importing java.net package for network linking
import java.net.*;
// Importing classes from java.security package to provide
// security framework to classes and interfaces
import java.security.Principal;
import java.security.cert.Certificate;
// Importing Map and List classes from java.util package
import java.util.List;
import java.util.Map;
// Importing class when peer not authenticated
import javax.net.ssl.SSLPeerUnverifiedException;

// Main class
// JavaSecureCacheResponse
public class GFG {

// Method 1
    // Main driver method
    public static void main(String args[]) throws Exception
    {

// Creating an final object of Principal class
        final Principal gfgPrincipal = new Principal() {
            // Method 2
            public String getName()
            {

// As it is simply retrieving names
                return null;
            }
        };

// Creating an object of this class
        // (SecureCacheResponse)
        final SecureCacheResponse secureCacheResponse
            = new SecureCacheResponse() {
                  // Method 3
                  // To get the name of the cipher suite
                  public String getCipherSuite()
                  {

// Returning the name of the cipher
                      // suite negotiated during this
                      // handshake This message will be
                      // displayed on console
                      return "Connection established";
                  }

// Method 4
                  // getLocalCertificateChain() method
                  public List<Certificate>
                  getLocalCertificateChain()
                  {
                      return null;
                  }

// Method 5
                  public List<Certificate>
                  getServerCertificateChain()
                      throws SSLPeerUnverifiedException
                  {

// Returning peer certificate chain
                      // associated with the ssl socket
                      return null;
                  }

// Method 6
                  // getPeerPrincipal() method
                  public Principal getPeerPrincipal()
                      throws SSLPeerUnverifiedException
                  {
                      return gfgPrincipal;
                  }

// Method 7
                  // getLocalPrincipal() method
                  public Principal getLocalPrincipal()
                  {
                      return gfgPrincipal;
                  }

// Method 8
                  public Map<String, List<String> >
                  getHeaders() throws IOException
                  {
                      return null;
                  }

// Method 9
                  public InputStream getBody()
                      throws IOException
                  {
                      return null;
                  }
              };

// Print and display commands which are returning
        // information

// 1. The cipher suite in use on the original
        // connection
        System.out.println(
            "getCipherSuite() method returns: "
            + secureCacheResponse.getCipherSuite());

// 2. The server's principal which was recognized
        // as a part of determining the session.
        System.out.println(
            "getPeerPrincipal() method returns: "
            + secureCacheResponse.getPeerPrincipal());

// 3. An immutable List of Certificate representing
        // the certificate chain that was sent to the
        // server.

// 4. null, as no certificate chain was sent
        System.out.println(
            "getLocalCertificateChain() returns: "
            + secureCacheResponse
                  .getLocalCertificateChain());

// 5. Principal that was sent to the server
        // during the handshaking of the original connection
        System.out.println(
            "getLocalPrincipal() method returns: "
            + secureCacheResponse.getLocalPrincipal());
    }
}
```

**输出**

```java
getCipherSuite() method returns: Connection established
getPeerPrincipal() method returns: GFG$1@34a245ab
getLocalCertificateChain() returns: null
getLocalPrincipal() method returns: GFG$1@34a245ab
```