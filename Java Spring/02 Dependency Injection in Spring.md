# IoC Container

IoC container is responsible to instantiate, configure and assemble the objects. IoC container gets informations from XML file. 

The main tasks performed by IoC:
* instantiate the application class.
* configure the object .
* assemble the dependencies between the objects.

Two Types of IoC:
* BeanFactory
* ApplicationContext

## Difference between BeanFactory and the ApplicationContext

**ApplicationContext** is built on the top of the **BeanFactory** interface, its add some extra functionality than BeanFactory such as simple integration with Spring's AOP, message resource handling (for I18N), event propagation, application layer specific context (e.g. WebApplicationContext) for web application. So it is better to use ApplicationContext than BeanFactory.

### Using BeanFactory
XmlBeanFactory is the implementation class for the BeanFactory interface

```java 
Resource resource=new ClassPathResource("applicationContext.xml");
BeanFactory factory=new XmlBeanFactory(resource);
```


#### Using ApplicationContext
The **ClassPathXmlApplicationContext** class is the implementation class of the ApplicationContext interface, We need to instantiate the ClassPathXmlApplicationContext class to use the ApplicationContext as given below

```java
ApplicationContext context = 
	 new ClassPathXmlApplicationContext("applicationContext.xml");
```
