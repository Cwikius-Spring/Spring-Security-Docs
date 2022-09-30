# Spring Security 新功能

Spring Security 5.7 提供了一系列行的特性。

下面为特别值得指出的一些新特性。


## Servlet

* Web

** 新增 xref:servlet/authentication/persistence.adoc#requestattributesecuritycontextrepository[`RequestAttributeSecurityContextRepository`]
** 新增 xref:servlet/authentication/persistence.adoc#securitycontextholderfilter[`SecurityContextHolderFilter`] - Ability to require explicit saving of the `SecurityContext`
** 针对 xref:servlet/exploits/headers.adoc#servlet-headers-cross-origin-policies[Cross Origin Policies headers] 新增 DSL 支持

* OAuth 2.0 客户端

** 允许对 https://github.com/spring-projects/spring-security/issues/6548[PKCE for confidential clients] 进行配置
** Allow 在 `JwtBearerOAuth2AuthorizedClientProvider` 中配置一个 https://github.com/spring-projects/spring-security/issues/9812[JWT assertion resolver] 
** 允许在 https://github.com/spring-projects/spring-security/issues/9855[JWT client assertions] 自定义 claims

* SAML 2.0

** 新增 xref:servlet/appendix/namespace/http.adoc#nsa-saml2-login[SAML 2.0 Login & Single Logout XML support]


## WebFlux

* Web

** 允许在 `ServerHttpBasicAuthenticationConverter` 中自定义 customizing https://github.com/spring-projects/spring-security/issues/10903[charset] 
** 针对 xref:reactive/exploits/headers.adoc#webflux-headers-cross-origin-policies[Cross Origin Policies headers] 新增 DSL 支持

* OAuth 2.0 客户端

** 允许配置 https://github.com/spring-projects/spring-security/issues/6548[PKCE for confidential clients]
** 允许在 `JwtBearerReactiveOAuth2AuthorizedClientProvider` 中配置一个 https://github.com/spring-projects/spring-security/issues/9812[JWT assertion resolver] 