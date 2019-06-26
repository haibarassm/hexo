# Spring IOC and Spring AOP
## 依赖注入
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;所谓的依赖注入，其实是当一个bean实例引用到了另外一个bean实例时spring容器帮助我们创建依赖bean实例并注入（传递）到另一个bean中，如上述案例中的AccountService依赖于AccountDao，Spring容器会在创建AccountService的实现类和AccountDao的实现类后，把AccountDao的实现类注入AccountService实例中，下面分别介绍setter注入和构造函数注入。
## IOC和AOP的区别
 &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;IOC,(Inverse of Control)控制反转，其包含两个内容：其一是控制，其二是反转。在程序中，被调用类的选择控制权从调用它的类中移除，转交给第三方裁决。这个第三方指的就是Spring的容器。IoC另解，依赖注入（Dependency Injection），调用类对被调用类的依赖关系由第三方注入，以移除调用类对被调用类的引用。
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;AOP,面向切面编程(也叫面向方面)：Aspect Oriented Programming(AOP),是目前软件开发中的一个热点，也是Spring框架中的一个重要内容。利用AOP可以对业务逻辑的各个部分进行隔离，从而使得业务逻辑各部分之间的耦合度降低，提高程序的可重用性，同时提高了开发的效率。   
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;AOP是OOP的延续，是（Aspect Oriented Programming）的缩写，意思是面向切面（方面）编程。主要的功能是：日志记录，性能统计，安全控制，事务处理，异常处理等等。 　  
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;主要的意图是：将日志记录，性能统计，安全控制，事务处理，异常处理等代码从业务逻辑代码中划分出来，通过对这些行为的分离，我们希望可以将它们独立到非指导业务逻辑的方法中，进而改变这些行为的时候不影响业务逻辑的代码.
