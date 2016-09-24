###Java 基础知识点
可以用几段话说明清楚的Java基础知识点，没有特别的分类，以下进行逐条描述。

--
  
**基本数据类型**

| 基本数据类型    | 大小           | 对应封装类型   |
| --------------|:-------------:|:------------:|
| int           | 4字节          | Integer      |
| double        | 8字节          | Double       |
| long          | 8字节          | Long         |
| float         | 4字节          | Float        |
| short         | 2字节          | Short        |
| byte          | 1字节          | Byte         |
| character     | 2字节          | Character    |
| boolean       | 1比特          | Boolean      |

--

**try catch finally语法里，try里有return，finally还执行么？**

会执行，在方法返回调用者前执行。Java允许在finally中改变返回值的做法是不好的，因为如果存在finally代码块，try中的return语句不会立马返回调用者，而是记录下返回值待finally代码块执行完毕之后再向调用者返回其值，然后如果在finally中修改了返回值，这会对程序造成很大的困扰，C#中就从语法规定不能做这样的事。

--

**String、StringBuffer、StringBuild的区别**

（1）String是对象不是基本数据类型。String是final类，不能被继承，是不可变对象，一旦创建，就不能改变它的值。
对于已经存在的String对象，修改它的值，就是重新创建一个对象，然后将新值赋予这个对象。

（2）StringBuffer类似于String的字符串缓冲区，对它的修改不会像String那样重新创建对象。使用append()方法修改StringBuffer的值，使用toString()方法转换为字符串。

（3）StringBuild是线程非安全的，不执行线程同步所以比StringBuffer的速度快，效率高。