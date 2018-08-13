# Spring Boot

## 微服务

>为什么要使用SpringBoot？

目前软件架构流行前后端分离，目前很多公司都使用微服务

### 微服务与Spring Boot

微服务——> SpringCloud ——> SpringBoot

## 优势

SpringBoot 简化配置
SpringBoot 是下一代框架
SpringBoot 是为SpringCloud打基础

## IDE

### IJ IDEA

第一次启动，使用`http://maven.aliyun.com/nexus/content/groups/public` 加速下载相关依赖

pom.xml

```xml
    <mirror>
        <id>nexus-aliyun</id>
        <mirrorOf>*</mirrorOf>
        <name>Nexus aliyuan</name>
        <url>http://maven.aliyun.com/nexus/content/groups/public</url>
    </mirror>
```

## 启动

1、IDEA 启动main方法

2、bash到项目目录下 `mvn spring-boot:run`

3、编译下
    `mvn install`
    `cd target`
    `java -jar yourjarproject.jar`
  
## 注解

1. @Value  从配置文件读取参数
2. @ConfigurationProperties 把yml里面一组配置参数封装成一个类
3. @Component 向SpringBoot注册一个类
4. @Autowired 注入一个类

## 配置

### applcation.properties

```properties
server.port = 8080端口配置
server.context-path = /girl URL前缀
```

### yml

```yml
server:
   port: 8081  
```

指定读取的配置文件，每一个：后面需要跟一个空格，yml文件格式规定

如：自定义对象boy

1. 实体类名上加@ConfigurationProperties(prefix="boy"),
2. 加上@Component.否则找不到实体类的bean

## RESTful Api

`@RestController==@Controller +@ResponseBody`

匹配多个路径：
`@RequestMapping(value={“hello”，“hi”} ,method=RequestMethod.GET)`

注解等价

```java
@GetMapping();
@RequestMapping(value = '/boy', method = RequestMethod.GET);

@PutMapping();
@RequestMapping(value = '/boy', method = RequestMethod.PUT);

@PostMapping();
@RequestMapping(value = '/boy', method = RequestMethod.POST)

@DeleteMapping();
@RequestMapping(value = '/boy', method = RequestMethod.DELETE)

```