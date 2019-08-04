# springboot-swagger

What is Swagger ?
1. Develop APIs
2. Interact with APIs
3. Document APIs

SOAP - as a WSDL for documentation
REST - not have a formal documentation , so swagger came into picture.

Adding Swagger to Spring boot
1. Add swagger 2 spring dependency 
2. Enabling swagger in code 
3. configuring swagger 
4. Adding deatils as annotations to APIs


1. Create Spring boot project :-
a) create a maven project 
b) open the pom and add the followind details 
<parent>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-parent</artifactId>
        <version>2.1.3.RELEASE</version>
        <relativePath></relativePath>
    </parent>
    
    <dependencies>
        <dependency>
            <groupId>org.springframework.boot</groupId>
            <artifactId>spring-boot-starter-web</artifactId>
        </dependency>
    </dependencies>
    
    <build>
        <plugins>
            <plugin>
                <groupId>org.springframework.boot</groupId>
                <artifactId>spring-boot-maven-plugin</artifactId>
            </plugin>
        </plugins>
    </build>
    
 c) create Main class as 
 @SpringBootApplication
public class SpringBootSwagger2Application {

    public static void main(String[] args) {
        SpringApplication.run(SpringBootSwagger2Application.class,args);
    }
}

d) Create AddressBookResource as a resource with APIs
e) create Contact model 
f)

2) Add swagger dependency 
        <dependency>
            <groupId>io.springfox</groupId>
            <artifactId>springfox-swagger2</artifactId>
            <version>2.9.2</version>
        </dependency>
 3) Enable swagger 
        @EnableSwagger2
 4) Restart application and see the http://localhost:8090/v2/api-docs documentation api (swagger.json)
 5) Add following dependecy to interact with UI (html )
 
        <dependency>
            <groupId>io.springfox</groupId>
            <artifactId>springfox-swagger-ui</artifactId>
            <version>2.8.0</version>
        </dependency>
 
  6) Restart and http://localhost:8090/swagger-ui.html 
  
  7) Customizing :
  a) Docket is object for customize the swagger 
  @Bean
    public Docket swaggerConfiguration(){

        return new Docket(DocumentationType.SWAGGER_2)
                .select()
                .paths(PathSelectors.ant("/api/*"))
                .apis(RequestHandlerSelectors.basePackage("com.test"))
                .build();
    }
    restart and check swagger ui
    8) Adding application metadata
       a) AppInfo add
       private ApiInfo getApIInfo(){

        return new ApiInfo(
                "Address Book API",
                "Sample API for swagger tutorial",
                "1.0",
                "Free to use",
                new Contact("Harinatha","","harinatha.k@gmail.com"),
                "API Licence",
                "",
                Collections.emptyList());
    }
     public Docket swaggerConfiguration(){

        return new Docket(DocumentationType.SWAGGER_2)
                .select()
                .paths(PathSelectors.ant("/api/*"))
                .apis(RequestHandlerSelectors.basePackage("com.test"))
                .build()
                .apiInfo(getApIInfo());
    }
    
    
    
    
  
