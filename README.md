# 安全相关
- jwt 
    - JWT实现的时候，一般会有两个过期时间
        - 第一个是Token本身的过期时间，这个时间一般1到2个小时，不能太长，也可以在短一点，不过5s的简直纯属扯淡。
        - 第二个是Token过期后，再次刷新的有效期，也就是Token过期后，你还有一段时间可以重新刷新，把过期的Token发给服务端，如果没有过刷新截止期，则服务端返回，不再需要通过用户名密码重新登录获取Token了。所以为了减少过期后重新获取Token所带来的麻烦，我们一般在每次Http请求成功后，将目前的Token刷新，然后可以在Http响应中返回新的Token。
        - JWT由于过期数据(expclaim)是封装在Payload中的，所以必须返回一个新Token，而不是在旧Token的基础上刷新。
        - 但是在并发的时候也会出现问题，如果前一个请求刷新了Token(为了安全，刷新后一般会把旧Token加入黑名单)，后面的请求使用了一个旧的Token像服务请求数据，这个时候请求会被拒绝。
        - 可以说这真的是JWT的一个缺陷，目前没有特别好的办法来解决并发刷新的问题。

        - 不过可以通过设置一个宽限时间，在Token刷新后，如果旧Token仍处于刷新宽限时间内，就放行。
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
