
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

# 队列

# String

# Collections

# 有用的参考

* [数据结构面试](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Data%20Structure/interview.md)
* [算法面试](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Algorithmic/interview.md)
