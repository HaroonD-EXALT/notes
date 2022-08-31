# Spring Framework

Spring is a _lightweight_ framework. It can be thought of as a _framework of frameworks_ because it provides support to various frameworks such as [Struts](https://www.javatpoint.com/struts-2-tutorial), [Hibernate](https://www.javatpoint.com/hibernate-tutorial), Tapestry, [EJB](https://www.javatpoint.com/ejb-tutorial), [JSF](https://www.javatpoint.com/jsf-tutorial), etc. The framework, in broader sense, can be defined as a structure where we find solution of the various technical problems.


### Inversion Of Control (IOC) and Dependency Injection
These are the design patterns to remove depencency from the code. 

```java
class Employee{  
	Address address;  
	Employee(){  
		address=new Address();  
	}  
}
```

In such case, there is dependency between the Employee and Address (tight coupling). In the Inversion of Control scenario, we do this something like this:

```java
class Employee{  
	Address address;  
	Employee(Address address){
		this.address=address;
	}  
}
```
Thus, IOC makes the code loosely coupled. In such case, there is no need to modify the code if our logic is moved to new environment.

In Spring framework, IOC container is responsible to inject the dependency. We provide metadata to the IOC container either by XML file or annotation.

#### Advantage of Dependency Injection

-   makes the code loosely coupled so easy to maintain
-   makes the code easy to test


# Spring Modules


![[spring modules.png]]
