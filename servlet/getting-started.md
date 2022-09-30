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

Spring Boot automatically:

* Enables Spring Security's default configuration, which creates a servlet `Filter` as a bean named `springSecurityFilterChain`.
  This bean is responsible for all the security (protecting the application URLs, validating submitted username and passwords, redirecting to the log in form, and so on) within your application.
* Creates a `UserDetailsService` bean with a username of `user` and a randomly generated password that is logged to the console.
* Registers the `Filter` with a bean named `springSecurityFilterChain` with the Servlet container for every request.

Spring Boot is not configuring much, but it does a lot.
A summary of the features follows:

* Require an authenticated user for any interaction with the application
* Generate a default login form for you
* Let the user with a username of `user` and a password that is logged to the console to authenticate with form-based authentication (in the preceding example, the password is `8e557245-73e2-4286-969a-ff57fe326336`)
* Protects the password storage with BCrypt
* Lets the user log out
* https://en.wikipedia.org/wiki/Cross-site_request_forgery[CSRF attack] prevention
* https://en.wikipedia.org/wiki/Session_fixation[Session Fixation] protection
* Security Header integration
  ** https://en.wikipedia.org/wiki/HTTP_Strict_Transport_Security[HTTP Strict Transport Security] for secure requests
  ** https://msdn.microsoft.com/en-us/library/ie/gg622941(v=vs.85).aspx[X-Content-Type-Options] integration
  ** Cache Control (can be overridden later by your application to allow caching of your static resources)
  ** https://msdn.microsoft.com/en-us/library/dd565647(v=vs.85).aspx[X-XSS-Protection] integration
  ** X-Frame-Options integration to help prevent https://en.wikipedia.org/wiki/Clickjacking[Clickjacking]
* Integrate with the following Servlet API methods:
  ** https://docs.oracle.com/javaee/6/api/javax/servlet/http/HttpServletRequest.html#getRemoteUser()[`HttpServletRequest#getRemoteUser()`]
** https://docs.oracle.com/javaee/6/api/javax/servlet/http/HttpServletRequest.html#getUserPrincipal()[`HttpServletRequest.html#getUserPrincipal()`]
** https://docs.oracle.com/javaee/6/api/javax/servlet/http/HttpServletRequest.html#isUserInRole(java.lang.String)[`HttpServletRequest.html#isUserInRole(java.lang.String)`]
** https://docs.oracle.com/javaee/6/api/javax/servlet/http/HttpServletRequest.html#login(java.lang.String,%20java.lang.String)[`HttpServletRequest.html#login(java.lang.String, java.lang.String)`]
  ** https://docs.oracle.com/javaee/6/api/javax/servlet/http/HttpServletRequest.html#logout()[`HttpServletRequest.html#logout()`]
