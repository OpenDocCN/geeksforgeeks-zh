# JSON 使用 Jackson 在 REST API 中与 Spring Boot 实现

> 原文: [https://www.geeksforgeeks.org/json-using-jackson-in-rest-api-implementation-with-spring-boot/](https://www.geeksforgeeks.org/json-using-jackson-in-rest-api-implementation-with-spring-boot/)

每当我们用 [Spring (Spring Boot)](https://www.geeksforgeeks.org/introduction-to-spring-boot/) 实现 [REST API](https://www.geeksforgeeks.org/rest-api-introduction/) 时，我们都会遇到在 API 的 [JSON](https://www.geeksforgeeks.org/difference-between-json-and-csv/) 响应中排除空值的要求。此外，可能需要将打开/关闭此功能具体化：**在 JSON 响应中排除空值**，从而允许应用编程接口的使用者根据需要进行定制。

在本文中，我们总结了使用 `Jackson` 实现上述特性的 ON/OFF 外部化的方法，`Jackson` 是一个基于 Java 的库，用于将 Java 对象序列化或映射到 JSON，反之亦然。

**不成功的方法：**

最初，我们尝试了 Spring Boot 现成的方法，但没有成功，例如：

*   在 `application.properties` 中具有 `spring.jackson.serialization-inclusion` 属性。该属性取值为：`always` / `non-null` / `non-empty` / `non-default` / `non-absent`。
*   扩展 `WebMvcConfigurationSupport` 类并定制 Spring Boot 配置，见下文。

## Java 语言（一种计算机语言，尤用于创建网站）

```java
@Configuration
class WebMvcConfiguration extends WebMvcConfigurationSupport {
    @Override
    protected void extendMessageConverters(List<HttpMessageConverter<?>> converters) {
        for (HttpMessageConverter<?> converter : converters) {
            if (converter instanceof MappingJackson2HttpMessageConverter) {
                ObjectMapper mapper = ((MappingJackson2HttpMessageConverter) converter).getObjectMapper();
                mapper.setSerializationInclusion(Include.NON_NULL);
            }
        }
    }
}
```

现在，创建一个实例 `org.springframework.http.converter.json.Jackson2ObjectMapperBuilderCustomizer`，下面给出的代码供大家参考。

## Java

```java
@Bean
public Jackson2ObjectMapperBuilderCustomizer customJackson() {
    return new Jackson2ObjectMapperBuilderCustomizer() {
        @Override
        public void customize(Jackson2ObjectMapperBuilder builder) {
            builder.serializationInclusion(Include.NON_NULL);
            builder.failOnUnknownProperties(false);
        }
    };
}
```

**成功方法：**

创建一个 JSON 响应对象，如果没有创建的话。这是在序列化为 JSON 时，基于 `application.properties` 中的属性，您想要“**排除/包含空字段**”特征的对象。您可以在下面看到响应对象，以供参考。

## Java

```java
public class RegistrationResponse {

    @JsonProperty("success")
    private Boolean success = null;

    @JsonProperty("message")
    private String message = null;

    @JsonProperty("data")
    private String data = null;

    @JsonProperty("error_code")
    private Integer errorCode = null;

    public RegistrationResponse success(Boolean success) {
        this.success = success;
        return this;
    }

    @NotNull
    public Boolean isSuccess() {
        return success;
    }

    public void setSuccess(Boolean success) {
        this.success = success;
    }

    public RegistrationResponse message(String message) {
        this.message = message;
        return this;
    }

    @NotNull
    public String getMessage() {
        return message;
    }

    public void setMessage(String message) {
        this.message = message;
    }
}
```

创建一个名为 `config.response.json.format.exclude_null` 的属性，该属性可以将值取为 `true` 或 `false`。值 `true` 表示在 JSON 响应中排除空字段 & 值 `false` 表示不排除空字段。此外，将此属性绑定到类级属性，以便可以读取该值。下面给出的代码供您参考。

```properties
config.response.json.format.exclude_null = false
```

```java
@Value("${config.response.json.format.exclude_null}")
private boolean toExcludeNull;
```

通过创建 `ObjectMapper` 的实例来实现基于全局属性值排除空值的实际逻辑。

*   将创建的 mapper 的 `serializationInclusion` 属性设置为 `Include.NON_BLANK`，如果全局属性值为 true，否则设置为 `Include.ALWAYS`。
*   使用 mapper 将响应对象序列化为字符串并返回该字符串。确保处理 `JsonProcessingException`。

让我们看看下面作为 API 实现的一部分构建 JSON 响应时要添加的实际代码片段。

## Java

```java
RegistrationResponse regResp = new RegistrationResponse();

regResp.setSuccess(true);
regResp.setErrorCode(null);
regResp.setData("testdata");
regResp.setMessage("success");

ObjectMapper mapper = new ObjectMapper();
mapper.enable(SerializationFeature.INDENT_OUTPUT);

if (toExcludeNull) mapper.setSerializationInclusion(Include.NON_NULL);
else mapper.setSerializationInclusion(Include.ALWAYS);

String regRespStr = null;
try {
    regRespStr = mapper.writeValueAsString(regResp);
} catch (JsonProcessingException e) {
    e.printStackTrace();
}
System.out.println("Formatted JSON Response:" + regRespStr);
```

这里，`regRespStr` 是应用了空排除/包含的 JSON 字符串。

**也可以查看 [Github 资源库](https://github.com/myblogs-demos/demo-jsonnullexclusion-proj)。**