1. hashMap原理  
    通过hash的方法，通过put和get存储和获取对象。存储对象时，我们将K/V传给put方法时，它调用hashCode计算hash从而得到bucket位置，进一步存储，HashMap会根据当前bucket的占用情况自动调整容量(超过Load Facotr则resize为原来的2倍)。获取对象时，我们将K传给get，它调用hashCode计算hash从而得到bucket位置，并进一步调用equals()方法确定键值对。如果发生碰撞的时候，Hashmap通过链表将产生碰撞冲突的元素组织起来，在Java 8中，如果一个bucket中碰撞冲突的元素超过某个限制(默认是8)，则使用红黑树来替换链表，从而提高速度。
2. hashMap线程是否安全  
    否 安全的是concurrentHashMap
 3. hashMap数组长度大于多少会进行红黑树  
    在默认链表长度为8的时候链表转换为二叉树查找的方式。
 4. hashMap红黑树原理   
 5. hashMap放值的时候，hash(key) key相同，算出来的位置不同，怎么处理（怎么找到正确的位置去放值）   
6. hashMap怎么扩容  
    当向容器添加元素的时候，会判断当前容器的元素个数，如果大于等于阈值(CAPACITY)---即当前数组的长度乘以加载因子的值的时候，就要自动扩容啦。
7. 五个服务器，两个服务器断了，其他服务器怎么记录登录的用户信息记录已经登录过  
8. 幻读的解释  
9. 事务的七种传播属性 
    * REQUIRED
    * SUPPORTS
    * MANDATORY
    * REQUIRES_NEW 
    * NOT_SUPPORTED
    * NEVER
    * NESTED
10. 四种隔离级别  
    * DEFAULT
    * READ_UNCOMMITTED
    * READ_COMMITTED
    * REPEATABLE_READ
    * SERIALIZABLE
11. spring事务中用的哪种隔离级别和传播属性  
12. 有关事务的几个关键字  
13. 怎么使用声明式事务  
    ① 添加依赖   
    ② 配置事务管理器   
    ③ 添加注解
14. 数据库连接池的作用  
15. 数据库存储引擎  
16. 唯一索引和主键索引的区别  
17. 索引有哪些类型  
18. 假如四个线程，十个服务器，每个服务器上都有这四个线程，怎么让这四个线程在这十个服务器上只运行一次  
19. 线程安全的实现方式   
20. 线程池有哪些，作用  
21. 线程的synchronized和volatile作用和他们的区别  
22. 常用的设计模式并解释  
23. BeanFactory和FactoryBean的区别  
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;BeanFactory是IOC最基本的容器，负责生产和管理bean，它为其他具体的IOC容器提供了最基本的规范  
    &nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;FactoryBean是一个接口，当在IOC容器中的Bean实现了FactoryBean后，通过getBean(String BeanName)获取到的Bean对象并不是FactoryBean的实现类对象，而是这个实现类中的getObject()方法返回的对象。要想获取FactoryBean的实现类，就要getBean(&BeanName)，在BeanName之前加上&。 
24. jvm五种内存模型  堆放哪些数据，堆又划分为几块  
    程序计数器(Program Counter Register)、Java栈(VM Stack)、本地方法栈(Native Method Stack)、方法区(Method Area)、堆(Heap)。 
    　堆是被所有线程共享的一块内存区域，在虚拟机启动时创建，用于存放对象实例。
    在JDK7以及其前期的JDK版本中，堆内存通常被分为三块区域Nursery内存(young generation)、长时内存(old generation)、永久内存(Permanent Generation for VM Matedata)
    JDK8中把存放元数据中的永久内存从堆内存中移到了本地内存(native memory)中
25. springmvc请求过程 
    1. 发送请求——>DispatcherServlet
    2. DispatcherServlet——>HandlerMapping
    3. HandlerAdapter——>controller
    4. ModelAndView 的逻辑视图名——> ViewResolver
    5. View——>渲染
    6. 返回控制权给 DispatcherServlet
26. spring ioc aop 用什么代替实现    
    IOC 控制反转 反射替代
    AOP 切面编程 代理替代
27. spring接口跟踪日志  
28. session工作机制  
29. 集合框架  
30. ES搜索引擎的使用  
31. 微服务  每个服务的跟踪日志（服务监控），分布式事务回滚，分库（主库和从库的数据同步）  
32. redis和数据库的同步  
33. redis里的数据，如果服务中断，缓存里的数据还有吗  
34. redis快照 rdb aof  
35. springcloud  ribbon负载均衡原理  feign怎么处理服务调用的  断路器怎么去防止服务血崩的  
36. Doubbo和feign的区别和他们协议的区别  
37. Doubbo原理及和zookeeper怎么使用的  
38. springcloud哪个去做服务监控的  
39. Java为什么具有跨平台性  
    因为字节码是在虚拟机上运行的，而不是编译器。换而言之，是因为JVM能跨平台安装，所以相应JAVA字节码便可以跟着在任何平台上运行。只要JVM自身的代码能在相应平台上运行，即JVM可行，则JAVA的程序员就可以不用考虑所写的程序要在哪里运行，反正都是在虚拟机上运行，然后变成相应平台的机器语言，而这个转变并不是程序员应该关心的。
40. jdk和jre的区别  
    JDK就是Java Development Kit.简单的说JDK是面向开发人员使用的SDK，它提供了Java的开发环境和运行环境。SDK是Software Development Kit 一般指软件开发包，可以包括函数库、编译程序等。
    JRE是Java Runtime Enviroment是指Java的运行环境，是面向Java程序的使用者，而不是开发者。

41. Integer的值缓存范围 :-128~127 







