**摘要**：

Scala语言的名称来自于可伸展的语言，之所以这样命名，是因为他被设计成可以随着使用者的需求而扩展，Scala的应用范围很广，从编写简单脚本，到建立大型系统。它运行在标准的Java平台上，可以与所有的Java库无缝交互，它可以用于建立大型系统或可重用控件的架构。

从技术层面上来说，Scala是一种把面向对象和函数式编程理念加入到静态类型语言中的混合体。在可伸展性方面，这两种编程风格具有互补的力量，Scala的函数式编程简化了用简单部件搭建实际应用的过程，它的面向对象特性又使他便于构造大型系统并使她们适应新的需求。Scala中的着两种风格的组合使得表达新的编程模式和性的组件抽象成为可能。

**在Scala中，函数就是对象，函数类型是能够被子类继承的类。它从深层次影响了可扩展性。每个值都是对象，每个操作都是方法调用。方法名可以用像操作符一样的名字定义。**

原则上，面向对象编程的动机非常简单：绝大多数的程序都需要某种结构，而最直接的方法就是把数据和操作放入某种形式的容器中。面向对象编程里最伟大的思想就是让这些容器完全的通用化，这样就能够像保存数据一样保存操作，并且还可以把这些容器作为值存储在其他的容器中，或者作为参数传递给操作。这种方法可以让你的对象与完整的计算机有同样的架构原则：用形式化的接口绑定数据和操作。

**说到组装对象，Scala比别的语言更胜一筹，Scala的特质（trait）就是其中一例。特质就像Java的接口，但可以有方法实现及字段。可以通过混入组装构造对象，从而带有了类的成员并加入了若个特质的成员，这样的构造方式，可以让不同用途的类包装不同的特质，这看上去有点像多重继承，但是细节上有差异，与类不同，特质可以把一些新的功能加入到一些还未定义的超类中，这使得特质比类更具有可加性，尤为重要的时，它可以避免多重继承中通过不同继承渠道继承相同类时发生的经典的菱形继承问题。**

函数式编程的两大理念：

1. **函数是头等值，与整数或者字符串处于同一地位。**
2. **程序的操作应该把输入值映射为输出值而不应该就地修改数据。**另一种解释是：方法不应该有任何的副作用（side effect）。方法与其所在环境的唯一交流方式应该是获得参数和返回结果。**函数式语言鼓励使用不可变数据结构和指称透明的方法。**

为什么使用Scala：

1. 兼容性，完美兼容Java
2. 简洁，既方便阅读，又可以减少代码量。
3. 高层抽象，Scala通过帮助提升接口的抽象级别来帮助管理复杂性。
4. **高级的静态类型化**。静态类型系统可以根据保存和计算的值的类型认定变量和表达式类型。Scala以Java的内嵌类型系统为基础，允许使用泛型参数化类型，用交集组合类型及抽象类型隐藏类型细节。它很好的诠释了两个静态类型问题的解决之道： **通过类型推断避免了冗余性以及通过模式匹配和一些新的编写和组织类型的方法获得了灵活性。**把这些绊脚石搬掉后，静态类型系统的经典优越性就体现的更为明显。其**中最重要的包括程序抽象的可检验属性，安全的重构，以及更好的文档。**
   - 可检验属性：静态类型系统可以保证消除某些运行时的错误。
   - 安全的重构：静态类型系统让你可以非常有信心的去改变代码基础的安全网。
   - 文档：静态类型是被编译器检查过正确性的程序文档。不像普通的注释，类型标注永远都不会过期，更进一步说，编译器和继承开发环境可以利用类型标注提供更好的上下文帮助。举例来说，集成开发环境可以通过判定选中表达式的静态类型，找到类型的所有成员，并全部显示出来。Scala中的类型推断程序经常看上去有点像是动态类型脚本写的。



scala中的分号推断规则（Scala中分号不是必须的，编译器会自动推断是否是一条语句），概括地说，除非一下任何一条为true，代码行的末尾就会被当作分号处理：

1. 当前行以一个不能作为语句结尾的词结尾，比如英文句点或者中缀操作符。
2. 下一行以一个泵作为语句开头的词开头。
3. 当前行的行尾出现在圆括号或者方括号，因为再怎么说圆括号和方括号也不能直接包含多条语句。

Scala编译器会在内部将操作标识符用内嵌 \$ 的方式转成合法的Java标识符，比如， :->这个操作符会在内部表示为 \$colon\$minus\$greater ，如果打算从Java中访问这些标识符，就需要使用这种内部形式。 



**只要有机会，尽可能使用val 而不是 var， 它会让你的代码更易读，也更容易重构。其中的一大好处就是对等式推理（equational reasoning）的支持，引入的变量等于计算出它的值的表达式（假定该表达式没有副作用），因此，在任何地方打算写变量名都可以直接用表达式来代替。**



一般来说，Scala只有两个命名空间用于定义，不同于Java的4个。Java中的4个分别是：**字段， 方法，类型和包**， 而Scala中的两个命名空间分别是：

- **值（字段， 方法， 包和单例对象）**
- **类型（类和特质名）**

**Scala将字段和方法放在同一个命名空间的原因正是为了让你可以用 val  来重写一个无参方法，包和单例对象都放一起也是同理，而这在Java中都是不被允许的。**



**底类型**

1. Null类是null引用的类型，它是每个引用类，也就是（每个继承自AnyRef的类）的子类，NUll不兼容于值类型，不能够将null赋值给一个整数变量。
2. Nothing是位于Scala类继承关系的底部，他是每个其他类型的子类型。不过，并不存在这个类型的任何值，Nothing的用途之一是给出非正常中止的信号。比如error的返回类型。



**for 表示法本质上和数据库查询语言的通用操作是等效的.。每个 for 表达式都可以用三个高阶函数  map,  flatMap 和 withFilter 来表示。**

**要支持各类for 表达式的写法， 需要你在数据类型上定义map, flatMap, withFilter和 foreach方法，也可以实现这些方法的子集，来支持部分for 表达式或者 for 循环的能力。确切的规则如下：**

1. **如果你的类型只定义了map， 它将允许包含单个生成器的for 表达式，**
2. **如果它同时定义了map 和 flatMap, 它将允许包含多个生成器的for表达式。**
3. **如果它定义了 foreach， 它将允许 for 循环（单个或者多个生成器）**
4. **如果它定义了withFilter,  它将允许for表达式中以 if 开头的过滤器表达式。**

**for 表达式的翻译发生在类型检查之前，这将允许最大限度的灵活性，因为唯一的要求是 for 表达式展开后能够通过类型检查。Scala对于 for 表达式本身并没有规定任何类型规则。也不要求map, flatMap, withFilter和 foreach有任何特定的类型签名。**

```scala
abstract class C[A]{
  def map[B](f: A => B)：C[B]
  def flatMap[B](f: A => C[B]): C[B]
  def withFilter(p: A => Boolean): C[A]
  def foreach(b: A => Unit): Unit
}
```



**将AnyVal类型数据转换为Double数据类型的方法，其他格式同理**

```scala
val number:AnyVal = 10
val l:Long = number.asInstanceOf[Number].longValue
```



**如何在模式匹配中的case 匹配 regex 表达式：**

```scala
val Pattern = "([a-cA-C])".r
word.firstLetter match {
   case Pattern(c) => c bound to capture group here
   case _ =>
}
```





## 1.基本数据类型



### 1.字符

判断String是否相等，用 == 即可。在scala中不可使用null 值。

```scala
//要创建包含多行的String 变量时，用
val foo = """I am a stupid guy,
I'am trying to learn scala."""

//split String 
"hello world".split(" ")
//res0: Array[java.lang.String] = Array(hello, world)
```

**在String前面添加s就可以讲变量变为字符串来输出了,要对String输出中对变量进行变换处理，用${} 括起来.  s 本质上是一个方法。 scala如此设计是为了能更灵活的设计s方法，使得String输出更强大，其他的还有f等（格式化输出）。r 关键字能够实现regex模式匹配。 raw关键字可以屏蔽String中包含的\t, \n 等转义字符，使得String保持原本字面意思 。**

```scala
val name = "ku"
val age = 24
val weight = 145
println(s"$name is $age years old, and weighs $weight pounds.")
print(s"Age next year: ${age + 1}, my age is 24: ${age == 24}")
println(f"$name is $age years old, and weights $weight%.2f pounds")
print("foo\nbar")
print(raw"foo\nbar")
```

第二种格式化输出的例子是利用String自带的format方法以及%字符。遵循printf的所有语法格式和关键字。

```scala
val s = "%s is %d years old".format(name,age)
```



**字符匹配, 替换和提取**

```scala
//创建一个简单的regex，两种方式
val numPattern = "[0-9]+".r  //第一种
import scala.util.matching.Regex
val numPattern = new Regex("[0-9]+") //第二种
val address = "123 Road Suite 101"
val match1 = numPattern.findAllIn(address) //得到一个迭代器
val matchString = numPattern.findAllIn(address).toArray //获得一匹配到的Array
//类似的还有 findFirstIn, findLastIn方法，这两个方法还可以配合getOrElse(args)方法返回未匹配到时的默认值。
val result = numPattern.findFirstIn(address).getOrElse("no match")


```

对于字符替换，字符是不可变对象，只能通过创建新字符串来完成String替换。同样是有两种方式可以进行

```scala
val address = "123 Main Street".replaceAll("[0-9]", "x")
val regex = "[0-9]".r
val newAddress = regex.replaceAllIn("123 Main Street", "x")
```



### 2.数字

**字符串与数字的相互转化**

scala中所有数字都是一个Object。

用 **to*** 方法可以将String 转换成各种类型的数据， 有**toInt, toDouble,  toFloat, toLong,  toShort, toByte**.  

java的parseInt方法也可实现转化，并且提供进制的设置。

```scala
Integer.parseInt("3", 2)
Integer.parseInt("3")
Integer.parseInt("100", 2) //按照二进制解析的方法，将String转成10进制的数字/
```

对于超大数据， scala和Java一样，通过BigInt和  BigDecimal类的方式来创建

**for和foreach**

```scala
//生成数组方式
val x = (1 to 10).tolist
val y = (1 t0 10).toArray

val a = Array("apple","orange", "banana")
for(i <- 0 until a.length){   //遍历方式
  println(f"$i is ${a(i)}")
}

//通过zipWithIndex方法可以连同 index 一起实现遍历。
for((e, count) <- a.zipWithIndex){
    println(s"$count is $e")
}
```

当for 与 yield 连用时，迭代的元素是新生成的对象的，不影响原来的对象的值，输出也是新的对象，当没有yield时，则迭代的是对象的元素本身。

关于循环的几条总结：

1. A simple **for** loop that iterates over a collection is translated to foreach method called on the collection.
2. A **for** loop with a guard is ttanslated to a sequence of a withFIlter method call on the collection followed by a foreach call.
3. A **for** loop with a yield expression is translated to a map method call on the colletions.
4.  A **for** loop with a yield expression and a guard is translated to a withFilter method on the collection followed by a map method.



### 3.流程控制

Scala中只有为数不多的内建控制结构，if, while ,for , try, match和函数调用。之所以这么少归功于Scala一开始引进了函数字面量。**Scala所有的控制结构都返回某种值做为结果，这就是函数式编程语言采取的策略，可以将这种方式看作是指令式语言已经存在的那种趋势的终值。这种返回值方式有助于简化代码，缺少这个机制，程序员必须创建临时变量，这些变量仅仅是保存那些在控制结果内部计算出来的结果， 总体言之，Scala这些基础的控制结构虽然看上去很小，取提供了本质上跟指令式编程语言相同的功能，通过确保每段代码都有返回值让代码变得更短。**

**case 关键字**

利用case语句可以实现一些自发的动作。

```scala
val mon = 1
val month = mon match{
  case 1 => "January"
  case 2 => "February"
  case 3 => "Mrch"
  case _ => "Invalid month"
}

val i = 5
i match {
    case 1 | 3 | 5 | 7 | 9 => println("add")
    case 2 | 4 | 6 | 8 | 10 => println("even")
}
```



**try/catch语句**

```scala
//与java 的try/catch语法非常相似，
val s = "Foo"
try {
    val i = s.toInt
}catch{
    case e: Exception => e.printStackTrace
}

//java中捕捉多个可能的Exceptions时直接对每个exception 都来一次catch， 而scala中则是用case语句实现
try{
    openAndReadFile(filename)
} catch {
    case e: FileNotFoundException => println("Could not found the file")
    case e: IOException => println("IO Error")
    
    case t: Throwable => t.printStackTrace() //捕捉所有可throw的异常。
    //case _: Throwable => println("exception ignored")
}
```

scala中要throw异常不需要在函数定义中做任何特殊标记。

```scala
//nothing required here
def toInt(s: String): Option[Int] = 
try {
    Some(s.toInt)
} catch{
    case e: Exception => throw e
}

//If you prefer to declare the exceptions that your method throws, or you need to interact with Java, add the @throws annotation to your method definition:
@throws(classOf[NumberFormatException])
def toInt(s: String): Option[Int] =
  try {
	Some(s.toInt)
  } catch {
	case e: NumberFormatException => throw e
  }
```



Scala中while循环没有任何返回值，因此返回的是默认值Unit单元（）， 赋值语句也是一样，所以不可以像Java用赋值语句用在if或者while的判断中，这样会永远只有一个结果。一般来讲，建议像挑战var那样挑战代码中的while循环。事实上var通常是和while一起出现的，如果找不到合适的理由来使用她们。那就应该尝试其他方案。



**for 循环**

for循环体的语句每被执行一次，都会产生一个值，通过yield关键字，可以将for循环的返回值放在一起产生一个新的集合。语法如下：

```Scala
for 子句 yield 代码体

def scalaFiles = 
for{
    file <- fileList
    if(file.getName.endWith(".scala"))
  }yield file 
//def scalaFiles = for( file <- fileList if(file.getName.endWith(".scala"))) yield file 

```



**match表达式**

类似于其他语言中的switch, 但是Scala中没有continue和break

```scala
val firstArg = if(!args.isEmpty) args(0) else ""
val f = 
  firstArg match{
    case "salt" => "pepper"
    case "chips" => "salsa"
    case _ => println("huh?")
  }
println(f)
```

和Java的swith相比，区别有以下：

1. Match表达式会返回值,每个可选项执行以后都会返回一个值。
2. **match中任何常量，字符串都可以作为样例，而不是仅限于Java中的case语句支持的整型，枚举和字符串常量。**





## 2.函数



**函数式语言的主要特征之一就是，函数是头等结构，而这也正是Scala的主要特征。**

```Scala
//一种简单的但因命令行参数的方法
args.foreach(args => println(arg))
```



**lazy关键字： 修饰变量的话，表示该变量只有在第一次被使用的时候才会实例化。**



#### **1.一等函数**

**scala支持一等函数。不仅仅可以定义函数并调用她们，还可以使用匿名的字面量来编写函数并将它们作为值进行传递。函数字面量被编译成类，并在运行时实例化成函数值。因此，函数字面量和函数值的区别在于，函数字面量存在于源码中，而函数值以对象形式存在于运行时。这跟类与对象的区别很相似。**

Scala提供了多个冗余信息，更简要的编写函数的方式，其中一个去除源码中无用字符的方式是省去某个靠类型推断的参数两侧的圆括号。

```Scala
val s = List(1,2,3,4,5)
s.filter((x:Int) => x > 2)
//编译器可以通过s推出x的type，所以x的类型推断信息可以直接去掉了
s.filter(x => x > 2)
s.fiter(_ > 2) = s.filter((x:Int) => x > 2)
```

**为了使函数更加精简，还可以使用下划线作为占位符，用来表示一个或者多个参数，只要满足每个参数只在函数字面量中出现一次即可。多个下划线意味着多个参数，而不是对单个参数的重复使用，出现多个下划线时就需要补充类型信息了，否则编译器不通过。**

```scala
val s = List(1,2,3,4,5)
s.filter(_ > 2)  //最精简的写法
//多个占位符定义的函数
val f = (_: Int) + (_: Double)  //必须补上类型信息
f(4,10.0)
```



```scala
def sum(a: Int, b:Int, c: Int) = a + b + c
val s1 = sum _  //scala仅在明确预期函数类型的地方允许省掉 _ , 通常他会明确要求你指出哪些是你特意省去的参数。
val s2 = sum(1, _:Int,3)
println(s1.apply(1,2,3).toString)
println(s2.apply(12) )
```

如果你要的部分应用函数表达式并不给出任何参数，比如println _ 或者 sum _ ，可以在需要这样一个函数的地方更加精简的表示，连下划线也不用写，



**闭包**：

运行时可以从函数字面量创建出来的函数值（对象）被称作闭包（closure）。该名称源于“捕获”其自由变量从而“闭合”该函数字面量的动作。没有自由变量的函数字面量，比如（x: Int） => x  + 1 称其为闭合语。



**特殊函数的调用形式**

1. 重复参数。Scala允许标识出函数的最后一个参数可以被重复。这让我们可以对函数传入一个可变长的参数列表，在参数类型后面加一个（*）即可。

   ```scala
   def echo(args: String*) = for(arg <- args) println(arg)
   ```



#### 2.偏函数

https://www.cnblogs.com/MOBIN/p/5326994.html

如果你想定义一个函数，而让它只接受和处理其参数定义域范围内的子集，对于这个参数范围外的参数则抛出异常，这样的函数就是偏函数，顾名思义，此函数只处理传进来的部分参数。

偏函数是一个特质，其类型是PartialFunction[A, B] 其中接收一个类型为A的参数，返回一个参数类型为B的结果，内部默认定义了 **isDefinedAt**  和 **apply** 函数，可重写，在调用偏函数时，这两个函数都回被自动调用。

```scala
val divide = new PartialFunction[Int, Int]{
  // isDefinedAt 方法可以检测一个特定的值是否被接受，接受则继续调用apply, 否则报错
  def isDefinedAt(x: Int): Boolean = x != 0  
  // apply 方法则是将传入参数进行处理，然后输出。
  def apply(x: Int): Int = 100 / x
}
//利用case 语法使之更简洁
val divide1: ParitialFunction[Int, Int] = {
  case d: Int  if d != 0 => 100/d
}
```



OrElse方法可以将多个偏函数组合起来使用，结合起来的效果类似case语句，但是每个偏函数里又可以再使用case。也可以用 addThen 方法串接起来。

```scala
scala> val or1 : PartialFunction[Int,String] = {case 1 => "One"}
or1: PartialFunction[Int,String] = <function1>
  
scala> val or2 : PartialFunction[Int,String] = {case 2 => "Two"}
or2: PartialFunction[Int,String] = <function1>
  
scala> val or_ : PartialFunction[Int,String] = {case _ => "Other"}
or_: PartialFunction[Int,String] = <function1>
  
scala> val or = or1 orElse or2 orElse or_ //使用orElse将多个偏结合起来
or: PartialFunction[Int,String] = <function1>
scala> val or = or1 addThen  or2 addThen  or_ //使用 addThen 将多个偏结合起来
or: PartialFunction[Int,String] = <function1>
```

当我们想要实现一个验证系统的时候，偏函数的这个特性将会变得非常有用。我们可以实现一系列的检查用于检测输入数据是否满足特定的规则。



在函数式编程语言中，调用函数的过程也叫做将函数应用(applying)到参数。当调用时传入了所有的参数，就叫做将函数完全应用(fully applied)到了所有参数。如果在调用时只传入了部分参数，返回的结果就是一个部分应用函数(Partially Applied Function)。当只传入部分参数时，Scala并不会报错，而是简单地应用(apply)了这些参数，并返回一个接受剩余参数的新函数。



#### **3.尾递归**

在函数的最后一步调用自己的函数，被称为尾递归函数（tail recursive）。Scala能够检测到尾递归并将他替换为跳转到函数的最开始，并在跳转之前将参数更新为新的值。这是Scala针对递归的一个优化。通常递归算法比基于循环的算法更加优雅简洁，如果解决方案是尾递归的，那么并不需要制度任何额外的开销。

不过在Scala中使用尾递归是比较受限的，因为用JVM指令实现更高级形式的尾递归非常的困难，Scala只能对那些直接尾递归调用自己的函数做优化。如果递归调用是间接的，就无法进行优化

```scala
def isEven(x:Int): Boolean = if (x == 0) true else isAdd(x-1)
def isAdd(x:Int): Boolean = if(x == 0) false else isEven(x-1)
```

同样，如果最后一步调用的是一个函数值而不是发起调用的那个函数自己也无法享受到尾递归优化。

```Scala
val funValue = nestedFun _
def nestedFun(x: Int) : Unit={
    if (x != 0) {println(x);funValue(x-1)}
}
```







scala 中函数和方法是完全不同的两个概念，不能混淆，二者定义的方式也不同

```scala
//方法
def m1(x: Int, y: Int) Int ={x + y}
//res:  m1: (x: Int, y: Int)Int

// 函数
val f1(x: Int, y: Int) => x + y
// res:   f1: (Int, Int) => Int = <function2>

def m2 (f： (Int, Int) => Int) = f(3, 4)   //将函数作为参数，传入方法
// res   m2: (f: (Int, Int) => Int)Int

var f2 = m2 _   //将方法转换为函数
//有时候Scala编译器需要函数结果类型的定义，比如说，如果函数是递归的，那么函数结果类型就必须被明确的说明。有些情况下，在没有指明返回值类型的时候，编译器也能推断他。如果函数仅包含一个语句，那么可以省略花括号。
def max2(x: Int, y:Int) = if(x > y) x else y
```



#### **柯里化（currying）**

**一个经过柯里化的函数在应用时支持多个参数列表，而不止有一个。**

**在拥有一等函数的语言中，可以有效制作出新的控制接口，尽管语言的语法是固定的，你需要做的就是创建接收函数作为入参的方法。**

```scala
def curriedSum(x: Int)(y: Int) = x + y
def curriedMultiply(x: Int) = (y: Int) => x * y
def twice(op: Double => Double, x:Double) = op(op(op(x)))
val f1 = curriedSum(12)_ 
val f2 = curriedMultiply(12)
println(f1.apply(12) )
println(f2.toString())
println(curriedMultiply(3)(2))
println(twice((x:Double) => x * 10,3))
println(twice(_ * 10, 3))
```



Scala允许用花括号代替圆括号来传入单个入参的目的是为了让调用方程序员在花括号当中编写函数字面量。这能让方法用起来更像是控制抽象。

**定义无参方法**

```Scala
abstract class Element{
    def contents: Array[String]
    def height:  Int = contents.length
    def width: Int = (if height == 0) 0 else contents(0).length 
}
```

三个方法都没有参数列表，定义时连圆括号都没有。这在Scala中很常见，被称为**无参方法**（parameterless method）。而def height() : Int ， 称**为空圆括号方法**，**推荐的做法时对于没有参数且只通过读取所在对象字段的方式访问可变状态的情况下尽量使用无参方法。这样做法支持所谓统一访问原则，使用方代码支持所谓的统一访问原则，使用方代码不应该受到某个属性是用属性还是用字段实现的影响。** 上例中的所有 def 完全可以直接替成 val, 从使用方来看没有任何区别。

唯一需要小心的是，Java中没有实现统一访问原则，因此Java中要写string.length() 而不是 string.length,  而对于数组要写 array.elngth 而不是 array.length()。因此为了减小混淆，**Scala中可以对所有的无参函数调用都去掉空括号。**不过仍然建议在被调用方法不仅只代表接受该调用的对象的某个属性时加上空括号。例如，空括号的应用场景包括执行IO， 写入可重新赋值的var，读取接收该调用对象字段之外的var，这样就可以知道该调用是触发了某个副作用。



## 3.语法



### 1.Option 和 Some

Option is container base which can be empty ir full. While Some(x) represent full with 'x' being present in th e container, None represent empty. some extends Option, so It inherits everything except get and isEmpty( and some other methods implemented by a case class.).  the companion object of Option has a special apply method foe dealing with null: 

为了让所有东西都是对象的目标更加一致，也为了遵循函数式编程的习惯，Scala鼓励你在变量和函数返回值可能不会引用任何值的时候使用Option类型。在没有值的时候，使用None，这是Option的一个子类。如果有值可以引用，就使用Some来包含这个值。Some也是Option的子类。 

None被声明为一个对象，而不是一个类，因为我们只需要它的一个实例。这样，它多少有点像null关键字，但它却是一个实实在在的，有方法的对象。

在Scala里Option[T]实际上是一个容器，就像数组或是List一样，你可以把他看成是一个可能有零到一个元素的List。 当你的Option里面有东西的时候，这个List的长度是1（也就是 Some），而当你的Option里没有东西的时候，它的长度是0（也就是 None）。如果把Option 当作一般的List来用并且用一个for 循环迭代它时， 如果Option是None, 那么这个for 循环就不会启动，

```scala
def apply[A](x: A): Option[A] = if (x == null) None else Some(x)
```



### 2.组合和继承

定义参数化对象

```Scala
class Cat{
  val dangerous = false
}
class Tiger(
           override val dangerous: Boolean,
           private var age: Int
           ) extends  Cat

//调用超类构造方法
class ArrayElement(
  val contents: Array[String]
) extends Element

class LineElement(s: String) extends ArrayElement(Array(s)){
    override def width = s.length
    override def height = 1
}
```



工厂对象：

工厂对象包含创建其他对象的方法。使用方用这些工厂方法来构造对象，而不是直接用new 构建对象，这种做法的好处是对象创建逻辑可以被集中起来，而对象是如何用具体的类表示的可以别隐藏起来。这样既可以让你的类库更容易被使用方理解，因为暴露的细节更少，也更方便后续修改。



### 4.单类对象

**单类对象并不仅仅用来存放静态方法，它是一等的对象，可以把单类对象的名称想象成附加在对象身上的“名字标签”。**

**类和单类对象的一个区别是单例对象不接受参数，而类可以。由于你没法用new实例化单例对象，也就没有任何手段来向她传参。每个单类对象都是通过一个静态变量引用合成类（synthetic class)的实例来实现的。因此单利对象从初始化的语义上跟Java的静态成员是一致的，尤其体现在，单例对象在有代码首次访问时才被初始化。**

**没有同名的伴生类的单例对象称为孤立对象（standalone object）。孤立对象有很多用途，包括将工具方法归集在一起，或定义scala应用程序的入口。**要运行一个scala程序，必须提供一个独立对象的名称。这个独立对象需要包含一个main方法，该方法接受一个Array[String]作为参数，结果类型为Unit , **任何带有满足正确签名的main方法都可以被应用作为应用程序的入口。**



### 5. trait

```scala
import scala.collection.mutable.ArrayBuffer

abstract class IntQueue {
  def get() :Int
  def put(x:Int)
}

trait Doubling extends IntQueue{
  abstract override def put(x: Int): Unit = super.put(x * 2)
}

trait Filter extends IntQueue{
  abstract override def put(x: Int): Unit = {
    if( x >= 0 )  super.put(x)
  }
}
trait Add extends IntQueue{
  abstract override def put(x: Int)= super.put(x + 1)
}

trait A extends IntQueue{}
trait AA{}
class B{}
class C extends AA{}
abstract class cc extends IntQueue with A{}
class D extends C{}
trait AAA extends A with AA{}

class BasicIntQueue extends IntQueue{
  private val buf = new ArrayBuffer[Int]
  override def get(): Int = buf.remove(0)
  override def put(x: Int): Unit = buf += x
}

object test{
  def main(args: Array[String]): Unit = {
    val queue = (new BasicIntQueue with Filter with Add  with Doubling)
    queue.put(1)
    queue.put(2)
    queue.put(3)
    queue.put(-1)
    queue.put(-2)
    println(queue.get())
    println(queue.get())
    println(queue.get())
  }
}
```

trait 分为动态绑定和静态绑定，既可以绑定trait，又可以绑定class。scala 中只允许类的单继承，因此trait也最多只能extends 一个类，静态绑定时 如果同时有class 和 trait 需要绑定，必须先用extends关键字绑定class ，再绑定 trait . 多个待绑定的 trait 之间用 with 连接。 当只有一个trait需要绑定（没有class时） 也要用 extends 绑定 。**简而言之，静态绑定时， extends 有且必须只出现一次且在最前面。继承类个数 <= 1。  动态绑定时可以不用出现 extends 关键字，而直接使用多个 with 关键字。**   

对于上例中 **Doubling** 而言，它在一个声明为抽象的方法里做了一个super调用，通常这是非法的，因为调用时会失败。不过对于特质而言，这是成功的，因为特质中super调用是动态绑定，只要在给出了该方法具体定义的特质或类之后混入，Doubling 特质中的 super 调用就可以正常工作。对于实现可修改可叠加的特质，**这是必要的，为了告诉编译器是特地这么做的，必须要将这样的方法标记为abstract override。这样的修饰符组合只允许用在特质的成员上，不允许用在类的成员上，它的涵义是该特质必须混入某个拥有该方法具体定义的类中。**

1. 多个 with 特质之间的调用顺序，按照从远到近的顺序。越靠右越先生效。初始化顺序则是按照继承顺序来。
2. 如果 trait A extends B{}  B是一个class， 那么所有绑定A的类都必须要是B的子类才行。 



### 6.包和引用

#### 1.包的引入和引用

除了常规的方式，还有另外一种方法可以将Scala代码放进包中，在 package 子句后面加上一段用花括号包起来的代码块，这个代码块包含了进入该包的定义，被称作打包。这样就可以在同一个文件中声明多个包，并且包之间还可以进行嵌套。

一个类可以从包含它的包里不需要前缀就别人访问到。其次，包自身也可以从包含他的包里不带前缀的访问到。

```Scala
package Bobsrockets {
  package navigation {
    class Navigator{
      val map = new StartMap  //无需前缀即可访问
    }
    class StartMap
  }
  class Ship{
    val nal = new fleets.Fleet
    val b = new nal.B    
  }
  package fleets{
    class Fleet {
      class B{ def addShip() = new Ship }
      def addShip() = new Ship
      def addNavigation() = {new navigation.Navigator}
    }
  }
}
```



使用花括号打包语法时，所有在包外的作用于内可被访问的名称，在包内也可以访问的到。这类方法问只有当显示的嵌套打包时才有用。

相比Java，Scala的import更加的灵活，主要有以下三点不同：

1. 引入可以出现在任何地方。

2. 引入可以引用对象（不论是单例还是常规对象），而不只是包

3. 让你重命名并隐藏某写被引入的成员。

   ```Scala
   //重命名的格式为  < 原名 > => < 新名 >
   import java.sql.{Date => SDate}  //别名
   import java.sql._  //引入所有
   
   import Fruits.{Apple => _, _} //引入Fruit中所有的成员（除了Apple）
   ```

4. 它可以引入包本身，而不仅仅是这些包中的非包成员，如果把嵌套的包想象成包含在上层包内，这样的处理是很自然的。





#### 2.访问修饰符

跟Java相比，Scala对protected成员的访问也更严格，在Scala中，protected的成员只能从定义该成员的子类访问，而Java允许同一个包内的其他类访问这个类的受保护成员。Scala提供了另一种方式来达到这种效果，就是添加 **qualifier** 修饰符。

**公共成员**：scala并没有专门的修饰符来标记公共成员，任何没有标记为private 或者 protected 的成员都是公共的。公共成员可以从任何位置上访问到。

**我们可以用限定词对Scala中的访问修饰记制进行增强，形如 private[X] 或 protected[x] 的修饰符的含义式对此成员的访问限制 “上至” X 都是私有或者受保护的，其中 Ｘ表示某个包含包含该定义的包，类或者单类对象。**

带有限定词的访问修饰符让我们可以对成员的可见性做非常细粒度的控制。这些用scala中简单的修饰符是无法直接表达出来的。这种机制还允许我们表达那些无法在Java中表达的访问规则。这个记制在那些垮多个大型包的工程非常有用，可以定义对工程中某些字包可见但对外界不可见的实体。

最后Scala还提供了比private 限制范围更小的访问修饰符。被标记为 **private[this]** 的定义，**只能在包含该对象的同一个对象所访问**。这样的定义被称作对象私有（object-private）。将一个成员标记为 private[this] 保证了它不会被同一个类的其他对象看到。方便编写更通用的型变注解。



#### 3.可见性和伴生对象

 Scala的访问规则在private 和 protect 的处理上给伴生对象和类保留了特权，**一个类会将它的所有访问权限都和它的伴生对象共享，反过来也一样。**不过对于Scala的伴生对象而言，protected的成员是没有意义的，因为单例对象没有子类。

```scala
class Rocket {
  import Rocket.fuel
  private def canGoHomeAgain = fuel > 20
}

object Rocket{
  private def fuel = 10
  def chooseStrategy(rocket: Rocket)={
    if(rocket.canGoHomeAgain) 
      goHome()
    else
      pickAStar()
  }
  def goHome(){}
  def pickAStar()={}
}
```



### 7.样例类

https://docs.scala-lang.org/zh-cn/tour/case-classes.html

一个最简单的案例类定义由关键字`case class`，类名，参数列表（可为空）组成. 与普通类的区别主要有以下几点：

1. 实例化案例类时，并没有使用关键字`new`，这是因为案例类有一个默认的`apply`方法来负责对象的创建。
2. 当创建包含参数的案例类时，这些参数默认是公开( public ) 的 val
3. 案例类的实例在比较的时候时按值比较而非引用比较。
4. 可以通过 copy  方法创建一个案例类实例的浅拷贝，可以同时指定构造参数来做一些改变。



### 8.模式匹配

案例类非常适合于模式匹配

这组孪生的语法结构为我们编写规则的，未封装的数据结构提供支持，这两个语法结构树对于表达树形的递归数据尤其有用。

要理解模式匹配(pattern-matching)，先把这两个单词拆开，先理解什么是**模式(pattern)**，这里所的模式并不是设计模式里的模式，而是数据结构上的，这个模式用于描述一个结构的组成。狭义的看，模式可以当作对某个类型，其内部数据在结构上抽象出来的表达式。如上面的`List("A", _, _*)`就是一种List结构的pattern。模式匹配(pattern-matching)则是匹配变量是否符合这种pattern。比如`List("A","B")`和`List("A","X","Y")` 就符合上面的pattern，而`List("X")`则不符合。

在 scala里对pattern有明确的定义，在形式上有以下几种pattern：

1. 常量模式（constant patterns） 包含常量变量和常量字面量，常量模式和普通的 if 比较两个对象是否相等(equals) 没有区别。

   ```scala
   scala> val site = "alibaba.com"
   scala> site match { case "alibaba.com" => println("ok") }
   scala> val ALIBABA="alibaba.com"
   //注意这里常量必须以大写字母开头
   scala> def foo(s:String) { s match { case ALIBABA => println("ok") } } 
   ```

2. 变量模式（varible patterns)， 单纯的变量模式没有匹配判断的过程，只是把传入的对象给起了一个新的变量名。

   ```scala
   site match { case whateverName => println(whateverName) }
   //上面把要匹配的 site对象用 whateverName 变量名代替，所以它总会匹配成功
   //不过这里有个约定，对于变量，要求必须是以小写字母开头，否则会把它对待成一个常量变量，比如上面的whateverName 如果写成WhateverName就会去找这个WhateverName的变量，如果找到则比较相等性，找不到则出错。
   
   //变量模式通常不会单独使用，而是在多种模式组合时使用，比如
   List(1,2) match{ case List(x,2) => println(x) }
   ```

3. 通配符模式， case _  => 它可以匹配任何对象。用于处理所有其他匹配不成功的情况。

4. 构造器模式（constuctor patterns）.构造器模式能真正体现出模式匹配威力的地方。这些额外的模式意味着Scala的模式支持深度匹配。这样的模式不仅检查给出对象的顶层，还会进一步检查对象的内容是否匹配额外的模式要求，由于额外的模式也可能是构造方法模式，用她们来检查对象内部时可以到任意的深度。

5. 序列模式，与样例类匹配相似，也可与序列类型做匹配。

   ```scala
   def listDemo(expr: Any) = 
   	expr match{
     	case List(0, _*) => println("found it")
     	case _ =>
   	}
   ```

6. 带变量类型的模式匹配，可以用来代替类型类型测试和类型转换。

   ```Scala
   //带类型的模式 匹配
   def generalSize(x: Any) = x match {
     case s: String => s.length
     case m: Map[_, _] => m.size
     case _ => -1
   }
   
   //重写match的类型转换
   if (x.isInstanceOf[String]){
     val s = x.asInstanceOf[String]
     s.length
   }else ...
   ```

7. 变量绑定。除了独自存在的变量模式，我们还可以对任何其他的模式添加变量。只需要写下变量名， 一个 @ 符和一个模式本身，就可以得到一个变量绑定模式。

**密封类**

将样例的超例标记为密封（**sealed**） 的，密封类除了在同一个文件中定义的子类之外，不能添加新的子类，这一点对于模式匹配而言十分有用，因为这样一来，我们就只需要关心那些已知的样例类，还会获得更好的编译器支持，如果我们对继承自密封的样例类做匹配，编译器用警告消息标识出缺失地模式组合。如果你的类被打算用于模式匹配，就应该将她们做成密封类。

```scala
sealed abstract class Furniture
case class Couch() extends Furniture
case class Chair() extends Furniture

def findPlaceToSit(piece: Furniture): String = piece match {
  case a: Couch => "Lie on the couch"
  case b: Chair => "Sit on the chair"
}
```

**Option类型**

Scala由一个名为Option的标准类型来表示可选值。这样的值可以有两种形式，：Some(x), 其中x那个实际的值，或者None对象，代表没有值。将可选值解开最常见的方式是通过模式匹配。例如

```scala
def show(x: Option[String]) = x match {
    case Some(s) => s
    case None => "?"
}

val capitals = Map("France" -> "Pairs", "Japan" -> "Tokyo")
scala> show (capitals get "France")


```

scala鼓励我们使用Option来表示可选值，这种处理可选值的方式跟Java相比有若干优势，某个类型为Option[String]的可选项对应一个可选的String，跟某个类型为String的变量是一个可选的String，可能是null ，相比要值观的多。

**本质上讲，case序列就是一个函数字面量，只是更加的通用，不像普通函数那样只有1个入口和参数列表，每个case对应函数的一个入口，而该入口的参数列表用模式来指定，每个入口的逻辑主题是case 右边的部分。**

```scala
val withDefault:Option[Int] => Int = {
      case Some(x) => x
      case None => 0
    }
 
withDefault(Some(10))  //res: Int = 10
withDefault(Some(None))  //res: Int = 0
```



**有一点值得注意，通过case序列得到的是一个偏函数，如果讲这样一个函数应用到他不支持的值上，他会产生一个运行时异常。如果想检查某个偏函数是否对某个入参有定义，必须首先告诉编译器你知道你要处理的是偏函数。** 仅涵盖从整数列表到整数的偏函数的类型写作 PartialFunction[List[Int], [Int]] 

```scala 
val second : List[Int] => Int = {case x :: y :: _ => y} //普通函数定义

val second: PartialFunction[List[Int], Int] = {case x :: y ::_ => y} //定义偏函数
//偏函数定义了一个isDefinedAt方法，可以用来检查该函数是否对某个特定的值有定义。
second.isDefinedAt(List(5,6,7)) //True
```





## 3.容器

scala's general-purpose sequential collections

|                      | IMMUTABLE | mUTABLE     |
| :------------------- | --------- | ----------- |
| Indexed              | Vector    | ArrayBuffer |
| Linear(Linked lists) | List      | ListBuffer  |



### 1.列表

scala中定义了大量的有用方法.

列表和数组的两大区别：

1. **列表是不可变的，列表的元素不可通过赋值改变。**
2. **列表的结果是递归的（即链表），而数组是平的。**

和数组一样，列表也是同构的： 同一个列表的所有元素都必须是相同的类型。元素类型T的列表的类型写作 List[T].

所有的列表操作都可以通过以下三个基本的方法来定义：

```Scala
def isEmpty: Boolean
def head: T
def tail: List[T]

//Nil单例对象的定义
case object Nil extends List[Nothing] {
  override def isEmpty = true
  def head: Nothing = throw new NoSuchElementException("head of empty list")
  def tail: List[Nothing] = throw new NoSuchElementException("tail of empty list")
}

//:: cons类的定义  表示非空List
final case class ::[T](hd: T, tl: List[T]) extends List[T]{
  def head = hd
  def tail = tl
  override def isEmpty: Boolean = false
  
  //构造方法
  def ::[U >: T](x: U): List[U] = new scala.::(x, this)
  //事实上， :: 堕胎定义中的下界T不仅为了方便，对于List类的类型的正确而言也是必要的，这是因为从定义上讲 List 是协变的。
  def :::[U >: T](prefix: List[U]): List[U] =
    if(prefix.isEmpty) this
  	else prefix.head :: prefix,tail ::: this
  //其中 :: 和 ::: 都是中缀表达式，他们都是和右操作元绑定的，也就是右结合的。 这些中缀表达式等价于：
  // (prefix.tail ::: this).::(prefix.head)
  // this.:::(prefix.tail).::(prefix.head)
  
  
  //定义其他的方法, 去掉前n个元素。
  def drop(n: Int): List[T] = 
    if (isEmpty) Nil
 		else if (n <= 0) this
  	else tail.drop(n -1)
  
  def map[U](f : T => U) : List[U] = if(isEmpty) Nil else f(head) :: tail.amp(f)
}
```

这些方法都是在List类中的抽象方法，他们的具体定义出现在子对象Nil 和子类 **::** 中。Nil对象继承自类型List[Nothing], 因为协变的原因，Nilsson和List 类型的每个实例都兼容。





**为什么不在列表末尾追加元素？ List类确实提供了追加操作，写作 :+ , 但是这个很少使用，因为在列表末尾追加元素的操作所需要的时间随着列表的大小线性增加，而使用 :: 操作符在列表的前面添加元素只需要常量时间。如果想通过追加的方式高效构建列表，可以依次在头部添加完成后，再调用reverse。也可以使用ListBuffer， 这是个可变的列表，支持追加操作，完成后调用toList即可。**



```scala
//创建元组,,  元组的下表从1 开始，取下标方式也和list不同。
val pair = (1,2,3,"A")
println(pal._1)
```

元组之所以不能像list一样用pair(0)的方式访问，是因为列表的apply方法永远只返回同一种类型，但元组里的元素可以是不同类型的，  _ 1是一种类型，_2 是另一种类型，这些 _N 表示的字段名是从1开始而非0.

所有的列表都构建自两个基础的构建单元： Nil 和 ::， Nil表示空列表。

**使用模式匹配方法实现插入排序。**通常对列表做模式匹配比用方法解构更加清晰。

```scala
def isort(xs: List[Int]): List[Int] = xs match{
  case List() => List()
  case x :: xs1 => insert(x, isort(xs1))
}
def insert(x:Int, xs:List[Int]): List[Int] = xs match {
  case List() => List(x)
  case y :: ys => if (x >= y) x :: xs else y :: insert(x, ys)
}

```

**如果一个方法不接受任何函数作为参数，就被称作初阶函数。**下面是利用List中的拼接和 分治递归原则实现append功能：

```Scala
def apppend[T](xs: List[T], ys: List[T]) = xs match {
  case List() => ys
  case x :: xs1 => x :: append(xs1 :: ys)
}
```

常用方法有

1.  **(head,  last)** 和 **（init,  tail)**   对空列表使用会报错。

2. **reverse**，反转。

   ```Scala
   //用分治和拼接来实现反转
   def reverse[T](xs: List[T]): List[T] =  xs match {
       case List() => xs
       case x :: xs1 => reverse(xs1) ::: List(x)
     }
   ```

   drop,  take 方法。 这两个是对tail和init的一般化，他们返回的是列表任意长度的前缀后者后缀，表达式xs take n, 返回xs的前n个元素。xs drop n 返回除了列表xs 除了前n个元素之外的所有元素，如果 n > xs.length 就返回空列表。

   splitAt操作将列表从指定位置上切开，返回这两个列表组成的对偶

   ```scala
   xs splitAt n = (xs.take(n), xs.drop(n))
   ```

3. 扁平化 flatten

   打包列表 zip和unzip。

   zip函数中，如果两个列表长度不一致，那么没有匹配上的元素都会被丢弃。

   一个将列表和它的下表zip起来的最有效方法是用 zipWithIndex 方法。这个方法会将列表种的每个元素和它出现在列表中位置组合成对偶。

   显示列表： toString 和 mkString

   addString:  mkString的变种，将构建出来的字符串追加到一个StringBuilder对象上面。

4. 转换为列表： iterator， toArray, copyToArray

5. 对列表进行映射操作： map, flatMap和 foreach。 flatMap操作符和map类似，不过**它要求右侧的操作元是一个返回元素列表的函数。它将这个函数应用到列表的每个元素，然后将所有结果拼接起来返回。**

   foreach要求有操作员是一个过程（结果类型是Unit的函数），它只是简单的将过程应用到列表的每一个元素上去，整个操作过程的结果 

6.  过滤列表： **filter、partition、find、groupBy、takeWhile、 dropWhile和span**。

    - “xs filter p” 这个操作的两个操作元分别是类型为List[T]的 xs 和 类型为 T => Boolean 的前提函数。这个操作将交出xs中所有p(x)为true 的元素 x。
    - partition方法和filter类似。 不过返回的是一对列表，一个为true 另一个false的元素组合。它等价于：xs partition p        等于     (xs filter p,   xs filter ( !p(_)))
    - find 返回 给定前提条件的第一个元素，而非所有。
    - splitAt可以认为前n个元素进第一个集合，剩余元素进第二个集合。
    -  groupBy(p)方法会把一个集合根据你提供的方法切分成一个map。Map中key＝true对应的value是所有使p返回true的集合元素组成的新集合，key＝flase对应的value是所有使p返回false的元素组成的新集合。
    - **窗口方法sliding(w, s), W是窗口大小，s是每次滑动距离。使用这个方法，就是下标从0开始，每次向后移动s距离，每次取当下开始的w个元素，组成一个新的集合。**
    - takeWhile、 dropWhile 操作符也是将一个前提条件作为右操作元。前者返回满足条件的最长前缀，后者则删除满足条件的最长前缀，然后返回剩下的列表元素。
    - **span方法会从集合头部开始遍历直到第一个不满足p的元素为止，所有满足p的进第一个集合，不满足p的进第二个集合。**可以将span看作是takeWhile、 dropWhile两个方法的合集。**就像splitAt是将take和drop合二为一一样。**

7.  对列表前提性检查： **forall 、 exists** .前者全与操作，或者全或操作。

8.  折叠列表： /:    :\。

    左折叠操作  **(z /: xs) (op)**  涉及3个对象，起始值z，列表xs， 和二元操作op. 折叠的结果是以z为前缀，对列表的元素依次连续应用op。如: **(z /: List(a,b,c)) (op)**  等于  **op(op(op(z,a),b),c)**  

    右折叠操作同理。 **(z  :\  List(a,b,c)) (op)**  等于  **op(a, op(b, op(c, z)))** 

    在使用这两个折叠符的时候，类型信息一定都要补上去。

    ```scala
    def sum(xs: List[Int]): Int = (0 /: xs) (_ + _)
    def product(List(a,b,c)): Int = (1 /: xs) (_ * _)
    
    //定义两个折叠拼接方法，用右折叠比左折叠要更加高效
    def flattenLeft[T](xss: List[List[T]]) = (List[T]() /: xss) (_ ::: _)
    def flattenRight[T](xss: List[List[T]]) = (xss :\ List[T]()) (_ ::: _)
    
    //用折叠方式反转列表，比reverse更高效，开销为线性的。
    //模板  def reverseLeft[T] (xs: List[T]) = (startValue /: xs)(operation)
    def reverseLeft[T] (xs: List[T]) = (List[T]() /: xs) { (ys,y) => y :: ys}
    //用此种方式可以将变量 ：： 操作符反转。 
    
    ```

9.   列表元素排序： **sortWith**, 

    xs  sortWith before  这个操作对列表xs中的元素进行排序，xs限定为列表

    ```scala
    List(1,2,-3,4,2,6) sortWith (_ < _)
    List("a","dfs", "ssdsdsd") soerWith (_.length > _.length)
    ```



List对象方法（全局方法），定义在全局可访问对象的 **scala.List** 上，这是List类的伴生对象，某些操作用于创建列表的工厂方法。另一些是对特定形状的列表进行操作。

1. 从元素创建列表： **List.apply**

2. 创建数值区间： **List.range**

3. 创建相同元素的列表： **List.fill**, 接受两个参数，要创建的列表长度和需要重复的元素。各自以不同参数列表给出。  **List.fiil(10)("hello")**

4. 表格化一个函数：**List.tabulate** ,和 fill 的区别是 元素值不固定，而是从函数计算得来的。

   ```scala
   scala> val squares = List.tabulate(5) (n => n * n)
   squares: List[Int] = List(0, 1, 4, 9, 16)
   
   scala> val plication = List.tabulate(5,5)(_ * _ )
   plication: List[List[Int]] = List(List(0, 0, 0, 0, 0), List(0, 1, 2, 3, 4), List(0, 2, 4, 6, 8), List(0, 3, 6, 9, 12), List(0, 4, 8, 12, 16))
   ```

5. 拼接 多个列表。 **List.concat()**



### 2.序列

**List 是不可变链表序列。**

**Scala中的数组的表现形式和Java数组一致，因此可以无缝的使用那些返回数据的Java方法。**



#### **ListBuffer 和 ArrayBuffer**:

使用 ListBuffer 而不是 List 的一个原因是防止可能出现的栈溢出。

```scala
val buf = new ListBuffer[Int]
buf += 2  //尾部追加
3 +=: buf  //头部追加

//List类中用ListBuffer实现 map   不使用递归可以防止栈溢出问题。
final override def map[U](f: T => U) List[U] = {
  val b = new ListBuffer[U]()
  var these = this
  while(!these.isEmpty){
    b += f(these.head)
    these = these.tail
  }
  b.toList
}

//ListBuffer的定义
package scala.coolection.immutable
final class ListBuffer[T] extends Buffer[T] {
  private var start: List[T] =Nil  //指向缓冲中保存的所有元素的列表
  private var last0: ::[T] = _   //指向该列表的最后一个 :: 单元格
  private var exported: Boolean = false  // 表示该缓冲是否已经通过toList转成了列表
  ...
  override def toList: List[T] = {
    exported = !start.isEmpty
    start
  }
}
```

**ArrayBuffer**和数组很想，创建时需要给出类型参数，不需要指定长度，会自定分配。



序列的工厂方法：

- S.empty
- S(x,y,z)
- S.concat(xs, ys, zs)
- S.fill(n)(e)
- S.tabulate(n)(f)
- S.tabulate(m,n)(f)
- S.range(start, end)
- S.range(start,end,step)
- S.iterator(x, n)(f)



### 3.集和映射

```Scala
//常用的集合操作： 
val nums = Set(1,2,3)  //不可变Set， 以下操作都不会改变nums 的原始值
nums + 5  //
nums -3  //
nums ++ List(5,6)
nums -- List(1,2)
nums & Set(1,3,5,7)
nums.size
nums.contains(3)

import scala.collections.mutable
val words = mutable.Set.empty[String]
// 创建空的可变Set集合， words会随着操作而变化。
words += "the"  //
words -= "the"
words ++= List("do","re","mi")
words --= List("do", "re","mi")
words.clear


/*常见的映射操作 
不可变Map:
特点： api不太丰富
如果是var修饰，引用可变，支持读写
如果是val修饰，引用不可变，只能写入一次值，其后只读*/

val nums = Map("i" -> 1, "ii" -> 2) //创建不可变的map
nums += ("c" -> 3)
nums ++ List("d" -> 4, "e" -> 5)
nums - "c"
nums -- List("d", "e")
nums.size
nums.contains("d")
nums.keys  //返回key的iterable的可迭代对象。
nums.values 
nums.keySet
nums.isEmpty

/*可变Map例子
特点：api丰富与Java中Map基本类似
如果是var修饰，引用可变，支持读写
如果是val修饰，引用不可变，支持读写*/
import scala.collection.mutable  //创建可变map
val words = mutable.Map.empty[String, Int]
nums += ("c" -> 3)
nums ++ List("d" -> 4, "e" -> 5)
nums - "c"
nums -- List("d", "e")
```



特点：

**api不太丰富**

**如果是var修饰，引用可变，支持读写**

**如果是val修饰，引用不可变，只能写入一次值，其后只读**

**/*常见的映射操作 
不可变Map:
    特点： api不太丰富
如果是var修饰，引用可变，支持读写
如果是val修饰，引用不可变，只能写入一次值，其后只读*/**



**可变对象和不可变对象：**

**scala集合类库中目前的不可变映射和不可变集单个对象最多可以存4个条目，根据条目数的不同，通常占据16到20个字节。因此对于小型的映射和集而言，不可变的版本比可变的版本要紧凑的多，由于实际中使用的集合都不大，采用不可变的版本可以节约大量空间，带来重要的性能优势。** 

**为了让不可变集到可变集更加容易，Scala提供了语法糖，尽管不可变集和映射不真正支持  +=  操作，Scala提供了一个变通的解读，只要看到了 a += b 而 a 并不支持名为 += 的方法，scala 会尝试将它解读为 a = a + b.  这种特殊的语法不仅仅适用于集合，它适用于任何值。**



### 4.初始化集合

创建和初始化一个集合的最常见的方式就是将初始元素传入所选集合的伴生对象的工厂方法，只需要将元素放在伴生对象名后面圆括号里即可，Scala编译器会将它转换成 对伴生对象apply方法的调用。

**可变和不可变的集合的映射的转换：** 要想将可变集映射转为不可变。首先用empty常见一个不可变的新类型集合，然后用 ++ 或者 ++= （视具体目标而定）添加新元素。反之也可以，关键在于创建的empty集合的性质。

```scala
scala> val colors  = List("red", "yellow")
colors: List[String] = List(red, yellow)

scala> val treeSet = TreeSet[String]() ++ colors
treeSet: scala.collection.immutable.TreeSet[String] = TreeSet(red, yellow)

scala> treeSet.toList
res197: List[String] = List(red, yellow)

scala> treeSet.toArray
res199: Array[String] = Array(red, yellow)

scala> val mutSet = mutable.Set.empty ++ treeSet
mutSet: scala.collection.mutable.Set[String] = Set(red, yellow)

scala> mutSet
res200: scala.collection.mutable.Set[String] = Set(red, yellow)

scala> mutSet += "blue"
res201: mutSet.type = Set(red, blue, yellow)

scala> mutSet
res202: scala.collection.mutable.Set[String] = Set(red, blue, yellow)

scala> val immutSet = Set.empty ++ mutSet
immutSet: scala.collection.immutable.Set[String] = Set(red, blue, yellow)

scala> val muta = mutable.Map("i" -> 1, "ii"-> 2)
muta: scala.collection.mutable.Map[String,Int] = Map(ii -> 2, i -> 1)

scala> val immu = Map.empty ++ muta
immu: scala.collection.immutable.Map[String,Int] = Map(ii -> 2, i -> 1)
```



### 5.Traversable特质

在集合类继承关系的顶端的是Traversable 特质，它唯一的抽象操作是 foreach:

```scala
def foreach[U](f: Elem => U)
```

实现Traversable 的集合类只需要定义这个方法即可，及其它方法都可以从Traversable 中继承。Traversable定义了许多的具体方法，可以归类如下：

1. 添加， ++ 操作
2. 映射操作： map , flatMap, collect
3. 转换： toIndexSeq,  toIterable , toString,  toArray, toList,  toSeq,  toSet, toMap
4. 拷贝操作： copyToBuffer ,   copyToArray
5. 大小操作： isEmpty, noEmpty, size 和 hasDefiniteSize
6. 元素获取操作： head, last, headOption, lastOption和 find 
7. 子集获取操作： takeWhile, tail, init, slice, take ,drop, filter, dropWhile,  filterNot, withFilter 
8. 细分： splitAt, spam , partition, groupby
9. 元素测试： exists, forall, count
10. 折叠： flodLeft, foldRght, /: ,   :\,  reduceLeft,   reduceRight
11. 特殊操作： sum,  product,  min,  max
12. 字符串操作：mkString,  addString, dtringPrefix
13. 视图操作： 由两个重载的view 方法组成，视图是一个惰性求值的集合。



**Iterable特质**

该特质的所有方法都是用抽象方法 Iterator来定义的，这个抽象方法的作用是逐个交出集合的元素，从Traversable 继承下来的 foreach 方法在 Iterable 中的定义就用到了 Iterator ，实际的实现如下：

```scala
def foreach[U](f: Elem => U): Unit = {
  val it = iterator
  while(it.hasNext) f(it.next())
}
```

Iterable 中还有两个方法返回迭代器：grouped 和 sliding。 不过这些迭代器并不返回单个元素，而是原始集合的整个子序列。可以通过入参来指定这些子序列的最大长度，grouped 方法将元素分段，而sliding交出的是对元素的一个滑动窗口。

**Seq特质由两个子特质，LinearSeq和 IndexSeq。这两个特质并没有添加任何新的操作，不过各自拥有不同的性能特征。线性的序列拥有高效的 head,  tail 操作， 而经过下标索引的序列 apply ， length 和 update 操作。List是一种常用的线性序列，Stream也是，而Array 和 Array Buffer 是两种常用的经过下标索引的序列。**

Map是由键值对组成的Iterable ，Scala的Predef 类提供了一个隐式转换，让我们可以用key -> value 的写法来表示 (key, value)对偶。



### 6.流

Stream 和 列表很像， 不过其元素是惰性计算的，正因为i如此，流可以无限长，只有请求到的元素会被计算，除此之外，流的性能特征跟列表是一样的。列表通过 :: 操作符构造， 而Stream则是通过看上去有些相似的 #:: 来构造：

```scala
scala> val str = 1 #:: 2 #:: 4 #:: Stream.empty
str: scala.collection.immutable.Stream[Int] = Stream(1, ?)
scala> def fibFrom(a:Int, b:Int): Stream[Int] = a #:: fibFrom(b, a+b)
fibFrom: (a: Int, b: Int)Stream[Int]
scala> val fibs = fibFrom(1,1)(70)
fibs: Int = 696897233
scala> val fibs = fibFrom(1,1).take(19)
fibs: scala.collection.immutable.Stream[Int] = Stream(1, ?)
```



**向量**： **由于向量在快速的任意位置的选择和快速的任意位置的函数式更新之间达到了较好的平衡，他们目前是不可变的带下标索引的序列的默认实现。**

**不可变栈 **： 不可变的栈stack在Scala中很少被用到，因为他们的功能完全被列表囊括了，对不可变栈的push操作跟对列表的  :: 的操作相同，而对于栈的pop操作等同于对列表的tail .



### 7.数组

在Scala中，[数组](http://www.scala-lang.org/api/2.12.2/scala/Array.html)是一种特殊的collection。一方面，Scala数组与Java数组是一一对应的。即Scala数组Array[Int]可看作Java的Int[]，Array[Double]可看作Java的double[]，以及Array[String]可看作Java的String[]。但Scala数组比Java数组提供了更多内容。首先，Scala数组是一种泛型。即可以定义一个Array[T]，T可以是一种类型参数或抽象类型。其次，Scala数组与Scala序列是兼容的 - 在需要Seq[T]的地方可由Array[T]代替。

既然Scala的数组用的是Java 的数组来表示，Scala是如何支持这些额外的功能呢，答案是对隐式转换的系统化使用，数组并不能假装自己是序列，因为原生数组的数据类型表示并不是Seq的子类型，每当数组被用作Seq时，它都会被隐式的包成Seq的子类。这个子类的名称是 scala.collection.mutable.WrappedArray

```scala
scala> val seq: Seq[Int] = a1
seq: Seq[Int] = WrappedArray(1, 2, 3)
scala> val a4: Array[Int] = s.toArray
a4: Array[Int] = Array(1, 2, 3)
scala> a1 eq a4
res1: Boolean = true
```

上面的例子说明数组与序列是兼容的，因为数组可以隐式转换为WrappedArray。反之可以使用Traversable提供的toArray方法将WrappedArray转换为数组。REPL最后一行表明，隐式转换与toArray方法作用相互抵消.

数组与序列兼容，并支持所有序列操作的方法，你现在应该已经了然于胸。那泛型呢？在Java中你不可以定义一个以T为类型参数的`T[]`。那么Scala的`Array[T]`是如何做的呢？事实上一个像`Array[T] `的泛型数组在运行时态可任意为Java的八个原始数组类型像`byte[]`, `short[]`, `char[]`, `int[]`, `long[]`, `float[]`, `double[]`, `boolean[]`,甚至它可以是一个对象数组。最常见的运行时态类型是AnyRef ，它包括了所有的这些类型（相当于java.lang.Object），因此这样的类型可以通过Scala编译器映射到`Array[T]`.在运行时，当`Array[T]`类型的数组元素被访问或更新时，就会有一个序列的类型测试用于确定真正的数组类型，随后就是java中的正确的数组操作。这些类型测试会影响数组操作的效率。这意味着如果你需要更大的性能，你应该更喜欢具体而明确的泛型数组。代表通用的泛型数组是不够的，因此，也必然有一种方式去创造泛型数组。这是一个更难的问题，需要一点点的帮助你。为了说明这个问题，考虑下面用一个通用的方法去创造数组的尝试。





### 8.相等性

集合类库对于相等性和哈希的处理方式是一致的。首先将集合分为集，映射和序列等不同类目，不同类目下的结合永远不相等。在相同类目下，当且集合拥有相同的元素时才相等（对序列而言，不光要元素相同，顺序也要先沟通，。例如 List(1,2,3) 永远不等于Set(1,2,3) . 而 List(1,2,3)  == Vector(1,2,3), 而HashSet(1,2) == TreeSet(2,1).

至于集合是不是可变的并不影响检查相等性。对可变集合而言，相等性的判断仅取决于执行相等性判断当时的元素。这意味着，随着元素的添加和移除，可变集合会在不同点和不同集合相等。





### 9.视图

transformer 可以通过两种主要的方式实现： 严格的和非严格的（惰性的）。严格的变换器会构造出带有所有元素的新集合。而非严格的只是构造出结果的一个代理，其结果会按需构造出来。

```scala
def lazyMap[T, U](coll: Iterable[T], f: T => U) = {
  new Iterable[U]{
    def iterator = coll.iterator map f
  }
}
```

视图是一种特殊的集合，他代表某个基础集合，但是用惰性的方式实现所有的变换器。要想从集合种获取他的视图，可以对集合使用view方法，如果 xs 是某个集合，那么xs.view 就是同一个集合但是所有变换器都是按惰性的方式实现的。通过v,view调用会产生一个SeqView ,即一个惰性求值的Seq,。 SeqView类型有两个类型参数，第一个类型参数显示了该试图的元素类型，**而第二个类型参数 Vector[int]显示了当你强转该视图时将取回的类型构造器。**通过 force操作可以显示view的值。

视图的第二个用途是针对可变序列，这类试图的许多变化函数提供了对元素序列的一个窗口，可以哦用来有选择的对该序列的某些元素进行更新

```scala
scala> val arr = (0 to 9).toArray
arr: Array[Int] = Array(0, 1, 2, 3, 4, 5, 6, 7, 8, 9)

scala> val subarr = arr.view.slice(3,6)
subarr: scala.collection.mutable.IndexedSeqView[Int,Array[Int]] = SeqViewS(...)

scala> def negate(xs: collection.mutable.Seq[Int]) = {
     | for(i <- 0 until xs.length) xs(i) = -xs(i)
     | }
negate: (xs: scala.collection.mutable.Seq[Int])Unit

scala> negate(subarr)
res183: Array[Int] = Array(0, 1, 2, -3, -4, -5, 6, 7, 8, 9)
```

**scala 从2.8开始规定， 除了 Streams 之外的所有集合都是严格求值的。从严格求值的集合到惰性求值的唯一方式就是通过 view 方法， 往回走的唯一方式是 通过  foreach 方法。总的来说，视图是一个用来调和效率和模块化之间的矛盾的强大工具，不过为了避免被延迟求值的各种细节纠缠，应该将视图的使用局限在两种场景，最好避免在既创建新的集合又有副作用的场景下混用视图和各种集合操作。**

- **在集合变换没有副作用的纯函数式的代码中应用视图。**
- **对所有修改都是显式执行的可变几何使用视图。**



### 10.迭代器

**迭代器并不是集合，而是逐个访问元素的一种方式，迭代器it的两个基本操作是next和hasNext， 如果迭代器提供了一个map方法，返回一个新的迭代器，遍历新的迭代器以后，原来的迭代也同样会被推进到末端，变成 empty-iterator。**

**只有一个标准操作duplicate 允许重用同一个迭代器： val(it1, it2) = it.duplicate。 对 duplicate的调用会给你两个迭代器，其中每一个都会返回跟迭代器it完全相同的元素，这两个迭代器是完全相互独立的，推进一个不会影响另外一个。**

每个迭代器都可以被转成带缓冲的 迭代器，方法是调用其 buffered 方法。其中包含一个head方法，可以访问 it  的下一个对象但却不会将it 推进到下一步，调用next 才会往下走。类似stack中的peek方法。





## 4.IO

```scala
import scala.io.Source
//读取文件的常规操作
val filename = "fileopen.scala"
for (line <- Source.fromFile(filename).getLines) {
  println(line)
}
val fileContents = Source.fromFile(filename).getLines.mkString

val bufferedSource = Source.fromFile("example.txt")  //获得Buffer流对象
for (line <- bufferedSource.getLines) { println(line.toUpperCase) }
bufferedSource.close


//写文件
//scala 中没有直接的写文件的API，继承自Java的写工具有两个类 PrintWriter 和 FileWriter两个类。
import java.io._ 
val pw = new PrintWriter(new File("E:\\hello.txt"))
pw.write("hello scala")
pw.write("\nhello world")
pw.close()
    
val file = new File("E:\\hello1.txt")
val bw = new BufferedWriter(new FileWriter(file))
bw.write("kuzhijie\nBob\nTom\tPenny")
bw.close()

//对于读写二进制文件，同样是继承自Java的方法。
object CopyBytes extends App{
  var in = None: Option[FileInputStream]
  var out = None: Option[FileOutputStream]
  try{
    in = Some(new FileInputStream("hello.txt"))
    out = Some(new FileInputStream("hello.copy.txt"))
    var c = 0
    while({c = in.get.read; c != -1}){
      out.get.write(c)
    }
  }catch {
    case e: IOException => e.printStackTrace
  } finally {
    println("entered finally ...")
    if (in.isDefined) in.get.close
    if (out.isDefined) out.get.close
  } 
}

//进行后缀筛选
import java.io.File
def getListFiles1(dir: File, extensions: List[String]): List[File] = {
  dir.listFiles.filter(_.isFile).toList.filter{
    file => extensions.exists(file.getName.endsWith(_))
  }
}


//递归列出子母录中所有的目录
import java.io.File
def getListOfSubDirectories(dir: File): List[String] = 
dir.listFiles
	 .filter(_.isDirectory)
   .map(_.getName)
   .toList
```







## 6.类型参数化



### 1. 函数式队列

函数式队列是一种数据结构，支持 **head  tail enqueue**（返回一个将给定元素追加到队尾的新队列。类似于List中的 **::**  操作）三种操作。纯函数式队列和列表有一些相似性，他们都被称作完全持久化的数据结果，经过扩展或者修改之后，老版本将继续可用。不过列表用 :: 在头部扩展，而队列在用enqueue在队尾扩展。



```scala
class SlowAppendQueue[T](elems: List[T]) {  //效率低
  def head = elems.head
  def tail = new SlowAppendQueue(elems.tail) //返回除第一个数据之外的列表
  def enqueue(x: T) = new SlowAppendQueue[T](elems ::: List(x))
}

//将list首先翻转再传入。效率仍然不高， enqueue操作是常量时间，但是head和tail操作不是/
class SlowHeadQueue[T](smele: List[T]){
  def head = smele.last
  def tail = new SlowHeadQueue[T](smele.init)
  def enqueue(x: T) = new SlowHeadQueue[T](x :: smele)
}

trait Queue[T]{
  def head: T
  def tail: Queue[T]
  def enqueue(x: T): Queue[T]
}

object Queue{
  def apply[T](xs: T*) = new QueueImp[T](xs.toList, Nil)
  private class QueueImp[T] (private val leading: List[T], private val trailing: List[T])
  extends Queue[T]{
    def mirror =
      if (leading.isEmpty)
        new QueueImp(trailing.reverse, Nil)
      else
        this

    def head = mirror.leading.head
    def tail:QueueImp[T] = {
      val q = mirror
      new QueueImp(q.leading.tail, q.trailing)
    }
    def enqueue(x:T) ={
      new QueueImp(leading, x :: trailing)
    }
  }

//Queue是一个特质，而Queue[String]是一个类型，Queue[String]是一个类型。Queue也被称作类型构造方法，因此我们可以通过指定类型参数来构造一个类型（这和通过指定值参数来构造对象实例的普通构造方法的理由是一样的。）
  def main(args: Array[String]): Unit = {
    def doesNotCompile(q: Queue[AnyVal]) = {}
  }
}
```





### 2.型变

**型变是复杂类型的子类型关系于其组件类型的子类型关系的相关性。Scala支持泛型类的类型参数的型变注释，允许他们是协变的，逆变的， 或者在没有使用注释的情况下是不变的，在类型系统中使用型变允许我们在复杂类型间建立值观的连接，而缺乏泛型则会限制类抽象的重用性。**

**逆变： 通过使用注释 -A ,可以使得一个泛型类的类型参数 A 成为逆变，与协变类似。这汇在类以及其类型参数之间创建一个子类型关系，但其作用与协变完全相反。 也就是说，对于某个类 `class Writer[-A]` ，使 `A` 逆变意味着对于两种类型 `A` 和 `B`，如果 `A` 是 `B` 的子类型，那么 `Writer[B]` 是 `Writer[A]` 的子类型。**

**不变：默认情况下，Scala中的泛型类是不变的。 这意味着它们既不是协变的也不是逆变的。 在下例中，类 `Container` 是不变的。 `Container[Cat]` *不是* `Container[Animal]`，反之亦然**

```scala
abstract class Animal{
  def name: String
}
case class Cat(name: String) extends Animal
case class Dog(name: String) extends Animal

abstract class Printer[-A]{     //定义print抽象方法的抽象类
  def print(value: A): Unit
}

class AnimalPrinter extends Printer[Animal]{
  override def print(value: Animal): Unit =
    println("the animal's name is: " + value.name)
}

class CatPrinter extends Printer[Cat] {
  override def print(value: Cat): Unit =
    println("the cat's name is: " + value.name)
}

class Container[A](value: A){
  private var _value: A = value
  def getValue: A = _value
  def setValue(value: A): Unit ={_value = value}
}

object CovarianceTest extends App{
  //协变测试
  def printAnimalNames(animals: List[Animal]): Unit={
    animals.foreach(animal => println(animal.name))
  }
  val cats: List[Cat] = List(Cat("Whiskers"), Cat("Tom"))
  val dogs: List[Dog] = List(Dog("Fido"), Dog("Rex"))
  printAnimalNames(cats)
  printAnimalNames(dogs)

  //逆变测试
  val myCat: Cat = Cat("Boot")
  def printMyCat(printer: Printer[Cat]): Unit ={
    printer.print(myCat)
  }

  val catPrinter: Printer[Cat] = new CatPrinter
  val animalPrinter: Printer[Animal] = new AnimalPrinter
  printMyCat(catPrinter)
  printMyCat(animalPrinter)

  val catContainer: Container[Cat] = new Container[Cat](Cat("Felix"))
  val animalContainer: Container[Animal] = catContainer  //此处会报错，类型不符
  catContainer.setValue(Cat("Spot"))
  val cat: Cat = catContainer.getValue
}
```



### 3.类型边界

在Scala中，类型参数和抽象类型都可以有一个类型边界的约束，这种类型边界在限制类型变量实际取值的同时还能展露类型成员的更多信息。 比如**像 T <: A 这样声明的类型上界表示类型变量T 应该是类型A的子类型。**  

**[类型上界](https://docs.scala-lang.org/zh-cn/tour/upper-type-bounds.html) 将类型限制为另一种类型的子类型，而 *类型下界* 将类型声明为另一种类型的超类型。 术语 `B >: A` 表示类型参数 `B` 或抽象类型 `B` 是类型 `A` 的超类型。 在大多数情况下，`A` 将是类的类型参数，而 `B` 将是方法的类型参数。**

```Scala
//类型下界测试
abstract class Animal {
 def name: String
}

abstract class Pet extends Animal {}

class Cat extends Pet {
  override def name: String = "Cat"
}

class Dog extends Pet {
  override def name: String = "Dog"
}

class Lion extends Animal {
  override def name: String = "Lion"
}

class PetContainer[P <: Pet](p: P) {
  def pet: P = p
}

val dogContainer = new PetContainer[Dog](new Dog)
val catContainer = new PetContainer[Cat](new Cat)


//类型下界测试
trait Node[+B] {
  def prepend(elem: B): Node[B]
}
case class ListNode[+B](h:B, t:Node[B]) extends Node[B]{
  def prepend(elem: B): ListNode[B] = ListNode(elem,this)
  def head: B = h
  def tail: Node[B] = t
}
case class Nil[+B]() extends Node[B] {
  def prepend(elem: B): ListNode[B] = ListNode(elem, this)
}
```



## 7.抽象成员



Java中允许我们声明抽象方法，scala也允许我们声明这样的方法，不过Scala走的更远，将这个概念完全泛化了，除了方法外，还可以声明抽象字段甚至抽象类型作为类和特质的成员。

抽象val 的声明看起来像是一个抽象的无参方法声明。但是抽象 val 限制了它的合法实现： 任何实现都必须是一个val 定义，而不能是var , def。 反过来var 和 def 定义可以被 val 重新覆盖。

```scala
val initial : String
def initial : String

abstract class Fruit{
  val v : String
  def m : String
}
abstract class BadApple extends Fruit {
  def V : String  //失败，不允许的操作 
  val m : String  //OK
}
```



**惰性val**

我们可以用与初始化字段来精确模拟类构造方法入参的初始化行为。可以将val 定义成惰性可以实现。在val 前面加上 lazy ，则该val的初始化就别延迟到第一次访问x的时候，这和x用def 定义成无参方法的情况类似。不过惰性的val不会被多次求值多次。

```scala 
trait LazyRationalTrait{
  val numerArg: Int
  val denomArg: Int
  //require(denomArg != 0)
  private def gcd(a:Int, b:Int): Int={
    if(b == 0) a else gcd(b, a % b)
  }
  private lazy val g = gcd(numerArg, denomArg)
  lazy val numer = numerArg / g
  lazy val denom = denomArg / g
  override def toString = numer + "/" + denom
}

scala> val x = 1
scala> new RationalTrait{  //并非是在new的时候时被初始化， denom和numer都是在第一次被调用的时候被初始化，此时 x 的值已经被传入。 Lazy可以显示的改变变量的初始化顺序。
       | val numerArg = 1 * x
       | val denomArg = 2 * x }
res4: LazyRationalTrait = 1/2
```

**不过这个优势仅在惰性的val 的初始化既不产生副作用，也不依赖副作用的时候有效，在有副作用时，初始化顺序就变的重要了。惰性的 val 是对函数式对象的完美补充，对函数式对象而言初始化顺序并不重要，只要最终所有的内容都被正常初始化即可，对那些以指令式风格为主的代码而言，惰性的val 就没有那么适用了。**



**用抽像类型对合适的食物建模**

```scala
class Food{} //定义食物
abstract animal extends Food{  //定义动物类和吃方法
  type SuitableFood <: Food   //确定 food 类为 SuitableFood 的类型上界。
  def eat(food: SuitableFood)
}

class Grass extends Food  //定义草食物
class BigGrass extends Grass

class Fish extends Food
class BigFish extends Fish

class Cow extends animal{
  type SuitableFood = Grass
  override def eat(food: SuitableFood): Unit= {}
}

object AbstractDemo1 {
  def main(args: Array[String]): Unit = {
    val a = new Cow
    a eat (new BigFish) //会报错， 如果将 SuitableFood 改为 fish 或者 food 就没问题，
    a.eat(new BigGrass)  // cow 类调用 SuitableFood 的子类是被允许的。
  }
}

```

**animal的类定义让 Animal只能吃那些适合它吃的食物，至于什么是合适的食物，并不能在Animal这个层次确定，因此 SuitableFood 被建模成了一个抽象类型，意味着 Animal子类中任何对 SuitableFood 的具体实例化都必须是Grass的子类。有了Animal 的定义，可以继续定义具体动物类，并在类中可以 将 suitableFood 定义为food 任意级别的子类。就可以控制什么动物吃什么类型的食物了。**

**定义SuitableFood以后， 任何extends Animal类的新类中的eat 方法传入的参数只能是 SuitableFood类或者它的子类。** 



在scala 中 内部类的寻址是通过 Outer#Inner 这样的表达式， 而不是Java的 Outer.Inner 方法。此方法只为对象保留。



**枚举**

Scala并不需要特殊的语法来表示枚举，而是在标准库中提供了一个类： **scala.Enumeration**

**创建新枚举的方式是定义一个扩展自该类的对象。Enumeration 定义了一个名为 Value 的内部类，跟这个内部类同名的不带参数的Value 方法每次都返回这个类的全新实例。换句话说，类似于Color.Red 这样的值的类型为Color.Value. 而Color.Value是所有定义在Color对象中的值的类型，他是一个路径依赖类型，其中 Color是路径，而Value是依赖的类型。**

枚举的值从0开始编号，可以通过枚举值的id的方式获取 这个编号。同样可以反过来利用编号去获取对应的枚举值。

```scala
object Color extends Enumeration{
  var Red = Value("red")
  val Green = Value("green")
  val Blue = Value("blue")
}
object Direction extends Enumeration{
  val North, East, South, West = Value
}
println(Direction.East.id) // 1
println(Direction(1)) //  East
```





## 8.隐式转换和隐式参数

隐式规则：

- **标记规则：** 只有标记为 implict 的定义才可用

- **作用域规则：** 被插入的隐式转换必须是的当前作用域的**单个标识符（single identifier）**，或者跟隐式转换的原类型或者目标类型有关联。scala 编译器只会考虑那些在作用域内的隐式转换。事实上，对于类库而言，常见的做法是提供一个包含了了一些有用的隐式转换的 Preamble 对象。这样使用这个类库的代码就可以通过一个  import Preamble._ 来访问该类库的隐式转换。

  作用域规则有助于模块化的推理。

- **每次一个规则： 每次只能有一个隐式定义被插入。** 不过可以通过让隐式定义包含隐式参数的方法绕过这个限制。

- **显式优先规则： 只要代码按编写的样子能过通过类型检查，就不后尝试隐式定义。**



Scala总共会在三个地方会使用隐式定义：

1. 转换到一个预期的类型

2. 对某个成员选择接收端（字段，方法调用等）的转换。主要有两个主要用途。

   - 接收端转换允许我们更平滑的将新类继承到已有的类继承关系图谱当中。
   - 他们支持在语言中编写原生的领域特定语言（DSL）

   

3. 隐式参数。编译器会插入隐式定义的最后一个地方是参数列表。

   ```scala
   class preferredPrompt(val preference: String)
   class preferredDrink(val preference: String)
   object Greeter{
     def greet(name: String)(implicit prompt: preferredPrompt, drink: preferredDrink) = {
       println("welcome, " + name + ". the system is ready.")
       println("why not enjoy a cup of " + drink.preference + "?")
       println(prompt.preference)
     }
   }
   
   object JoesPref {
     implicit val prompt = new preferredPrompt("yes master>")  //利用编译器隐式的填充确实的消息列表
     implicit val drink = new preferredDrink("tea")
   }
   
   scala> import JoesPref._  //将其引入作用域。
   import JoesPref._
   
   scala> Greeter.greet("Bob")
   welcome, Bob. the system is ready.
   why not enjoy a cup of yes master>?
   yes master>
   
   
   //关于隐式参数，他们最常用的使用的场景是提供关于在更靠前的参数的vans胡里欸博爱中已经显式的提到的类型的信息。下面是一个找到传入List中最大元素的函数。其中implici传入的是排序方式。这样在实际使用时，第二个参数可以省略，因为它可以根据T的类型自动推断处List该适用于什么类型的排序方式。
   
   def maxListImpParm[T](elements: List[T]) (implicit ordering: Ordering[T]): T={
       elements match {
         case List() => throw new IllegalArgumentException("empty list")
         case List(x) => x
         case x :: rest =>
           val maxRest = maxListImpParm(rest)(ordering)//(ordering)可以省略
           if (ordering.gt(x, maxRest)) x
           else maxRest
        }
     }
   //还有一种方法可以去掉对ordering的第二次调用，这世界标准类库中定义的如下方法：
   def implicitly[T] (implicit t: T) = t
   //调用 implicitly[Foo]的作用时编译器会查找一个类型为Foo的隐式定义，然后他会用这个对象来调用 implicitly 方法，这个方法在将这个对象返回。这样可以在想要在当前作用域找到类型为Foo 的隐式对象时直接写 implicitly[Foo]。
   def maxList[T](elements: List)(implicit comparator: Ordering[T]): T = ...
   ```

   单例对象 JoesPref 声明了两个 隐式的 val ，不过，这要这些定义不以单个标识符的形式出现在作用域内，他们就不会被用来填充greet的缺失参数列表。

   **注意，当我们在参数上使用implicit时，编译器不仅会尝试给这个参数提供一个隐式值，还会吧这个参数当作一个可以在方法体中使用的隐式定义。也就是说可以省去方法体中对ordering 的第一次使用。**

   
