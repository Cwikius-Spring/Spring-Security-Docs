# Spring Security 文档和手册（中文）

Spring Security 提供了一个 [验证（authentication）](features/authentication/index.md), [授权（authorization）](features/authorization/index.md)，和[保护常见攻击](features/exploits/index.md) 的框架。

Spring security 是一个强大的，并且可以高度定制的身份验证和访问控制框架，能够同时支持 [imperative](servlet/index.md) 和 [reactive](reactive/index.md) 应用， Spring security 已经成为保护 Spring 应用实事上的标准。

有关完整的特性列表，请参考本参考指南中有关[特性（Features）](features/index.md) 部分的内容。

## 开始使用
如果你已经开始准备对你的应用程序进行安全限制，请参考针对[servlet](servlet/getting-started.md) 和 [reactive](reactive/getting-started.md) 部分的内容。

?> 这里，提到了 2 个概念 servlet 和 reactive。Spring WebFlux 是 Spring Framework 5.0 中引入的新的响应式web框架。
与Spring MVC不同，它不需要Servlet API，是完全异步且非阻塞的，并且通过 Reactor 项目实现了 Reactive Streams 规范。
可以理解，servlet 和 reactive 是 2 个不同的处理方式，通常 MVC 模式是使用 servlet 的。reactive 是响应式，也可以说是反应式，主要特点就是异步处理，是基于 Spring WebFlux 框架的。

上面 2 个指南将会帮助你构建第一个使用 Spring Security 的应用程序。

如希望了解 Spring Security 是如何工作的，请参考 [Architecture](servlet/architecture.md) 部分的内容。

如你还有其他的一些内容，请访问 Spring Security 有关[社区(community)](community.md) 中的内容，通常你能够在这里获得不少的帮助。

### 社区和快速导航

在下面的列表格，我们列出了一些比较有用的 CWIKIUS 相关软件开发使用教程的导航，欢迎访问下面的链接获得更多的内容和参与讨论

| 网站名称           | URL                                                    | NOTE                       |
|----------------|--------------------------------------------------------|----------------------------|
| OSSEZ 社区       | [www.ossez.com](https://www.ossez.com/)                | 开放社区，欢迎注册参与讨论              |
| WIKI 维基        | [www.cwiki.us](https://www.cwiki.us/)                  | 使用 Confluence 部署的 WIKI 知识库 |
| DOCS.OSSEZ.COM | [https://docs.ossez.com/#/](https://docs.ossez.com/#/) | 本手册的编译版本将会部署在这个链接上         |
| CN 博客          | [http://www.cwikius.cn/](http://www.cwikius.cn/)       | CWIKIUS.CN 一个有独立思考和温度的清新站  |

[](prerequisites.md ':include')