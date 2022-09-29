# 系统要求
Spring Security 需要 JDK 8 或更高的版本。

由于 Spring Security 是以独立的方式运作, 所以,不需要在你的 Java 运行环境配置特殊的文件。 也不需要配置专门的 Java 认证和授权服务(JAAS)策略文件，或者将 Spring Security 的位置放到普通的类载入路径（classpath）中。

同样的，如果你使用的是 EJB 或 Servlet 容器，也不需要在任何地方放置特殊的配置文件，或者将 Spring Security 的位置放到普通的类载入路径（classpath）中。

所有需要的文件和类已经打包到你的应用程序中了。

这种设计给为应用的部署署时间提供了最大的灵活性，你可以非常简单拷贝你的部署文件（可以是 JAR, WAR 或者 EAR）从一个系统到另一个系统中，你的应用可以马上工作。