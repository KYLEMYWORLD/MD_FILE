# SpringBoot

## `@Spring BootApplication`

> Spring boot 入口类
>
> 该注解封装了以下三个注解
>
> `@Spring BootConfiguration`:配置类注解
>
> `@EnableAutoConfiguration`:启用自动配置注解
>
> `@ComponentScan`:组件扫描注解



## Spring Boot 配置类注解

1. `@SpringBootConfiguration` 与`@Component`注解是一样的

2. `@SpringBootConfiguration`是SpringBoot包装的@Configuration注解

3. 而`@Configuration`注解使用的是`@Component`注解
4. `@Component`注解：把普通POJO实例化到Spring容器中，相当于配置文件中的<bean id="" class""/>

## 启用自动配置注解

`@EnableAutoConfiguration`:是Spring Boot的最核心注解

## 组件扫描注解

`@ComponentScan`提供的功能与Spring XML配置文件的`<context:component-scan>`元素等价



# 深入理解Spring Boot自动配置

## 传统的SSM开发过程

1. Spring + SpringMVC + MyBatis, 曾经是主流的企业级架构方案，标准的MVC分级架构设计模式
2. 将系统分为模板视图（View）层，控制器（Controller）层，业务逻辑 Service 层，数据库访问 Dao 层。
3. 使用Spring MVC负责请求的转发和视图管理，使用Spring核心容器实现业务对象的协作和生命周期管理，MyBatis作为数据库ORM层的对象持久化引擎。
4. 需要小心翼翼的配置pom.xml中的各种项目依赖及其版本以保证Jar包不冲突
5. pom.xml将是一个庞大的依赖配置，动辄百行，各种版本号需要对应的上，版本兼容。
6. Spring.xml配置文件是Spring的BeanFactory工厂进行Bean生产，依赖关系注入（装配）及Bean实例分发的图纸总纲。
7. Web.xml文件是用来初始化整个项目的配置信息。比如Welcome页面，servlet,servlet-mapping,filter,listener,启动加载级别。

## Spring Boot自动配置原来

### Java配置

1. 组件扫描（Component Scan）：Spring去自动发现应用发现应用上下文中创建的Bean.
2. 自动装配（Autowired）：Spring自动创建Bean之间的依赖。
3. 通过JavaConfig方式实现Java代码配置Bean.
4. 

