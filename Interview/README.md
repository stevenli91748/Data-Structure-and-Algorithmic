
# 基础类型(Primitives)

<details>
<summary>基础类型(Primitives)与封装类型(Wrappers)的区别在哪里？</summary>

1 传递方式不同

封装类是引用类型。基本类型（原始数据类型）在传递参数时都是按值传递，而封装类型是按引用传递的(其实“引用也是按值传递的”，传递的是对象的地址)。由于包装类型都是final修饰的不可变量，因此没有提供改变它值的方法，增加了对“按引用传递”的理解难度。
int是基本类型，直接存放数值；Integer是类，产生对象时用一个引用指向这个对象。

2 封装类可以有方法和属性

封装类可以有方法和属性，利用这些方法和属性来处理数据，如Integer.parseInt(Strings)。基本数据类型都是final修饰的，不能继承扩展新的类、新的方法。

3 默认值不同

基本类型跟封装类型的默认值是不一样的。如int i,i的预设为0；Integer j，j的预设为null,因为封装类产生的是对象，对象默认值为null。

4 存储位置

基本类型在内存中是存储在栈中，引用类型的引用（值的地址）存储在栈中，而实际的对象（值）是存在堆中。
基本数据类型的好处就是速度快（不涉及到对象的构造和回收），封装类的目的主要是更好的处理数据之间的转换。JDK5.0开始可以自动封包了，基本数据类型可以自动封装成封装类。

* [基础类型(Primitives)与封装类型(Wrappers)的区别](https://blog.csdn.net/xzp_12345/article/details/79038251)

</details>

<details>
<summary>简述九种基本数据类型的大小，以及他们的封装类。</summary>
  

</details>


<details>
<summary>int和 Integer 哪个会占用更多的内存？int和 Integer 有什么区别？parseInt()函数在什么时候使用到？</summary>
  
当然是Integer会占用更多的内存。以下为int和Integer的区别：

1、Integer是int的包装类，int则是java的一种基本数据类型

2、Integer变量必须实例化后才能使用，而int变量不需要

3、Integer实际是对象的引用，当new一个Integer时，实际上是生成一个指针指向此对象；而int则是直接存储数据值

4、Integer的默认值是null，int的默认值是0

延伸关于Integer和int的比较 ：

由于Integer变量实际上是对一个Integer对象的引用，所以两个通过new生成的Integer变量永远是不相等的（因为new生成的是两个对象，其内存地址不同）。

```java

Integer i = new Integer(100);
Integer j = new Integer(100);
System.out.print(i == j); //false

```

Integer变量和int变量比较时，只要两个变量的值是向等的，则结果为true（因为包装类Integer和基本数据类型int比较时，java会自动拆包装为int，然后进行比较，实际上就变为两个int变量的比较）

```java

Integer i = new Integer(100);
int j = 100；
System.out.print(i == j); //true

```

非new生成的Integer变量和new Integer()生成的变量比较时，结果为false。（因为非new生成的Integer变量指向的是java常量池中的对象，而new Integer()生成的变量指向堆中新建的对象，两者在内存中的地址不同）

```java
Integer i = new Integer(100);
Integer j = 100;
System.out.print(i == j); //false

```

对于两个非new生成的Integer对象，进行比较时，如果两个变量的值在区间-128到127之间，则比较结果为true，如果两个变量的值不在此区间，则比较结果为false

```java

Integer i = 100;
Integer j = 100;
System.out.print(i == j); //true
Integer i = 128;
Integer j = 128;
System.out.print(i == j); //false

```

对于第4条的原因：
java在编译Integer i = 100 ;时，会翻译成为Integer i = Integer.valueOf(100)；，而java API中对Integer类型的valueOf的定义如下：

```java

public static Integer valueOf(int i){
    assert IntegerCache.high >= 127;
    if (i >= IntegerCache.low && i <= IntegerCache.high){
        return IntegerCache.cache[i + (-IntegerCache.low)];
    }
    return new Integer(i);
}

```

java对于-128到127之间的数，会进行缓存，Integer i = 127时，会将127进行缓存，下次再写Integer j = 127时，就会直接从缓存中取，就不会new了。



parseInt()
parseInt()将把该字符之前的字符串转换成数字。parseInt()方法还有基模式，可以把二进制、八进制、十六进制或其他任何进制的字符串转换成整数。基是由parseInt()方法的第二个参数指定的，所以要解析十六进制的值，当然，对二进制、八进制，甚至十进制（默认模式），都可以这样调用parseInt()方法。
如果十进制数包含前导0，那么最好采用基数10，这样才不会意外地得到八进制的值。

```java

static int parseInt(String s)
static int parseInt(String s, int radix)

```

 * [int和Integer的区别](https://www.cnblogs.com/guodongdidi/p/6953217.html)
 
</details>

# 类型转换

# 数组

# 队列

# String

# Collections

# 有用的参考

* [数据结构面试](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Data%20Structure/interview.md)
* [算法面试](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Algorithmic/interview.md)
