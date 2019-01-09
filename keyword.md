# keyword
## static
1. static 关键字用法 能修饰什么 有什么作用
2. ”static” 关键字是什么意思？Java 中是否可以覆盖(override) 一个 private 或者是 static 的方法？   
“static” 关键字表明一个成员变量或者是成员方法可以在没有所属的类的实例变量的情况下被访问。  
Java 中 static 方法不能被覆盖，因为方法覆盖是基于运行时动态绑定的，而 static 方法是编译时静态绑定的。static 方法跟类的任何实例都不相关，所以概念上不适用。  
3. 是否可以在 static 环境中访问非 static 变量？  
static 变量在 Java 中是属于类的，它在所有的实例中的值是一样的。当类被Java虚拟机载入的时候，会对 static 变量进行初始化。如果你的代码尝试不用实例来访问非 static 的变量，编译器会报错，因为这些变量还没有被创建出来，还没有跟任何实例关联上。
## public, private, protected,default
1. 访问修饰符 public, private, protected, 以及不写（默认）时的区别  
类的成员不写访问修饰时默认为 default 。默认对于同一个包中的其他类相当于公开（public），对于不是同一个包中的其他类相当于私有（private）。受保护（protected）对子类相当于公开，对不是同一包中的没有父子关系的类相当于私有。Java 中，外部类的修饰符只能是 public 或默认，类的成员（包括内部类）的修饰符可以是以上四种。
## volatile
1. volatile关键字是否能保证线程安全  
不能,volatile 关键字用在多线程同步中，可保证读取的可见性，JVM只是保证从主内存加载到线程工作内存的值是最新的读取值，而非 cache 中。但多个线程对 volatile 的写操作，无法保证线程安全。例如假如线程 1，线程 2 在进行 read,load 操作中，发现主内存中 count 的值都是 5，那么都会加载这个最新的值，在线程 1 堆 count 进行修改之后，会 write 到主内存中，主内存中的 count 变量就会变为 6；线程 2 由于已经进行 read,load 操作，在进行运算之后，也会更新主内存 count 的变量值为 6；导致两个线程及时用 volatile 关键字修改之后，还是会存在并发的情况。
## assert
1.  什么时候用 assert  
assertion(断言)在软件开发中是一种常用的调试方式，很多开发语言中都支持这种机制。一般来说，assertion 用于保证程序最基本、关键的正确性。assertion 检查通常在开发和测试时开启。为了提高性能，在软件发布后， assertion 检查通常是关闭的。在实现中，断言是一个包含布尔表达式的语句，在执行这个语句时假定该表达式为 true；如果表达式计算为 false，那么系统会报告一个 AssertionError。
## goto
1. Java 有没有 goto  
goto 是 Java 中的保留字，在目前版本的 Java 中没有使用。（根据James Gosling（Java 之父）编写的《The Java Programming Language》一书的附录中给出了一个 Java 关键字列表，其中有 goto 和 const，但是这两个是目前无法使用的关键字，因此有些地方将其称之为保留字，其实保留字这个词应该有更广泛的意义，因为熟悉 C 语言的程序员都知道，在系统类库中使用过的有特殊意义的单词或单词的组合都被视为保留字）
## final, finally, finalize 
1. Java 中的 final关键字有哪些用法  
(1)修饰类：表示该类不能被继承；  
(2)修饰方法：表示方法不能被重写；  
(3)修饰变量：表示变量只能一次赋值以后值不能被修改（常量）。  
2. final, finally, finalize 的区别  
final：修饰符（关键字）有三种用法：如果一个类被声明为final，意味着它不能再派生出新的子类，即不能被继承，因此它和 abstract 是反义词。将变量声明为 final，可以保证它们在使用中不被改变，被声明为 final 的变量必须在声明时给定初值，而在以后的引用中只能读取不可修改。被声明为 final 的方法也同样只能使用，不能在子类中被重写。  
finally：通常放在 try…catch 的后面构造总是执行代码块，这就意味着程序无论正常执行还是发生异常，这里的代码只要 JVM 不关闭都能执行，可以将释放外部资源的代码写在 finally 块中。  
finalize：Object 类中定义的方法，Java 中允许使用 finalize() 方法在垃圾收集器将对象从内存中清除出去之前做必要的清理工作。这个方法是由垃圾收集器在销毁对象时调用的，通过重写finalize() 方法可以整理系统资源或者执行其他清理工作。

## link
http://wiki.jikexueyuan.com/project/java-interview-bible/platorm-memory.html

