# Servlet 应用程序

Spring Security 使用标准的 Servlet `过滤器（Filter）` 并与 Servlet 容器集成。
这个意味着 Spring Security 可以在任何运行运行在 Servlet 容器（Servlet Container）中的应用上使用。
更具体地说，你可以不使用 Spring，而是基于 Servlet 的应用程序中使用 Spring Security。

因为我们都知道，Spring 是可以通过 Spring Boot 启动的，实际上启动的时候 Spring 也会启动一个嵌入式 Tomcat。

Spring Security 的这种设计意味着，我们可以不使用 Spring Boot 启动的容器，而直接使用一个 Tomcat 容器。

[](getting-started.md ':include')

[](architecture.md ':include')