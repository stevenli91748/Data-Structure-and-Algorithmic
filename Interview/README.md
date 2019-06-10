
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
<summary>基础类型(Primitives)与封装类型(Wrappers)的区别在哪里？</summary>
  

</details>

# 类型转换

# 数组

# 队列

# String

# Collections

# 有用的参考

* [数据结构面试](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Data%20Structure/interview.md)
* [算法面试](https://github.com/stevenli91748/Data-Structure-and-Algorithmic/blob/master/Algorithmic/interview.md)
