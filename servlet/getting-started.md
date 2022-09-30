# Hello Spring Security

本节介绍了如何把 Spring Security 与 Spring Boot 结合使用的最小设置。

?> 完整的本示例程序可以在 https://github.com/spring-projects/spring-security-samples/tree/5.7.x/servlet/spring-boot/java/hello-security 仓库中找到。
为了方便您的使用和测试，你可以 [单击这里](https://start.spring.io/starter.zip?type=maven-project&language=java&packaging=jar&jvmVersion=1.8&groupId=example&artifactId=hello-security&name=hello-security&description=Hello%20Security&packageName=example.hello-security&dependencies=web,security) 
下载 zip 的版本直接解压后运行。


## 更新依赖

针对已经下载下来的版本，唯一需要做的就是更新 [Maven](getting-spring-security.md#getting-maven-boot) 或者 [Gradle](getting-spring-security.md#getting-gradle-boot) 依赖。


## 启动 Hello Spring Security Boot 应用

现在，你可以使用 Maven 的插件 `run` [运行 Spring Boot 应用](https://docs.spring.io/spring-boot/docs/current/reference/htmlsingle/#using-boot-running-with-the-maven-plugin)。 
下面的代码显示了使用这个插件如何启动这个应用（以及执行本操作的控制台输出）：

```shell
$ ./mvn spring-boot:run
...
INFO 23689 --- [  restartedMain] .s.s.UserDetailsServiceAutoConfiguration :

Using generated security password: 8e557245-73e2-4286-969a-ff57fe326336
```

?> 有关这个项目的运行，请参考页面：https://www.ossez.com/t/hello-spring-security-boot/14119 中的内容。

## Spring Boot 自动配置

// FIXME: Link to relevant portions of documentation
// FIXME: Link to Spring Boot's Security Auto configuration classes
// FIXME: Add a links for what user's should do next

Spring Boot 自动配置：

* 在 Spring Boot 中启用 Spring Security 的默认配置。这个配置将会创建一个 servlet `Filter`（过滤器），这个 Bean 被命名为 `springSecurityFilterChain`。
  这个 Bean 将会在你的应用中负责所有的安全策略，包括但不限于，保护应用 URLs，对提交的用户名和密码进行校验，重定向登录表单等）。
* 创建一个名为 `UserDetailsService` 的 bean，使用的用户名为  `user`，同时对这个用户生成一个随机的密码，并将这个密码输出到控制台中。
* 针对每个请求都会调用的一个被命名为 `springSecurityFilterChain` 的 Bean 到 Servlet 容器的 `Filter`中。

Spring Boot 并没有配置很多，但是却做了很多。 
主要的一些特性如下：

* 对所有需要使用的系统用户先进行授权
* 为你创建一个默认的登录表单
* 让用户可以使用 `user` 用户名和在控制台中打印的密码进行登录（在这个示例中，密码为 `8e557245-73e2-4286-969a-ff57fe326336`）
* 使用 BCrypt 算法对存储的密码进行保护
* 让用户可以注销登录
* 阻止 [CSRF 攻击](https://en.wikipedia.org/wiki/Cross-site_request_forgery)
* [固定会话（Session Fixation）](https://en.wikipedia.org/wiki/Session_fixation) 保护
* Header 的安全整合 
  * 针对安全请求，使用[HTTP Strict Transport Security](https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security)
  * 集成[X-Content-Type-Options](https://msdn.microsoft.com/en-us/library/ie/gg622941(v=vs.85).aspx)
  * 缓存控制（可以在你的应用程序中对这个进行重写，以允许缓存你的静态资源） 
  * 集成[X-XSS-Protection](https://msdn.microsoft.com/en-us/library/dd565647(v=vs.85).aspx)
  * 集成 X-Frame-Options 来防止点击劫持 [Clickjacking](help prevent https://en.wikipedia.org/wiki/Clickjacking)
* 集成以下的 Servlet API 方法
  * [`HttpServletRequest#getRemoteUser()`](https://docs.oracle.com/javaee/6/api/javax/servlet/http/HttpServletRequest.html#getRemoteUser())
  * [`HttpServletRequest.html#getUserPrincipal()`](https://docs.oracle.com/javaee/6/api/javax/servlet/http/HttpServletRequest.html#getUserPrincipal())
  * [`HttpServletRequest.html#isUserInRole(java.lang.String)`](https://docs.oracle.com/javaee/6/api/javax/servlet/http/HttpServletRequest.html#isUserInRole(java.lang.String))
  * [`HttpServletRequest.html#login(java.lang.String, java.lang.String)`](https://docs.oracle.com/javaee/6/api/javax/servlet/http/HttpServletRequest.html#login(java.lang.String,%20java.lang.String))
  * [`HttpServletRequest.html#logout()`](https://docs.oracle.com/javaee/6/api/javax/servlet/http/HttpServletRequest.html#logout())
