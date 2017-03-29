# 第一节  Spring Boot基本框架的搭建<br>
## 一、Intellij中Spring Boot基本框架的搭建<br>
### 1、在Intellij中选择Spring Initializr然后Next,填写Group、package、artifact,再Next选择支持的Web模块，然后再填写项目的文件名称即可。<br>
#### <font color="red">group一般和Java package一样表示</font><br>
#### <font color="red">groupID 表示项目所属组</font><br>
#### <font color="red">Artifact 表示项目在项目组中的ID</font><br>
#### <font color="red">version表示版本</font><br>
### 2、在新建的packe中，使Application.java位于根目录下面，否则会出现扫描不到Bean。例如：<br>


* com
    * example
        * Application.java（Spring Boot M主函数）</br>
        * domain(实体类的包)<br>
            * Author.java<br>
        * service(service层的包)
            * AuthorService
        * controller(controller层的包)
            * AuthorController

### 3、（本章先做简单的介绍）直接在Application下面写Controller的方法。<br>
```Java
@SpringBootApplication
@Controller
public class DemoApplication {

	@RequestMapping("/")
	public String value(){
		return "value";
	}

	public static void main(String[] args) {
		SpringApplication.run(DemoApplication.class, args);
	}
}
```
<font color="red">注意：Application.java中注解必须是@ResutController,@Controller是不可以的</font>

### 4、打开浏览器访问http://localhost:8080/就会返回“value”。<br>

