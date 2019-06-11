
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


<details>w
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


<details>
<summary>如何去小数四舍五入保留小数点后两位？</summary>

//使用银行家算法
BigDecimal i = d.multiply(r).setScale(2,RoundingMode.HALF_EVEN);

推荐使用BigDecimal ，并且采用setScale方法来设置精确度，同时使用RoundingMode.HALF_UP表示使用最近数字舍入法则来近似计算。在这里我们可以看出BigDecimal和四舍五入是绝妙的搭配。

* [java的四舍五入](https://www.cnblogs.com/chenssy/p/3366632.html)

</details>

<details>
<summary>char 型变量中能不能存贮一个中文汉字，为什么？</summary>

char型变量是用来存储Unicode编码的字符的，unicode编码字符集中包含了汉字，所以char型变量中当然可以存储汉字啦。不过，如果某个特殊的汉字没有被包含在unicode编码字符集中，那么，这个char型变量中就不能存储这个特殊汉字。

补充说明：unicode编码占用两个字节，所以，char类型的变量也是占用两个字节。

</details>


# 类型转换

<details>
<summary>怎样将 bytes 转换为 long 类型</summary>

```java
  
  public static long bytes2long(byte[] b) {
    long temp = 0;
    long res = 0;
    for (int i=0;i<8;i++) {
        res <<= 8;
        temp = b[i] & 0xff;
        res |= temp;
    }
    return res;
}

```

</details>

<details>
<summary>.怎么将 string 转成 byte</summary>

```java

string s = "Hello!!";
byte[] b = new byte[1024*1024];
b = System.Text.Encoding.ASCII.GetBytes(s);
//当string含有中文字符时用 System.Text.Encoding.UTF8.GetBytes(s);
sock.Send(b);

```
</details>

<details>
<summary>.怎么将 byte 转换为 String</summary>

```java

byte[] b1 = new byte[1024*1024*2];
sock.Receive(b1);
string s1 = System.Text.Encoding.ASCII.GetString(b1);

```

// System.Text.Encoding.UTF8.GetString(b1);



注意： 在把byte数组转换成string的时候，由于byte数组有2M的字节，所以转换后得到的字符串s1也会填充到2M的字符（用\0来填充）
所以，为了避免这个问题，可以使用Receive返回的字节数来确定接收到byte的长度

```java

int length = sock.Receive(b1);
string s1 = System.Text.Encoding.ASCII.GetString(b1, 0, length);
//这样，s1就为byte实际的值

```

</details>

<details>
<summary>如何将数值型字符转换为数字</summary>

**string和int之间的转换**

string转换成int : Integer.valueOf("12")

int转换成string : String.valueOf(12)

**char转int之间的转换**

首先将char转换成string

String str=String.valueOf('2')

Integer.valueof(str) 或者Integer.PaseInt(str)

Integer.valueof返回的是Integer对象，Integer.paseInt返回的是int

</details>

<details>
<summary>我们能将 int 强制转换为 byte 类型的变量吗？如果该值大于 byte 类型的范围，将会出现什么现象</summary>
  
**1. Byte转int**

```java

public static int bytes2int(byte[] bytes) {
        int num = bytes[0] & 0xFF;
        num |= ((bytes[1] << 8) & 0xFF00);
        num |= ((bytes[2] << 16) & 0xFF0000);
        num |= ((bytes[3] << 24) & 0xFF000000);
        return num;
}

```

**2. int转 byte**

```java

public static byte[] int2bytes(int i) {
        byte[] b = new byte[4];
        b[0] = (byte) (0xff&i);
        b[1] = (byte) ((0xff00&i) >> 8);
        b[2] = (byte) ((0xff0000&i) >> 16);
        b[3] = (byte) ((0xff000000&i) >> 24);
        return b;
}

```
  
</details>

<details>
<summary>能在不进行强制转换的情况下将一个 double 值赋值给 long 类型的变量吗?</summary>
  
```java

  public static void main(String[] args) {
    double d = 88.88;
    long l = Math.round(d);
    System.out.println(l);

    long ll = 100L;
    double dd = (double) ll;
    System.out.println(dd);
}

```

</details>


# 数组

<details>
<summary>如何权衡是使用无序的数组还是有序的数组</summary>

在数据偏向查找操作的时候用有序数组快一些，在数据偏向插入的时候，无序数组好一些。删除操作效率一样。
  
</details>  


<details>
  
<summary>怎么判断数组是 null 还是为空</summary>

（无论使用哪种类型的数组，数组标识符其实只是一个引用，指向在堆中创建的一个真实对象 Int[] A =new int[10];new 一下就是实例化了，开辟了内存空间，基本数据类型的元素会被赋初始值，数组建立后长度不能改变，但是还是可以重新赋值）

有如下两个变量定义：

1 int[] zero = new int[0];

2 int[] nil = null;

这两种定义有什么区别呢？

zero是一个长度为0的数组，我们称之为“空数组”，空数组也是一个对象，只是包含元素个数为0。nil是一个数组类型的空引用。
  
</details>  

<details>
<summary>Array 和 ArrayList有什么区别？什么时候应该使用Array而不是ArrayList?</summary>

1）精辟阐述：

可以将 ArrayList想象成一种“会自动扩增容量的Array”。

2）Array（[]）：最高效；但是其容量固定且无法动态改变；

ArrayList： 容量可动态增长；但牺牲效率；

3）建议：
基于效率和类型检验，应尽可能使用Array，无法确定数组大小时才使用ArrayList！

不过当你试着解决更一般化的问题时，Array的功能就可能过于受限。

4）Java中一切皆对象，Array也是对象。不论你所使用得Array型别为何，Array名称本身实际上是个reference，指向heap之内得某个实际对象。这个对象可经
由“Array初始化语法”被自动产生，也可以以new表达式手动产生。

5）Array可做为函数返回值，因为它本身是对象的reference；

6）对象数组与基本类型数组在运用上几乎一模一样，唯一差别在于，前者持有得是reference，后者直接持有基本型别之值；

例如：

```java
string [] staff=new string[100];
int [] num=new int[10];

```

7）容器所持有的其实是一个reference指向Object，进而才能存储任意型别。当然这不包括基本型别，因为基本型别并不继承自任何classes。

8）面对Array，我们可以直接持有基本型别数值的Array（例如：int [] num;),也可以持有reference（指向对象）的Array；但是容器类仅能持有reference（指向对象），若要将基本型别置于容器内，需要使用wrapper类。但是wrapper类使用起来可能不很容易上手，此外，primitives Array的效率比起“容纳基本型别之外覆类（的reference）”的容器好太多了。

当然，如果你的操作对象是基本型别，而且需要在空间不足时自动扩增容量，Array便不适合，此时就得使用外覆类的容器了。

9）某些情况下，容器类即使没有转型至原来的型别，仍然可以运作无误。有一种情况尤其特别：编译器对String class提供了一些额外的支持，使它可以平滑运作。

10）对数组的一些基本操作，像排序、搜索与比较等是很常见的。因此在Java中提供了Arrays类协助这几个操作

sort(),binarySearch(),equals(),fill(),asList().

不过Arrays类没有提供删除方法，而ArrayList中有remove()方法，不知道是否是不需要在Array中做删除等操作的原因（因为此时应该使用链表）。

11）ArrayList的使用也很简单：产生ArrayList，利用add()将对象置入，利用get(i）配合索引值将它们取出。这一切就和Array的使用方式完全相同，只不过少了[]而已。

换一种简单说法：

1）效率：

数组扩容是对ArrayList效率影响比较大的一个因素。

每当执行Add、AddRange、Insert、InsertRange等添加元素的方法，都会检查内部数组的容量是否不够了，如果是，它就会以当前容量的两倍来重新构建一个数组，将旧元素Copy到新数组中，然后丢弃旧数组，在这个临界点的扩容操作，应该来说是比较影响效率的。

ArrayList是Array的复杂版本

ArrayList内部封装了一个Object类型的数组，从一般的意义来说，它和数组没有本质的差别，甚至于ArrayList的许多方法，如Index、IndexOf、Contains、Sort等都是在内部数组的基础上直接调用Array的对应方法。

2）类型识别：

ArrayList存入对象时，抛弃类型信息，所有对象屏蔽为Object，编译时不检查类型，但是运行时会报错。但是现在有jdk1.5后引入泛型来进行编译检查类型，如错存入了不同类型会直接报错。

ArrayList与数组的区别主要就是由于动态增容的效率问题了

3）ArrayList可以存任何Object，如String等。
  
</details>  

<details>
<summary>数组和链表数据结构描述，各自的时间复杂度</summary>
  
 数组是将元素在内存中连续存放，由于每个元素占用内存相同，可以通过下标迅速访问数组中任何元素。但是如果要在数组中增加一个元素，需要移动大量元素，在内存中空出一个元素的空间，然后将要增加的元素放在其中。同样的道理，如果想删除一个元素，同样需要移动大量元素去填掉被移动的元素。如果应用需要快速访问数据，很少插入和删除元素，就应该用数组。
 
链表中的元素在内存中不是顺序存储的，而是通过存在元素中的指针联系到一起，每个结点包括两个部分：一个是存储 数据元素的数据域，另一个是存储下一个结点地址的 指针。 如果要访问链表中一个元素，需要从第一个元素开始，一直找到需要的元素位置。但是增加和删除一个元素对于链表数据结构就非常简单了，只要修改元素中的指针就可以了。如果应用需要经常插入和删除元素你就需要用链表。


内存存储区别

数组从栈中分配空间, 对于程序员方便快速,但自由度小。链表从堆中分配空间, 自由度大但申请管理比较麻烦.　

逻辑结构区别

数组必须事先定义固定的长度（元素个数），不能适应数据动态地增减的情况。当数据增加时，可能超出原先定义的元素个数；当数据减少时，造成内存浪费。　

链表动态地进行存储分配，可以适应数据动态地增减的情况，且可以方便地插入、删除数据项。（数组中插入、删除数据项时，需要移动其它数据项）　

总结
1、存取方式上，数组可以顺序存取或者随机存取，而链表只能顺序存取；　

2、存储位置上，数组逻辑上相邻的元素在物理存储位置上也相邻，而链表不一定；　

3、存储空间上，链表由于带有指针域，存储密度不如数组大；　

4、按序号查找时，数组可以随机访问，时间复杂度为O(1)，而链表不支持随机访问，平均需要O(n)；　

5、按值查找时，若数组无序，数组和链表时间复杂度均为O(1)，但是当数组有序时，可以采用折半查找将时间复杂度降为O(logn)；　

6、插入和删除时，数组平均需要移动n/2个元素，而链表只需修改指针即可；　

7、空间分配方面：

数组在静态存储分配情形下，存储元素数量受限制，动态存储分配情形下，虽然存储空间可以扩充，但需要移动大量元素，导致操作效率降低，而且如果内存中没有更大块连续存储空间将导致分配失败；

链表存储的节点空间只在需要的时候申请分配，只要内存中有空间就可以分配，操作比较灵活高效；

数组有没有length()这个方法? String有没有length()这个方法 
  
</details>    

<details>
<summary>为什麽数组从栈中分配空间？</summary>

* [数组是分配在栈中的](https://blog.csdn.net/lcl19970203/article/details/54428358)

</details>   

# 队列

<details>
<summary>队列和栈是什么，列出它们的区别</summary>

队列（Queue）：是限定只能在表的一端进行插入和在另一端进行删除操作的线性表；

栈（Stack）：是限定只能在表的一端进行插入和删除操作的线性表。

区别如下：

**规则不同**

1. 队列：先进先出（First In First Out）FIFO

2. 栈：先进后出（First In Last Out ）FILO

**对插入和删除操作的限定不同**

1. 队列：只能在表的一端进行插入，并在表的另一端进行删除；

2. 栈：只能在表的一端插入和删除。

**遍历数据速度不同**

1. 队列：基于地址指针进行遍历，而且可以从头部或者尾部进行遍历，但不能同时遍历，无需开辟空间，因为在遍历的过程中不影响数据结构，所以遍历速度要快；

2. 栈：只能从顶部取数据，也就是说最先进入栈底的，需要遍历整个栈才能取出来，而且在遍历数据的同时需要为数据开辟临时空间，保持数据在遍历前的一致性

</details>   

<details>
<summary>BlockingQueue是什么</summary>
  
阻塞队列（BlockingQueue）是一个支持两个附加操作的队列。这两个附加的操作是：在队列为空时，获取元素的线程会等待队列变为非空。当队列满时，存储元素的线程会等待队列可用。阻塞队列常用于生产者和消费者的场景，生产者是往队列里添加元素的线程，消费者是从队列里拿元素的线程。阻塞队列就是生产者存放元素的容器，而消费者也只从容器里拿元素。

* [Java中的阻塞队列](http://www.importnew.com/17537.html)

</details>   


<details>
<summary>Java里的7种阻塞队列是什么</summary>
  
JDK7提供了7个阻塞队列。分别是

1. ArrayBlockingQueue ：一个由数组结构组成的有界阻塞队列。

2. LinkedBlockingQueue ：一个由链表结构组成的有界阻塞队列。

3. PriorityBlockingQueue ：一个支持优先级排序的无界阻塞队列。

4. DelayQueue：一个使用优先级队列实现的无界阻塞队列。

5. SynchronousQueue：一个不存储元素的阻塞队列。

6. LinkedTransferQueue：一个由链表结构组成的无界阻塞队列。

7. LinkedBlockingDeque：一个由链表结构组成的双向阻塞队列。

**ArrayBlockingQueue**

ArrayBlockingQueue是一个用数组实现的有界阻塞队列。此队列按照先进先出（FIFO）的原则对元素进行排序。默认情况下不保证访问者公平的访问队列，所谓公平访问队列是指阻塞的所有生产者线程或消费者线程，当队列可用时，可以按照阻塞的先后顺序访问队列，即先阻塞的生产者线程，可以先往队列里插入元素，先阻塞的消费者线程，可以先从队列里获取元素。通常情况下为了保证公平性会降低吞吐量。我们可以使用以下代码创建一个公平的阻塞队列：

1
ArrayBlockingQueue fairQueue = new  ArrayBlockingQueue(1000,true);
访问者的公平性是使用可重入锁实现的，代码如下：

```java
public ArrayBlockingQueue(int capacity, boolean fair) {
        if (capacity <= 0)
            throw new IllegalArgumentException();
        this.items = new Object[capacity];
        lock = new ReentrantLock(fair);
        notEmpty = lock.newCondition();
        notFull =  lock.newCondition();
}

```

**LinkedBlockingQueue**

LinkedBlockingQueue是一个用链表实现的有界阻塞队列。此队列的默认和最大长度为Integer.MAX_VALUE。此队列按照先进先出的原则对元素进行排序。

**PriorityBlockingQueue**

PriorityBlockingQueue是一个支持优先级的无界队列。默认情况下元素采取自然顺序排列，也可以通过比较器comparator来指定元素的排序规则。元素按照升序排列。

**DelayQueue**

DelayQueue是一个支持延时获取元素的无界阻塞队列。队列使用PriorityQueue来实现。队列中的元素必须实现Delayed接口，在创建元素时可以指定多久才能从队列中获取当前元素。只有在延迟期满时才能从队列中提取元素。我们可以将DelayQueue运用在以下应用场景：

缓存系统的设计：可以用DelayQueue保存缓存元素的有效期，使用一个线程循环查询DelayQueue，一旦能从DelayQueue中获取元素时，表示缓存有效期到了。
定时任务调度。使用DelayQueue保存当天将会执行的任务和执行时间，一旦从DelayQueue中获取到任务就开始执行，从比如TimerQueue就是使用DelayQueue实现的。
队列中的Delayed必须实现compareTo来指定元素的顺序。比如让延时时间最长的放在队列的末尾。实现代码如下：

```java

public int compareTo(Delayed other) {
           if (other == this) // compare zero ONLY if same object
                return 0;
            if (other instanceof ScheduledFutureTask) {
                ScheduledFutureTask x = (ScheduledFutureTask)other;
                long diff = time - x.time;
                if (diff < 0)
                    return -1;
                else if (diff > 0)
                    return 1;
       else if (sequenceNumber < x.sequenceNumber)
                    return -1;
                else
                    return 1;
            }
            long d = (getDelay(TimeUnit.NANOSECONDS) -
                      other.getDelay(TimeUnit.NANOSECONDS));
            return (d == 0) ? 0 : ((d < 0) ? -1 : 1);
        }

```

**如何实现Delayed接口**

我们可以参考ScheduledThreadPoolExecutor里ScheduledFutureTask类。这个类实现了Delayed接口。首先：在对象创建的时候，使用time记录前对象什么时候可以使用，代码如下：

```java

ScheduledFutureTask(Runnable r, V result, long ns, long period) {
            super(r, result);
            this.time = ns;
            this.period = period;
            this.sequenceNumber = sequencer.getAndIncrement();
}

```

然后使用getDelay可以查询当前元素还需要延时多久，代码如下：

```java

public long getDelay(TimeUnit unit) {
            return unit.convert(time - now(), TimeUnit.NANOSECONDS);
        }

```

通过构造函数可以看出延迟时间参数ns的单位是纳秒，自己设计的时候最好使用纳秒，因为getDelay时可以指定任意单位，一旦以纳秒作为单位，而延时的时间又精确不到纳秒就麻烦了。使用时请注意当time小于当前时间时，getDelay会返回负数。

***如何实现延时队列***

延时队列的实现很简单，当消费者从队列里获取元素时，如果元素没有达到延时时间，就阻塞当前线程。

```java

long delay = first.getDelay(TimeUnit.NANOSECONDS);
                    if (delay <= 0)
                        return q.poll();
                    else if (leader != null)
                        available.await();
                        
```

**SynchronousQueue**

SynchronousQueue是一个不存储元素的阻塞队列。每一个put操作必须等待一个take操作，否则不能继续添加元素。SynchronousQueue可以看成是一个传球手，负责把生产者线程处理的数据直接传递给消费者线程。队列本身并不存储任何元素，非常适合于传递性场景,比如在一个线程中使用的数据，传递给另外一个线程使用，SynchronousQueue的吞吐量高于LinkedBlockingQueue 和 ArrayBlockingQueue。

**LinkedTransferQueue**

LinkedTransferQueue是一个由链表结构组成的无界阻塞TransferQueue队列。相对于其他阻塞队列LinkedTransferQueue多了tryTransfer和transfer方法。

transfer方法。如果当前有消费者正在等待接收元素（消费者使用take()方法或带时间限制的poll()方法时），transfer方法可以把生产者传入的元素立刻transfer（传输）给消费者。如果没有消费者在等待接收元素，transfer方法会将元素存放在队列的tail节点，并等到该元素被消费者消费了才返回。transfer方法的关键代码如下：

```java

Node pred = tryAppend(s, haveData);
return awaitMatch(s, pred, e, (how == TIMED), nanos);

```

第一行代码是试图把存放当前元素的s节点作为tail节点。第二行代码是让CPU自旋等待消费者消费元素。因为自旋会消耗CPU，所以自旋一定的次数后使用Thread.yield()方法来暂停当前正在执行的线程，并执行其他线程。

tryTransfer方法。则是用来试探下生产者传入的元素是否能直接传给消费者。如果没有消费者等待接收元素，则返回false。和transfer方法的区别是tryTransfer方法无论消费者是否接收，方法立即返回。而transfer方法是必须等到消费者消费了才返回。

对于带有时间限制的tryTransfer(E e, long timeout, TimeUnit unit)方法，则是试图把生产者传入的元素直接传给消费者，但是如果没有消费者消费该元素则等待指定的时间再返回，如果超时还没消费元素，则返回false，如果在超时时间内消费了元素，则返回true。

**LinkedBlockingDeque**

LinkedBlockingDeque是一个由链表结构组成的双向阻塞队列。所谓双向队列指的你可以从队列的两端插入和移出元素。双端队列因为多了一个操作队列的入口，在多线程同时入队时，也就减少了一半的竞争。相比其他的阻塞队列，LinkedBlockingDeque多了addFirst，addLast，offerFirst，offerLast，peekFirst，peekLast等方法，以First单词结尾的方法，表示插入，获取（peek）或移除双端队列的第一个元素。以Last单词结尾的方法，表示插入，获取或移除双端队列的最后一个元素。另外插入方法add等同于addLast，移除方法remove等效于removeFirst。但是take方法却等同于takeFirst，不知道是不是Jdk的bug，使用时还是用带有First和Last后缀的方法更清楚。在初始化LinkedBlockingDeque时可以初始化队列的容量，用来防止其再扩容时过渡膨胀。另外双向阻塞队列可以运用在“工作窃取”模式中。

</details>   

<details>
<summary>阻塞队列的实现原理</summary>
  
  如果队列是空的，消费者会一直等待，当生产者添加元素时候，消费者是如何知道当前队列有元素的呢？如果让你来设计阻塞队列你会如何设计，让生产者和消费者能够高效率的进行通讯呢？让我们先来看看JDK是如何实现的。

使用通知模式实现。所谓通知模式，就是当生产者往满的队列里添加元素时会阻塞住生产者，当消费者消费了一个队列中的元素后，会通知生产者当前队列可用。通过查看JDK源码发现ArrayBlockingQueue使用了Condition来实现，代码如下：

```java

private final Condition notFull;
private final Condition notEmpty;
 
public ArrayBlockingQueue(int capacity, boolean fair) {
        //省略其他代码
        notEmpty = lock.newCondition();
        notFull =  lock.newCondition();
    }
 
public void put(E e) throws InterruptedException {
        checkNotNull(e);
        final ReentrantLock lock = this.lock;
        lock.lockInterruptibly();
        try {
            while (count == items.length)
                notFull.await();
            insert(e);
        } finally {
            lock.unlock();
        }
}
 
public E take() throws InterruptedException {
        final ReentrantLock lock = this.lock;
        lock.lockInterruptibly();
        try {
            while (count == 0)
                notEmpty.await();
            return extract();
  } finally {
            lock.unlock();
        }
}
 
private void insert(E x) {
        items[putIndex] = x;
        putIndex = inc(putIndex);
        ++count;
        notEmpty.signal();
    }
    
```

当我们往队列里插入一个元素时，如果队列不可用，阻塞生产者主要通过LockSupport.park(this);来实现

```java

public final void await() throws InterruptedException {
            if (Thread.interrupted())
                throw new InterruptedException();
            Node node = addConditionWaiter();
            int savedState = fullyRelease(node);
            int interruptMode = 0;
            while (!isOnSyncQueue(node)) {
                LockSupport.park(this);
                if ((interruptMode = checkInterruptWhileWaiting(node)) != 0)
                    break;
            }
            if (acquireQueued(node, savedState) && interruptMode != THROW_IE)
                interruptMode = REINTERRUPT;
            if (node.nextWaiter != null) // clean up if cancelled
                unlinkCancelledWaiters();
            if (interruptMode != 0)
 
reportInterruptAfterWait(interruptMode);
        }

```

继续进入源码，发现调用setBlocker先保存下将要阻塞的线程，然后调用unsafe.park阻塞当前线程。

```java

public static void park(Object blocker) {
        Thread t = Thread.currentThread();
        setBlocker(t, blocker);
        unsafe.park(false, 0L);
        setBlocker(t, null);
    }
    
```

unsafe.park是个native方法，代码如下：

1
public native void park(boolean isAbsolute, long time);
park这个方法会阻塞当前线程，只有以下四种情况中的一种发生时，该方法才会返回。

与park对应的unpark执行或已经执行时。注意：已经执行是指unpark先执行，然后再执行的park。
线程被中断时。
如果参数中的time不是零，等待了指定的毫秒数时。
发生异常现象时。这些异常事先无法确定。
我们继续看一下JVM是如何实现park方法的，park在不同的操作系统使用不同的方式实现，在linux下是使用的是系统方法pthread_cond_wait实现。实现代码在JVM源码路径src/os/linux/vm/os_linux.cpp里的 os::PlatformEvent::park方法，代码如下：

```java

void os::PlatformEvent::park() {
             int v ;
         for (;;) {
        v = _Event ;
         if (Atomic::cmpxchg (v-1, &_Event, v) == v) break ;
         }
         guarantee (v >= 0, "invariant") ;
         if (v == 0) {
         // Do this the hard way by blocking ...
         int status = pthread_mutex_lock(_mutex);
         assert_status(status == 0, status, "mutex_lock");
         guarantee (_nParked == 0, "invariant") ;
         ++ _nParked ;
         while (_Event < 0) {
         status = pthread_cond_wait(_cond, _mutex);
         // for some reason, under 2.7 lwp_cond_wait() may return ETIME ...
         // Treat this the same as if the wait was interrupted
         if (status == ETIME) { status = EINTR; }
         assert_status(status == 0 || status == EINTR, status, "cond_wait");
         }
         -- _nParked ;
 
         // In theory we could move the ST of 0 into _Event past the unlock(),
         // but then we'd need a MEMBAR after the ST.
         _Event = 0 ;
         status = pthread_mutex_unlock(_mutex);
         assert_status(status == 0, status, "mutex_unlock");
         }
         guarantee (_Event >= 0, "invariant") ;
         }
 
     }
     
```

pthread_cond_wait是一个多线程的条件变量函数，cond是condition的缩写，字面意思可以理解为线程在等待一个条件发生，这个条件是一个全局变量。这个方法接收两个参数，一个共享变量_cond，一个互斥量_mutex。而unpark方法在linux下是使用pthread_cond_signal实现的。park 在windows下则是使用WaitForSingleObject实现的。

当队列满时，生产者往阻塞队列里插入一个元素，生产者线程会进入WAITING (parking)状态。我们可以使用jstack dump阻塞的生产者线程看到这点：

```java
"main" prio=5 tid=0x00007fc83c000000 nid=0x10164e000 waiting on condition [0x000000010164d000]
   java.lang.Thread.State: WAITING (parking)
        at sun.misc.Unsafe.park(Native Method)
        - parking to wait for  <0x0000000140559fe8> (a java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject)
        at java.util.concurrent.locks.LockSupport.park(LockSupport.java:186)
        at java.util.concurrent.locks.AbstractQueuedSynchronizer$ConditionObject.await(AbstractQueuedSynchronizer.java:2043)
        at java.util.concurrent.ArrayBlockingQueue.put(ArrayBlockingQueue.java:324)
        at blockingqueue.ArrayBlockingQueueTest.main(ArrayBlockingQueueTest.java:11)
        
```

</details> 

<details>
<summary>简述 ConcurrentLinkedQueue LinkedBlockingQueue 的用处和不同之处</summary>
  
**阻塞队列：线程安全**

按 FIFO（先进先出）排序元素。队列的头部是在队列中时间最长的元素。队列的尾部是在队列中时间最短的元素。新元素插入到队列的尾部，并且队列检索操作会获得位于队列头部的元素。链接队列的吞吐量通常要高于基于数组的队列，但是在大多数并发应用程序中，其可预知的性能要低。

注意：

1、必须要使用take()方法在获取的时候达成阻塞结果

2、使用poll()方法将产生非阻塞效果

**非阻塞队列**

基于链接节点的、无界的、线程安全。此队列按照 FIFO（先进先出）原则对元素进行排序。队列的头部 是队列中时间最长的元素。队列的尾部 是队列中时间最短的元素。新的元素插入到队列的尾部，队列检索操作从队列头部获得元素。当许多线程共享访问一个公共 collection 时，ConcurrentLinkedQueue是一个恰当的选择。此队列不允许 null 元素。

在并发编程中，一般推荐使用阻塞队列，这样实现可以尽量地避免程序出现意外的错误。阻塞队列使用最经典的场景就是socket客户端数据的读取和解析，读取数据的线程不断将数据放入队列，然后解析线程不断从队列取数据解析。还有其他类似的场景，只要符合生产者-消费者模型的都可以使用阻塞队列。

使用非阻塞队列，虽然能即时返回结果（消费结果），但必须自行编码解决返回为空的情况处理（以及消费重试等问题）。另外他们都是线程安全的，不用考虑线程同步问题。

* [《JAVA阻塞队列以及非阻塞队列的区别》](https://www.cnblogs.com/starcrm/p/4998067.html)
  
</details>   

<details>
<summary>ArrayList、Vector、LinkedList的存储性能和特性</summary>

ArrayList 和Vector他们底层的实现都是一样的，都是使用数组方式存储数据，此数组元素数大于实际存储的数据以便增加和插入元素，它们都允许直接按序号索引元素，但是插入元素要涉及数组元素移动等内存操作，所以索引数据快而插入数据慢。

Vector中的方法由于添加了synchronized修饰，因此Vector是线程安全的容器，但性能上较ArrayList差，因此已经是Java中的遗留容器。

LinkedList使用双向链表实现存储（将内存中零散的内存单元通过附加的引用关联起来，形成一个可以按序号索引的线性结构，这种链式存储方式与数组的连续存储方式相比，内存的利用率更高），按序号索引数据需要进行前向或后向遍历，但是插入数据时只需要记录本项的前后项即可，所以插入速度较快。

Vector属于遗留容器（Java早期的版本中提供的容器，除此之外，Hashtable、Dictionary、BitSet、Stack、Properties都是遗留容器），已经不推荐使用，但是由于ArrayList和LinkedListed都是非线程安全的，如果遇到多个线程操作同一个容器的场景，则可以通过工具类Collections中的synchronized List方法将其转换成线程安全的容器后再使用（这是对装潢模式的应用，将已有对象传入另一个类的构造器中创建新的对象来增强实现）。

</details>   


# String

<details>
<summary>ByteBuffer 与 StringBuffer有什么区别</summary>


</details>   


# Collections

<details>
<summary>介绍Java中的Collection FrameWork。集合类框架的基本接口有哪些？</summary>

总共有两大接口：Collection 和Map ，一个元素集合，一个是键值对集合；

其中List和Set接口继承了Collection接口，一个是有序元素集合，一个是无序元素集合；

ArrayList和LinkedList实现了List接口，HashSet实现了Set接口，这几个都比较常用；

HashMap和HashTable实现了Map接口，并且HashTable是线程安全的，但是HashMap性能更好；

</details>   

<details>
<summary>集合类框架的最佳实践有哪些</summary>

根据应用的需要合理的选择集合的类型对性能非常重要

假如元素的大小是固定的，而且能事先知道，我们就该用Array而不是ArrayList.

有些集合类允许指定初始容量。因此，如果我们能估计出存储元素的数目，我们可以设置初始容量来避免重新计算hash值或者扩容.

为了类型安全，可读性和健壮性的原因总要使用翻新。同时，使用泛型还能皮面运行时的ClassCastException.

使用JDK提供的不变类（immutable class）作为Map的键可以避免为我们自己的类实现hashCode()和equals()方法。

编程的时候接口优于实现。

底层的集合实际上是空的情况下返回长度是0的集合或者是数组，不要返回null.

</details>   

<details>
<summary>为什么 Collection 不从 Cloneable 和 Serializable 接口继承?</summary>

Collection接口指定一组对象，对象即为它的元素。如何维护这些元素由Collection的具体实现决定。例如，一些如List的Collection实现允许重复的元素，而其它的如Set就不允许。很多Collection实现有一个公有的clone方法。然而，把它放到集合的所有实现中也是没有意义的。这是因为Collection是一个抽象表现。

重要的是实现，克隆（cloning）或者序列化（serialization）的语义和含义是跟具体的实现相关的。**因此应该由集合类的具体实现类来决定如何被克隆或者序列化。**

</details>   

<details>
<summary>说出几点 Java 中使用 Collections 的最佳实践？</summary>

）使用正确的集合类，例如，如果不需要同步列表，使用 ArrayList 而不是 Vector。

b）优先使用并发集合，而不是对集合进行同步。并发集合提供更好的可扩展性。

c）使用接口代表和访问集合，如使用List存储 ArrayList，使用 Map 存储 HashMap 等等。

d）使用迭代器来循环集合。

e）使用集合的时候使用泛型

</details>   

# 有用的参考

* [数据结构面试](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Data%20Structure/interview.md)
* [算法面试](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Algorithmic/interview.md)
