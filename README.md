# 安全相关
- jwt 
- Spring Cloud Security
- spring-security
  - 权限相关
    -  想要开启Spring方法级安全，你需要在已经添加了@Configuration注解的类上再添加@EnableGlobalMethodSecurity注解
    -  加上 @PreAuthorize("hasAuthority('USER')") ，标明这个资源只能被拥有 USER 权限的用户访问
    -  [Spring Security 4 使用@PreAuthorize,@PostAuthorize, @Secured, EL实现方法安全（带源码）](http://blog.csdn.net/w605283073/article/details/51327182)
  - [Spring Security在登录验证中增加额外数据（如验证码）](http://www.cnblogs.com/phoenix-smile/p/5666686.html)
  - 参考文档有安全表达试的介绍,比如下面代表的意思:传入的联系人为当前的认证用户,才可以执行doSomething方法
@PreAuthorize("#c.name == authentication.name")
  -  [Spring Security（16）——基于表达式的权限控制](http://elim.iteye.com/blog/2247073)

# 前端
- angularjs
- ionic

# 数据模型
- jpa
- mybatis

# 微服务
- 数据资源手册
- 当事人
- 产品与服务
- 运输

# 相关技术
- redis
 - [Redis应用场景](http://www.scienjus.com/redis-use-case/)
- token
 - [RESTful登录设计（基于Spring及Redis的Token鉴权）](http://www.scienjus.com/restful-token-authorization/)
- restful
 - [我所认为的RESTful API最佳实践](http://www.scienjus.com/my-restful-api-best-practices/)
