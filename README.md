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

