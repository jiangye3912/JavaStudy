[TOC]



# 1 Java编程

## 1.1 编程语言

Java是一种高级语言（high-level language），其他高级语言还有Python、C、C++、Ruby和JavaScript。

要想运行用高级语言编写的程序，必须将其转换为低级语言（low-level language），即“机器语言”。这种转换需要一定的时间，这是高级语言的一个小小的缺点，但高级语言有两个优点：

- 用高级语言编程容易得多：编写程序所需要的时间更短，程序更简洁、更容易理解，同时更容易确保程序正确无误；
- 高级语言是可移植的（portable），这意味着用高级语言编写的程序只需做少量修改甚至无需修改，就可在不同类型的计算机上运行。用低级语言编写的程序只能在一种计算机上运行，这种程序必须重写才能在其他计算机上运行。

有两种将高级语言转换为低级语言的程序：解释器和编译器。解释器（interpreter）读取并执行用高级语言编写的程序，这意味着程序怎么说它就怎么做。它每次处理程序的一小部分，即交替地读取代码行并执行计算。下图展示了解释器的结构。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230310102913689.png" alt="image-20230310102913689" style="zoom: 50%;" />

相反，编译器（compiler）读取并转换整个程序，然后才开始运行程序。在这种情况下，用高级语言编写的程序称为源代码（source code），而转换得到的程序称为目标代码（object code）或可执行程序（executable）。程序编译后可反复执行，无需在每次执行前都进行转换。因此，编译型程序的运行速度通常比解释型程序更快。

Java 既是解释型的又是编译型的。Java 编译器不将程序直接转换为机器语言，而是生成字节码（byte code）。字节码类似于机器语言，解释起来既轻松又快捷，同时也是可移植的，即可在一台机器上编译程序，在另一台机器上运行生成的字节码。运行字节码的解释器被称为 Java 虚拟机（Java Virtual Machine，JVM）。

![image-20230310103135293](C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230310103135293.png)

上图展示了这个过程包含的步骤。这个过程看似复杂，但在大多数程序开发环境中，这些步骤都是自动完成的：通常只需按一下按钮或输入简单的命令，就能编译并运行程序。然而，知道幕后执行了哪些步骤很重要，这样就可以在出现问题时找出问题所在。

## 1.2 Hello World程序

代码：

```java
public class Work1 {
    public static void main(String[] args) {
        System.out.println("Hello,World!");
    }
}
```

输出结果：

```
Hello，World！
```

Java 程序由类定义和方法定义组成，而其中的方法由语句（statement）组成。语句是一行执行基本操作的代码。在 Hello World 程序中，这是一条打印语句（print statement），在屏幕上显示一条消息：

```java
System.out.println("Hello,World!"); 
```

System.out.println 在屏幕上显示结果，其中的 println 表示“打印一行”。令人迷惑的是，打印既可以表示“在屏幕上显示”，也可以表示“发送到打印机”。在本书中，表示输出到屏幕上时，我们尽可能说“显示”。与大多数语句一样，打印语句也以分号（;）结尾。Java 是区分大小写的，这意味着大写和小写是不同的。在前面的示例中，System 的首字母必须大写，使用 system 或 SYSTEM 都行不通。方法（method）是一系列命名的语句。前面的程序定义了一个名为main 的方法：

```java
public static void main(String[] args) 
```

方法 main 比较特殊：程序运行时，首先执行方法 main 中的第一条语句，并在执行完这个方法的最后一条语句后结束。在本书的后文中，你将看到定义了多个方法的程序。类（class）是方法的集合。前面的程序定义了一个名为 Hello 的类。你可以随便给类命名，但根据约定，类名的首字母应大写。类必须与其所属的文件同名，因此前面的类必须存储在文件 Hello.java 中。Java 用大括号（{ 和 }）编组。在 Hello.java 中，外面的大括号包含类定义，而里面的大括号包含方法定义。以双斜线（//）开头的行是注释（comment），它用自然语言编写的文本解释代码。编译器遇到 // 时，将忽略随后到行尾的所有内容。注释对程序的执行没有任何影响，但可以让其他程序员（还有未来的你自己）更容易地明白你要做什么。

## 1.3 显示字符串

方法 main 中可包含任意条语句。例如，要显示多行输出，你可以像下面这样做：

```java
public class Work1 {
    public static void main(String[] args) {
        // 生成一些简单的输出
        System.out.println("Hello,World!"); // 第一行
        System.out.println("How are you?"); // 第二行
    }
}
```

输出结果：

```
Hello,World!
How are you?
```

这个示例表明，除独占一行的注释外，还可在行尾添加注释。用引号括起的内容称为字符串（string），因为它们包含一系列串在一起的字符。字符包括字母、数字、标点、符号、空格、制表符，等等。System.out.println 在指定的字符串末尾添加了一个特殊字符——换行符（newline），其作用是移到下一行开头。如果你不想在末尾添加换行符，可用 print 代替 println：

```java
public class Work1 {
    public static void main(String[] args) {
        System.out.print("Goodby,");
        System.out.println("cruel world.");
    }
}
```

输出结果：

```
Goodby,cruel world.
```

在这个示例中，第一条语句没有添加换行符，因此输出只有一行：Goodbye, cruel world。请注意，第一个字符串末尾有一个空格，这也包含在输出中。

## 1.4 转义序列

可用一行代码显示多行输出，只需告诉 Java 在哪里换行就可以了：

```java
public class Work1 {
    public static void main(String[] args) {
        System.out.print("Hello!\nHow are you doing?\n");
    }
}
```

上述代码的输出为两行，每行都以换行符结尾：

```
Hello!
How are you doing?
```

\n 是一个转义序列（escape sequence），表示特殊字符的字符序列。反斜线让你能够对字符串的内容进行转义。请注意，\n 和 How 之间没有空格；如果在这里添加一个空格，第二行输出的开头将会是一个空格。转义序列的另一个常见用途是在字符串中包含引号。由于双引号标识字符串的开头和结尾，因此，要想在字符串中包含双引号，必须用反斜线对其进行转义。

```java
System.out.print("She said \"Hello!\" to me.");
```

输出结果：

```
She said "Hello!" to me.
```

常见的转义序列：

| `\n` | 换行符 |
| :--- | ------ |
| `\t` | 制表符 |
| `\"` | 双引号 |
| `\\` | 反斜线 |

## 1.5 设置代码格式

在 Java 程序中，有些空格是必不可少的。例如，不同的单词之间至少得有一个空格，因此下面的程序是不合法的：

```java
public class Work1 {
    public static void main(String[] args) {
        System.out.print("Goodbye, ");
        System.out.println("cruel world");
    }
}
```

但其他空格大都是可有可无的。例如，下面的程序完全合法：

```java
public class Goodbye {
public static void main(String[] args) {
System.out.print("Goodbye, ");
System.out.println("cruel world");
}
}
```

换行也是可选的，因此可将前面的代码编写如下：

```java
public class Goodbye { public static void main(String[] args)
{ System.out.print("Goodbye, "); 
System.out.println("cruel world");}}
```

这也是可行的，但程序阅读起来更难了。要以直观的方式组织程序，换行和空格都很重要，使用它们可让程序更容易理解，发生错误时也更容易查找。很多编辑器都自动设置源代码的格式：以一致的方式缩进和换行。例如，在 DrJava（参见附录 A）中，可以按 Ctrl+A 选择所有的代码，再按 Tab 键来缩进代码。

从事大量软件开发工作的组织通常会制定严格的源代码格式设置指南，例如，Google 就发布了针对开源项目的 Java 编码标准，其网址为http://google.github.io/styleguide/javaguide.html。

## 1.6 术语表

| 术语                          | 含义                                                         |
| ----------------------------- | ------------------------------------------------------------ |
| 解决问题                      | 明确地描述问题、找到并描述解决方案的过程。                   |
| 程序(program)                 | 一系列的指令，指定了如何在计算机上执行任务。                 |
| 编程(programming)             | 用问题解决技能创建可执行的计算机程序。                       |
| 计算机科学                    | 科学而实用的计算方法及其应用。                               |
| 算法(algorithm)               | 解决问题的流程或公式，可以涉及计算机，也可以不涉及。         |
| bug                           | 程序中的错误。                                               |
| 调试                          | 找出并消除错误的过程。                                       |
| 高级语言(high-level language) | 人类能够轻松读写的编程语言。                                 |
| 低级语言(low-level language)  | 计算机能够轻松运行的编程语言，也叫“机器语言”或“汇编语言”。   |
| 可移植(portable)              | 程序能够在多种计算机上运行。                                 |
| 解释器(interpreter)           | 指运行用高级语言编写的程序，即每次转换其中的一行并立即执行转换得到的指令。 |
| 编译器(compiler)              | 将用高级语言编写的程序一次性转换为低级语言，供以后执行。     |
| 源代码(source code)           | 用高级语言编写的、未编译的程序。                             |
| 目标代码(object code)         | 编译器转换程序后得到的输出。                                 |
| 可执行代码                    | 可在特定硬件上执行的目标代码的别名。                         |
| 字节码(byte code)             | Java 程序使用的一种特殊目标代码，类似于低级语言，但像高级语言一样是可移植的。 |
| 语句(statement)               | 程序的一部分，指定了算法中的一个步骤。                       |
| 打印语句                      | 将输出显示到屏幕上的语句。                                   |
| 方法(method)                  | 命名的语句序列。                                             |
| 类(class)                     | 就目前而言，指的是一系列相关的方法。（后面你将看到，类并非只包含方法。） |
| 注释(comment)                 | 程序的一部分，包含有关程序的信息，但对程序的运行没有任何影响。 |
| 换行符(newline)               | // 标识文本行尾的特殊字符。                                  |
| 转义序列(escape sequence)     | 在字符串中用于表示特殊字母的编码序列。                       |
| 字符串(string)                | 字符串或串(String)是由数字、字母、下划线组成的一串字符。一般记为 s="a1a2···an"(n>=0)。 |

# 2 变量和运算符

## 2.1 声明变量

编程语言最强大的功能之一是能够定义和操作变量（variable）。变量是存储值（value）的命名位置，其中的值可以是数字、文本、图像、声音和其他类型的数据。要存储值，得先声明变量。

```java
String message;
```

这条语句是一个声明（declaration），因为它声明变量 message 的类型为 String。每个变量都有类型（type），决定了它可以存储什么样的值。例如，类型为 int 的变量可存储整数，而类型为 char 的变量可存储字符。

**有些类型名的首字母大写，有些类型名的首字母小写。**这种差别的含义将在后文中介绍，就目前而言，你只需要确保首字母大小写正确即可，因为没有类型 Int，也没有类型 string。

要声明整型变量，可用如下语法：

```java
int x;
```

其中的 x 是一个随便指定的变量名。一般而言，使用的名称应指出变量的含义。例如，看到下面的声明，你可能就能猜出各个变量将存储什么值：

```java
String firstName;
String lastName;
int hour, minute;
```

这个示例声明了四个变量，其中两个的类型为 String，另外两个的类型为 int。根据约定，对于包含多个单词的变量名，如 firstName，应将每个单词的首字母大写，但第一个单词除外。变量名是区分大小写的，因此，firstName、firstname 和 FirstName 指的是不同的变量。

这个示例还演示了在一行中声明多个同类变量的语法：hour 和 minute都是 int 变量。请注意，每条声明语句都以分号结尾。

你可以随便给变量命名，但大约有 50 个被称为关键词（keyword）的保留词不能用作变量名。这些关键词包括public、class、static、void 和 int，被编译器用来分析程序的结

构。

有关完整的关键词清单，请参阅http://docs.oracle.com/javase/tutorial/java/nutsandbolts/_keywords.html，但不必记住它们。大多数编程编辑器都提供了“语法突出”的功能，即用不同的颜色显示程序的不同部分。

## 2.2 赋值

声明变量后，即可用它们来存储值。为此，可用赋值（assignment）语

句：

```java
message = "Hello!"; // 给变量message指定值"Hello!"
hour = 11; // 将值11赋给变量hour
minute = 59; // 将变量minute的值设置为59
```

这个示例包含三条赋值语句，其中的注释指出了三种解读赋值语句的方式。这里使用的术语可能令人迷惑，但涉及的概念简单易懂。

- 当声明变量时，便创建了一个命名的存储位置。
- 当给变量赋值时，便修改了它的值。

一般而言，**变量和赋给它的值必须是相同的类型**。例如，你不能将字符串存储到变量 mintue 中，也不能将整数存储到变量 message 中。在本书的后文中，你将看到一些违反这条规则的示例。有些字符串看起来像是整数，但其实不是整数，这常常令人迷惑。例如，变量 message 可包含字符串 "123"，这个字符串由字符 '1'、'2'和 '3' 组成，与整数 123 不是同一码事。

```java
message = "123"; // 合法
message = 123; // 非法
```

使用变量前，必须对其进行初始化（initialize，首次赋值）。你可以像前一个示例那样，先声明变量，再赋值；也可以在声明变量的同时给它赋值：

```java
String message = "Hello!";
int hour = 11;
int minute = 59;
```

## 2.2 状态图

相等具有交换性，但赋值并非如此。例如，在数学中，如果 *a*=7，则

7=*a*；而在 Java 中，a=7; 是一条合法的赋值语句，但 7=a; 则不是，因

为赋值语句的左边必须是变量名（存储位置）。

另外，在数学中，相等声明在任何情况下都成立。如果当前 *a*=*b*，那么

在任何情况下 *a* 和 *b* 都相等；而在 Java 中，赋值语句可能导致两个变

量相等，但它们并不一定始终如此。

```java
int a = 5;
int b = a; // 现在a和b相等
a = 3; // a和b不再相等
```

第三行代码修改了 a 的值，但没有修改 b 的值，因此它们不再相等。

程序中的所有变量及其当前值一同组成了程序的状态（state）。下图显示了程序在上述三条语句运行后的状态。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230310141449269.png" alt="image-20230310141449269" style="zoom:50%;" />

显示程序状态的图被称为状态图（state diagram）。每个变量都用一个方框表示，方框内是变量的值，方框外是变量名。状态随程序的运行而变化，因此，应将状态图视为程序执行过程中特定时点的快照。

## 2.4 显示变量

可用 print 或 println 显示变量的值。下面的语句声明了一个名为firstLine 的变量，将值 "Hello, again!" 赋给它，并显示这个值：

```java
String firstLine = "Hello, again!";
System.out.println(firstLine);
```

在说显示变量时，我们通常指的是显示变量的值。要显示变量的名称，必须将其用引号括起。

```java
System.out.print("The value of firstLine is ");
System.out.println(firstLine);
```

这个示例的输出如下：

```
The value of firstLine is Hello, again!
```

不管变量的类型如何，显示其值的语法都相同。例如：

```java
int hour = 11;
int minute = 59;
System.out.print("The current time is ");
System.out.print(hour);
System.out.print(":");
System.out.print(minute);
System.out.println(".");
```

输出结果：

```
The current time is 11:59.
```

**要在同一行输出多个值，通常使用多条 print 语句，并在最后使用一条 println 语句。**千万不要忘了 println 语句！很多计算机都将来自print 的输出存储起来，等遇到 println 后才将整行输出一次性显示出来。如果省略了 println，程序可能在意想不到的时候显示存储的输出，甚至直到结束也不显示任何输出。

## 2.5 算术运算符

运算符（operator）是表示简单计算的符号，例如，加法运算符为 +，减法运算符为 -，乘法运算符为 *，而除法运算符为 /。下面的程序将时间转换为分钟数：

```java
int hour = 11;
int minute = 59;
System.out.print("Number of minutes since midnight: ");
System.out.println(hour * 60 + minute);
```

在这个程序中，hour * 60 + minute 是一个表达式（expression），表示计算将得到的单个值。这个程序运行时，每个变量都被替换为当前值，再执行运算符指定的计算。运算符使用的值称为操作数（operand）。

前述示例的结果如下：

```
Number of minutes since midnight: 719
```

表达式通常由数字、变量和运算符组成。程序编译并执行时，表达式将变成单个值。

例如，表达式 1 + 1 的值为 2。对于表达式 hour - 1，Java 将变量hour 替换为其当前值，因此这个表达式变成 11 - 1，结果为 10。对于表达式 hour * 60 + minute，其中的两个变量都被替换了，整个表达式变为 11 * 60 + 59。先执行乘法运算，因此这个表达式变为 660\+ 59；再执行加法运算，结果为 719。

加法、减法、乘法运算都与你的预期一样，但除法运算可能会让你感到意外。例如，下面的代码片段试图将分钟数转换为小时数：

```java
System.out.print("Fraction of the hour that has passed: ");
System.out.println(minute / 60);
```

输出结果：

```
Fraction of the hour that has passed: 0
```

这样的结果令人感到迷惑。变量 minute 的值为 59，59 除以 60 的结果应为 0.98333，而不是 0。问题在于 **Java 在两个操作数都为整数时执行“整数除法”，而根据设计，整数除法总是向下圆整**，即便这里的结果更接近下一个整数时也是如此。

一种替代方式是，计算百分比而不是小数：

```java
System.out.print("Percent of the hour that has passed: ");
System.out.println(minute * 100 / 60);
```

上述代码的输出如下：

```
Percent of the hour that has passed: 98
```

同样，结果也被向下圆整了，但至少离正确的答案更近了。

## 2.6 浮点数

一种更通用的解决方案是使用浮点（floating-point）数，它可用于表示小数，也可用于表示整数。在 Java 中，默认的浮点类型为 double，它指的是双精度浮点数。double 变量的声明和赋值语法与其他类型的变量相同：

```java
double pi;
pi = 3.14159;
```

只要有一个操作数为 double 值，Java 就执行“浮点除法”，因此，我们可以用如下方式来解决 2.5 节中的问题：

```java
double minute = 59.0;
System.out.print("Fraction of the hour that has passed: ");
System.out.println(minute / 60.0);
```

输出如下：

```
Fraction of the hour that has passed: 0.9833333333333333
```

虽然浮点数很有用，但也可能让人感到迷惑。例如，Java 区分整数 1 和浮点数 1.0，即使它们看起来是同一个数字。它们属于不同的数据类型，而严格来说，你不能将一种类型的值赋给另一种类型的变量。

下面的语句是非法的，因为左边是一个 int 变量，而右边是一个double 值：

```java
int x = 1.1; // 编译错误
```

这种规则很容易忘记，因为 Java 在很多情况下会自动转换类型：

```java
double y = 1; // 合法，但这是一种糟糕的做法
```

这个示例原本应该是非法的，但由于 Java 自动将 int 值 1 转换为double 值 1.0，使得这个示例变得合法了。这样的宽容是十分便利的，但常会给初学者带来问题，例如：

```java
double y = 1 / 3; // 常见的错误
```

你可能会认为变量 y 的值为 0.333333——一个合法的浮点值，但实际上其值为 0。右边的表达式将两个整数相除，因此 Java 执行整数除法，结果为 int 值 0。这个结果被转换为 double 值 0.0，再赋给变量 y。**[先运算等号右边的1/3，1和3都是整型数据，1/3后结果是0.333333不是整型数据，所以变成整型会直接舍弃小数部分，变为0，然后再赋值给y，所以y等于0]**

对于这种问题，其中一种解决方案是将右边的表达式变成浮点表达式，如下所示，这样变量 y 将像预期的那样被设置为 0.333333：

```java
double y = 1.0 / 3.0; // 正确
```

作为一种编程风格，在任何情况下都应将浮点值赋给浮点变量。编译器并没有要求必须这样做，但如果不这样做的话，不知什么时候一个简单的错误就可能阴魂不散，给你带来麻烦。

## 2.7 舍入误差

大多数浮点数只能大致正确地表示。有些数字，如果不是特别大的整数，可以准确地表示。但循环小数（如 1/3）和无理数（如 π）不能准确地表示。为表示这些数字，计算机必须将其舍入到最接近的浮点数。

所需数字和实际得到的浮点数之间的差称为舍入误差（roundingerror）。例如，以下两条语句应该是等价的：

```java
System.out.println(0.1 * 10);
System.out.println(0.1 + 0.1 + 0.1 + 0.1 + 0.1
                   + 0.1 + 0.1 + 0.1 + 0.1 + 0.1);
```

但在很多计算机上，它们的输出如下：

```
1.0
0.9999999999999999
```

原因是 0.1 在十进制中为有限小数，但在二进制中为循环小数，因此其浮点数表示只是近似的。将近似值相加会逐渐累积舍入误差。

在很多应用领域，如计算机图形学、加密、统计分析和多媒体渲染，使用浮点数算术利大于弊。**但如果要求绝对精确，应使用整数。**例如，查看余额为 123.45 美元的银行账户：

```java
double balance = 123.45; // 可能存在舍入误差
```

在这个示例中，随着不断地对变量执行算术运算（如存款和取款），它存储的值将不再准确。这可能会激怒顾客，甚至引发诉讼。为避免这种问题，可以用整数来表示余额：

```java
int balance = 12345; // 美分数
```

只要美分数不超过变量 int 可表示的最大值（约 20 亿），就可以使用这种解决方案。

## 2.8 字符串运算符

一般而言，不能对字符串执行数学运算，即便对那些看起来像数字的字符串亦是如此。下面的表达式是非法的：

```java
"Hello" - 1			"World" / 123 		"Hello" * "World"
```

**运算符 + 可用于字符串**，但其所作所为可能出乎意料。用于字符串时，运算符 + 执行串接（concatenation），即**首尾相连**，因此 "Hello, " +"World!" 的结果为字符串 "Hello, World!"。

```java
System.out.println("Hello," + "world!");
// 输出为Hello,world!
```

再举一个例子。如果你声明了类型为 String 的变量 name，则表达式"Hello, " + name 会将变量 name 的值附加在字符串 hello 的后面，从而生成个性化的问候。

```java
public class Work1 {
    public static void main(String[] args) {
        String name = "mzk";
        System.out.println("Hello," + name);
    }
}
// 输出为：Hello,mzk
```

鉴于对数字和字符串都定义了加法运算，因此 Java 可能执行意料之外的自动转换：

```java
System.out.println(1 + 2 + "Hello");
// 输出为：3Hello
System.out.println("Hello" + 1 + 2);
// 输出为：Hello12
System.out.println(1 + "Hello" + 2);
// 输出为：1Hello2
```

Java 按从左到右的顺序执行这些运算。在第 1 行中，1 + 2 等于 3，而3 + "Hello" 的结果为 "3Hello"；在第 2 行中，"Hello" + 1 的结果为 "Hello1"，而"Hello1" + 2 结果为"Hello12";在第3行中，1+"Hello"的结果为"1Hello"，而"1Hello"+2的结果为"1Hello2"。

表达式包含多个运算符时，将根据运算顺序（order of operation）计算表达式。一般而言，Java 按从左到右的顺序执行运算（如 2.7 节所示），但对于数值运算符，Java 遵循如下的数学规则。

- 乘除运算的优先级高于加减运算，这意味着先乘除后加减。因此 1\+ 2 * 3 的结果为 7，而不是 9，而 2 + 4 / 2 的结果为 4，而不是 3。
- 运算符的优先级相同时，按从左到右的顺序执行。因此，表达式minute * 100 / 60 先执行乘法运算；如果 minute 的值为 59，这个表达式将变为 5900 / 60，结果为 98。如果按从右到左的顺序执行这些运算，将得到错误的结果 59 * 1。
- 要想改变默认的运算优先级或对默认的运算优先级不太确定时，可使用括号。首先计算括号内的表达式，因此 (1 + 2) * 3 的结果为 9。还可用括号让表达式更容易理解，如 (minute * 100) /60，虽然就这个表达式而言，用不用括号对结果并没有影响。

别费劲地去记运算符的优先级，尤其是除算术运算符外的其他运算符。如果表达式的含义不那么明显，可用括号让它清晰起来。

## 2.9 组合

前面分别介绍了编程语言的一些元素——变量、表达式和语句，但没有讨论如何结合使用它们。

编程语言最有用的功能之一是能够组合（compose）小型构件。例如，在知道如何将数字相乘以及如何显示值后，我们可以将这些操作放在一条语句中：

```java
System.out.println(17 * 3);
// 输出结果为：51
```

任何算术表达式都可用于打印语句中，我们见过这样的例子：

```java
System.out.println(hour * 60 + minute);
```

还可将表达式放在赋值语句的右边：

```java
int percentage;
percentage = (minute * 100) / 60;
```

**赋值语句的左边必须是变量名，不能是表达式。**这是因为赋值语句的左边要指定将结果放在什么地方，而表达式表示的并非存储位置。

```java
hour = minute + 1; // 正确
minute + 1 = hour; // 导致编译错误
```

就目前而言，能够将操作组合起来好像没什么大不了的，但在本书的后文中你将了解到，这让我们能够编写简洁的代码以执行复杂的计算。不过，也别忘乎所以，冗长而复杂的表达式可能会难以理解和调试。

## 2.10 错误类型

程序中可能出现的错误有三种：编译时错误、运行时错误和逻辑错误。区分这些错误可以更快地找出错误。

编译时错误（compile-time error）指的是因违反 Java 语法（syntax）规则而导致的错误。例如，括号和大括号必须成对出现，所以 (1 + 2)是合法的，而 8) 是非法的。8) 导致程序无法编译，而编译器将显示一条错误消息。

编译器显示的错误消息通常会指出错误出现在程序的什么地方，有时还可以准确地指出错误。我们来重温一下第 1 章中的 Hello World 程序。

```java
public class Hello {
public static void main(String[] args) {
// 生成一些简单的输出
System.out.println("Hello, World!");
}
}
```

如果遗漏了打印语句末尾的分号，将出现类似于以下的错误消息：

```
File: Hello.java [line: 5]
Error: ';' expected
```

这条错误消息准确地指出了错误的位置，还指出了是什么样的错误。

然而，并非所有的错误消息都是容易理解的。有时编译器报告的错误位置不准确；有时对错误的描述模棱两可，几乎没什么帮助。

例如，如果遗漏了方法 main 末尾（第 6 行）的右大括号，可能出现类似于以下的错误消息：

```
File: Hello.java [line: 7]
Error: reached end of file while parsing
```

这里有两个问题。首先，这条错误消息是从编译器的角度而不是你的角度生成的。分析（

parsing）指的是在转换前读取程序的过程；如果编译器到达文件末尾后分析还在进行的话，那么就意味着程序遗漏了什么东西，但编译器不知道遗漏了什么，也不知道在何处遗漏的。它认为错误发生在程序末尾（第 7 行），但遗漏的大括号应该在前一行。

错误消息提供了很有用的信息，你应尽力阅读并理解它们，但也不能将它们奉为圭臬。

刚从事编程的几周内，你可能会为找出编译错误花费大量的时间，但随着经验越来越丰富，你犯的错误将越来越少，找出错误的速度也将越来越快。

第二种错误是运行时错误（run-time error），因其要等到程序运行后才会出现而得名。在 Java 中，这种错误发生在解释器执行字节码期间，也被称为异常，因为它们通常表明出现了异常而糟糕的情况。

前几章的简单程序中很少出现运行时错误，因此可能需要过段时间才能见到它们。运行时错误发生时，解释器将显示一条错误消息，指出在什么地方出现了什么问题。

例如，如果你不小心将零用作了除数，将出现类似于以下的错误消息：

```
Exception in thread "main" java.lang.ArithmeticException: / by zero at Hello.main(Hello.java:5)
```

上述第 1 行指出了异常的名称`java.lang.ArithmeticException`，还具体地指出了发生的情况`/ by zero`（除以零）。接下来的一行指出了问题所在的方法；`Hello.main` 指的是 Hello 类的方法 main；还指出了这个方法是在哪个文件（Hello.java）中定义的以及问题出现在第几行。

有些错误消息还包含无意义的信息，因此你面临的挑战之一是确定有用的部分，而不被多余的信息搞得不知所措。另外别忘了，导致程序崩溃的代码行可能并不是需要修改的代码行。

第三种错误是逻辑错误（logic error）。存在逻辑错误的程序能够通过编译，且运行时不会出现错误消息，但不会做正确的事。相反，你让它怎么做，它就怎么做。例如，下面这个版本的 Hello World 程序存在一个逻辑错误：

```java
public class Hello {
    
	public static void main(String[] args) {
		System.out.println("Hello, ");
		System.out.println("World!");
}
}
```

这个程序能够通过编译并运行，但输出如下：

```
Hello,
World!
```

如果我们要在一行中显示全部输出，那么上述输出就不正确。问题出在第 1 行，它用的是 println，而我们原本想用的是 print（参见 1.3节中的 goodbye world 示例）。

有时很难找出逻辑错误，因为你必须进行反向推导：根据输出结果推断程序行为不正确的原因，并确定如何让它的行为正确无误。编译器和解释器在这方面帮不了你，因为它们并不知道正确的行为是什么样的。

## 2.11 术语表

| 术语                           | 含义                                                         |
| ------------------------------ | ------------------------------------------------------------ |
| 变量(variable)                 | 命名的存储位置。所有变量都有类型，这是在创建变量时声明的。   |
| 值(value)                      | 数字、字符串或其他可存储在变量中的数据。每个值都属于特定的类型，如 int 或 String。 |
| 声明(declaration)              | 创建变量并指定其类型的语句。                                 |
| 类型(type)                     | 从数学角度来说，类型是一个值集。变量的类型决定了它可存储哪些值。 |
| 关键词                         | 编译器用来分析程序的保留词。关键词（如 public、class 和void）不能用作变量名。 |
| 赋值                           | 给变量指定值的语句。                                         |
| 初始化                         | 首次给变量赋值。                                             |
| 状态                           | 程序中的变量及其当前值。                                     |
| 状态图                         | 程序在特定时点的状态的图形表示。                             |
| 运算符                         | 表示计算（如加、乘和字符串串接）的符号。                     |
| 操作数                         | 运算符操作的值。在 Java 中，大多数运算符需要两个操作数。     |
| 表达式                         | 表示单个值的变量、运算符和值的组合。表达式也有类型，这是由表达式包含的运算符和操作数决定的。 |
| 浮点                           | 一种数据类型，表示包含整数部分和小数部分的数字。在 Java中，默认的浮点类型为 double。 |
| 舍入误差                       | 要表示的数字和与之最接近的浮点数之间的差。                   |
| 拼接                           | 将两个值（通常是字符串）首尾相连。                           |
| 运算顺序                       | 决定运算顺序执行的规则。                                     |
| 组合                           | 将简单的表达式和语句合并为复合的表达式和语句。               |
| 语法                           | 程序的结构，即程序包含的单词和符号的排列方式。               |
| 编译时错误(compile-time error) | 导致源代码无法编译的错误，也叫“语法错误”。                   |
| 分析                           | 分析程序的结构，这是编译器做的第一项工作。                   |
| 运行时错误(run-time error)     | 导致程序无法完成运行的错误，也叫“异常”。                     |
| 逻辑错误(logic error)          | 导致程序的行为不符合程序员预期的错误。                       |

# 3 输入和输出

## 3.1 System类

前面一直在使用 `System.out.println`，但你可能没有想过其含义。System 是一个类，提供了与运行程序的系统或环境相关的方法，以及特殊值 System.out，这个值提供了显示输出的方法，其中包括println。

实际上，我们可用 System.out.println 来显示 System.out 的值：

```java
System.out.println(System.out);
```

结果如下：

```
java.io.PrintStream@5594a1b5
```

上述输出表明，System.out 是一个 PrintStream（打印输出流），而 PrintStream是在 java.io 包中定义的。包（package）是一组相关的类；java.io包含用于 I/O（输入和输出）的类。

@ 后面的数字和字母是 System.out 的十六进制地址（address）。值的地址指的是值在计算机内存中的位置，可能随计算机而异。在这个示例中，地址为 5594a1b5，但如果你运行这些代码，可能会得到不同的地址。

如图所示，System 是在文件 System.java 中定义的，而PrintStream 是在文件 PrintStream.java 中定义的。这些文件都包含在Java 库（library）中，Java 库是一个庞大的类集，你可以在程序中使用其中的任何类。
![image-20230313134533582](C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230313134533582.png)

## 3.2 Scanner类

System 类还提供了特殊值 System.in，这是一个 InputStream（字节输入流），提供了从键盘读取输入的方法。这些方法用起来并不那么容易，好在 Java还提供了其他类，从而能更容易地处理常见的输入任务。

例如，Scanner 类提供了输入单词、数字和其他数据的方法，其包含在java.util 包中。java.util 包含的类很有用，因此被称为“实用类”。在使用 Scanner 之前，必须先像下面这样导入它：

```java
import java.util.Scanner;
```

这条导入语句`import statement`告诉编译器，当说到 Scanner 时，你指的是 java.util 中定义的 Scanner。必须将这一点传达给编译器，因为其他包中可能也存在 Scanner 类。使用导入语句可避免代码存在二义性。

导入语句不能存在于类定义中。根据约定，它们通常位于文件的开头。

接下来，你需要创建一个 Scanner 对象：

```java
Scanner in = new Scanner(System.in);
```

这行代码声明了一个名为 in 的 Scanner 变量，并新建了一个 Scanner对象以便从 ystem.in 获取输入。

Scanner 提供了**方法 nextLine，它从键盘读取一行输入，并返回一个 String (nextInt看3.4)**。下面的示例读取了两行，并向用户显示了它们：

```java
package Chapter3;
import java.util.Scanner;
public class Work1 {
    public static void main(String[] args) {

        // 输入练习
        String name;
        int age;
        Scanner in = new Scanner(System.in);
        System.out.print("请输入您的姓名：");
        name = in.nextLine();
        System.out.println("您的姓名是：" + name);
        System.out.print("请输入您的年龄：");
        age = in.nextInt();
        System.out.println("您的年龄是：" + age + "岁");
    }
}
```

输出：

```
请输入您的姓名：mzk（mzk是自己输入）
您的姓名是：mzk
请输入您的年龄：23（23是自己输入）
您的年龄是：23岁
```

如果你在没有包含上述导入语句的情况下引用 Scanner，编译器将显示一条类似于 cannot find symbol（找不到符号）的消息，这意味着编译器不知道你说的 Scanner 指的是什么。

你可能会心存疑惑，为何不用导入 System 就能使用它呢？ System 位于可自动导入的 java.lang 包中。Java 文档指出，java.lang 提供了Java 编程语言中的基本类。String 类也位于 java.lang 包中。

## 3.3 程序结构

![image-20230313152009340](C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230313152009340.png)

包是类的集合，而类定义了方法；方法包含语句，而有些语句包含表达式；表达式由标记（token）组成，而标记是程序的基本元素，其中包括数字、变量名、运算符、关键词以及括号、大括号和分号等标点。

Java 的标准版自带了可在程序中导入的数千个类，这令人既激动又惊恐。要浏览这个库，可访问 http://docs.oracle.com/javase/8/docs/api/。Java 库主要是用 Java 编写的。

请注意，Java 语言和 Java 库的主要差别在于，前者定义了上图所示元素的语法和含义，而后者提供了内置类。

## 3.4 英寸到厘米的转换

现在让我们来看一个有点实用价值的示例。虽然全球的大部分地区都在用公制度量衡，但有些国家依然还在用英制单位。例如，与欧洲的朋友谈论天气时，美国人可能要在摄氏温度和华氏温度之间进行转换。另外，还可能要将身高从英寸数转换为厘米数。

我们可以编写一个程序来提供帮助。在这个程序中，我们将用一个Scanner 对象来获取以英寸为单位的值，然后将其转换为厘米数并显示结果。下面的代码行声明了所需要的变量并创建了一个 Scanner 对象：

```java
int inch;
double cm;
Scanner in = new Scanner(System.in);
```

接下来需要提示用户输入值。为此，我们将使用 print 而不是println，让用户能够在提示所在的行进行输入。另外，我们还将使用Scanner 类的**方法 nextInt，以便从键盘读取输入并将其转换为整数**：

```java
System.out.print("How many inches? ");
inch = in.nextInt();
```

接下来，我们将英寸数乘以 2.54（因为 1 英寸相当于 2.54 厘米）并显示结果：

```java
cm = inch * 2.54;
System.out.print(inch + " in = ");
System.out.println(cm + " cm");
```

这些代码可以正确运行，但存在一个小问题：其他程序员看到这些代码时，可能不明白 2.54 是怎么来的。为方便其他程序员（还有未来的你），更好的做法是将这个值赋给一个变量，并给这个变量指定一个有意义的名称。对此将在 3.5 节中对此进行演示。

完整代码：

```java
package Chapter3;
import java.util.Scanner;
public class Work2 {
    public static void main(String[] args){

        // 英寸厘米转换
        int inch; // 英寸为整数没有小数
        double cm; // 厘米可以有小数
        Scanner in = new Scanner(System.in);
        System.out.print("请输入一个英寸数：");
        inch = in.nextInt(); // Int是将输入的数转化为整数，英寸为整数
        cm = inch * 2.54;
        System.out.println("它对应的厘米数是：" + cm + "cm");
    }
}
```

输出结果：

```
请输入一个英寸数：11（11是自己输入的）
它对应的厘米数是：27.94cm
```

## 3.5 字面量和常量

在程序中，2.54（或 " in ="）这样的值被称为字面量（literal）。一般而言，使用字面量没什么错，但如果在表达式中使用 2.54 这样的数字，却不作任何解释的话，代码将难以理解。另外，如果同样的值出现多次，且以后可能需要修改，那么代码将难以维护。

这样的值有时被称为魔幻数字（magic number，这里的“魔幻”可不是褒义的），一种很好的做法是像以下这样将魔幻数字赋给变量，并给变量指定有意义的名称：

```java
double cmPerInch = 2.54;
cm = inch * cmPerInch;
```

这个版本更容易理解，而且不那么容易出错，但还是存在一个问题，那就是变量是可变的，而 1 英寸对应的厘米数是不变的。一旦给cmPerInch 赋值，就再也不应该修改。Java 提供了实施这种规则的语言特性——关键词 final。

```java
final double CM_PER_INCH = 2.54;
```

**将变量声明为 final 意味着对其进行初始化后，就不能重新赋值了。**

如果你试图这样做，编译器就会报错。声明为 final 的变量被称为常量（constant）；根据约定，**常量名全部大写，且单词间用下划线（ _ ）连接**。

代码演示：

```java
package Chapter3;
import java.util.Scanner;
public class Work3 {
    public static void main(String[] args){

        // 使用final定义常量来转化
        final double CM_PER_INCH = 2.54;
        int inch;
        double cm;
        Scanner in = new Scanner(System.in);
        System.out.print("请输入一个英寸数：");
        inch = in.nextInt();
        cm = inch * CM_PER_INCH;
        System.out.print("转化为厘米数为：" + cm + "cm");
    }
}
```

输出结果：

```
请输入一个英寸数：11（11为自己输入的数）
转化为厘米数为：27.94cm
```

## 3.6 设置输出的格式

使用 print 或 println 输出 double 值时，最多显示 16 位小数：

```java
System.out.print(4.0 / 3.0);
```

结果如下：

```
1.3333333333333333
```

这可能比你想要的要多。System.out 提供了另一个**方法 printf**，让你对输出格式有更大的控制权，printf 中的 f 指的是“格式化”。以下是一个示例：

```java
System.out.printf("Four thirds = %.3f", 4.0 / 3.0);
```

括号中的第一个值为格式字符串（format string），指定了输出的显示方式。上述的格式字符串中包含普通文本，**普通文本的后面是格式说明符（format specifier）——以百分号打头的特殊序列。格式说明符 %.3f指定接下来的值应显示为浮点数，并舍入到三位小数**。上述代码的结果如下：

```
Four thirds = 1.333
```

格式字符串可包含任意数目的格式说明符，下面的格式字符串就包含了两个格式说明符：

```java
package Chapter3;
public class Work4 {
    public static void main(String[] args) {

        final double CM_PER_INCH = 2.54;
        int inch = 100;
        double cm = inch * CM_PER_INCH;
        System.out.printf("%d in = %f cm\n", inch, cm); // %d为整型数据，%f为浮点型数据
    }
}
```

结果如下：

```
100 in = 254.000000 cm
```

与 print 一样，printf 也不在末尾换行；所以格式字符串通常以换行符结尾。

格式说明符 %d 用于显示整数值，其中的 d 表示 decimal（十进制）。值依次与格式说明符配对，因此，用于 inch 的格式说明符为 %d，用于cm 的格式说明符为 %f。

学习格式字符串相当于学习 Java 中的一种子语言；涉及的选项很多，细节可能让人不可重负。表 3-1 列出了一些常用的格式说明符，旨在让你大致地了解其中的工作原理；更多细节请参阅java.util.Formatter 的相关文档。要想找到有关 Java 类的文档，最简单的方法是在网上搜索 Java 和类名。

格式说明符示例：

| %d   | 十进制整数                          | 12345    |
| ---- | ----------------------------------- | -------- |
| %08d | 添加前导零，确保显示的值至少包含8位 | 00012345 |
| %f   | 浮点数                              | 6.789000 |
| %.2f | 舍入到两位小数                      | 6.78     |

## 3.7 厘米到英寸的转换

现在假设有一个以厘米为单位的值，我们想将其转换为与之最接近的英寸数。你可能很想这样编写代码：

```java
inch = cm / CM_PER_INCH; // 语法错误
```

但这将导致编译错误，会出现类似于“Bad types in assignment: fromdouble to int”这样的错误消息。这是因为右边是浮点数，而左边是整数变量。

要将浮点值转换为整数，最简单的方式是使用类型转换（type cast），类型转换因将值从一种类型塑造或铸造成另一种类型而得名。类型转换的语法是将类型名放在括号内，并将其用作运算符。

```java
double pi = 3.14159;
int x = (int) pi;
```

**运算符 (int) 会将它后面的值转换为整数**。在这个示例中，x 将被设置为 3。与整数除法一样，**转换为整数时总是向下圆整**，即便小数部分为0.999999（或 -0.999999）也是如此。换言之，将**直接丢弃小数部分**。

类型转换的优先级高于算术运算。在下面的示例中，先将 pi 的值转换为整数，然后再执行乘法运算，因此结果为 60.0，而不是 62.0。

```java
double pi = 3.14159;
double x = (int) pi * 20.0;
```

请务必牢记这一点。下面的代码演示了如何将厘米数转换为英寸数：

```java
inch = (int) (cm / CM_PER_INCH);
System.out.printf("%f cm = %d in\n", cent, inch);
```

转换运算符后面的括号使得除法运算先执行，然后再进行类型转换。因此**除法运算的结果将向下圆整**；我们将在下一章介绍如何将浮点数圆整为与之最接近的整数。

完整代码：

```java
package Chapter3;
import java.util.Scanner;
public class Work5 {
    public static void main(String[] args) {

        final double CM_PER_INCH = 2.54;
        int inch;
        double cm;
        Scanner in = new Scanner(System.in);
        System.out.print("请输入厘米数：");
        cm = in.nextDouble(); // cm有小数部分，用Double类型
        inch = (int)(cm / CM_PER_INCH); // (int)相当于运算符，将右边括号内数据转化为整型数据
        System.out.printf("%.2f cm = %d in\n", cm, inch); // 使用printf方法，%.2保留两位小数，引号内的 %.2和 %d按照逗号后面变量依次显示
    }
}
```

输出：

```
请输入厘米数：22.22
22.22 cm = 8 in
```

## 3.8 求模运算符

现在我们再进一步：假设你有一个以英寸为单位的值，并且想将其转换为英尺数和英寸数。为此，需要除以 12（1 英尺对应 12 英寸），并将余数记录下来。

前面已经介绍过除法运算符（/），用于计算两个数的商。如果两个操作数都为整数，那么它将执行整数除法。Java 还提供了求模（modulus）运算符（%），用于计算两个数相除的余数。

可像以下这样用除法和求模运算来将英寸数转换为英尺数和英寸数：

```java
quotient = 76 / 12; // 除法
remainder = 76 % 12; // 求模
```

第 1 行的结果为 6，第 2 行读作“76 与 12 的模”，结果为 4。因此，76英寸相当于 6 英尺 4 英寸。

求模运算符看起来像百分号，但其实可以将其视为除号（÷）向左旋转90 度的结果。

求模运算符很有用，例如，可以检查一个数能否被另一个数整除：如果x % y 的结果为零，就说明 x 能够被 y 整除。可用求模运算来提取数字中的某些位：x % 10 的结果为 x 的个位，而 x % 100 的结果为最后两位。另外，很多加密算法都大量地使用了求模运算符。

完整代码：

```java
package Chapter3;
import java.util.Scanner;
public class Work6 {
    /**
     * 将英寸转化为英尺
     */
    public static void main(String[] args) {

        int inch1, inch2, feet; // 定义两个英寸，1为输入的英寸，2为英尺余下的英寸
        Scanner in = new Scanner(System.in);
        System.out.print("请输入英寸数：");
        inch1 = in.nextInt(); // 输入的为英寸，为整数Int
        feet = inch1 / 12; // 求出英尺的整数部分
        inch2 = inch1 % 12; // 求出英尺的小数部分
        System.out.printf("%d in = %d ft,%d in", inch1, feet, inch2); // 使用方法printf
    }
}
```

运行结果：

```
请输入英寸数：76
76 in = 6 ft,4 in
```

## 3.9 整合

如何导入 Java 库中的类、如何创建 Scanner 对象、如何从键盘获取输入、如何用 printf 设置输出的格式以及如何执行整数除法和求模运算。写一个本章整合的程序，将厘米转化为英寸，再转化为英尺。

代码如下：

```java
package Chapter3;
import java.util.Scanner;
public class Work7 {
    /**
     * 将厘米数转换为英尺数和英寸数
     */
    public static void main(String[] args) {

        // 定义数据类型
        int inch1, inch2, feet;
        double cm;
        final double CM_PER_INCH = 2.54;
        final int INCH_PER_FOOT = 12;

        // 输入厘米数
        Scanner in = new Scanner(System.in);
        System.out.print("请输入厘米数：");
        cm = in.nextDouble();

        // 将厘米转化为英寸
        inch1 = (int)(cm / CM_PER_INCH);

        // 将英寸转化为英尺
        feet = inch1 / INCH_PER_FOOT;
        inch2 = inch1 % INCH_PER_FOOT;
        System.out.printf("%.2f cm = %d in = %d ft,%d in", cm, inch1, feet, inch2);
    }
}
```

运行结果：

```
请输入厘米数：222.22
222.22 cm = 87 in = 7 ft,3 in
```

虽然没有要求，但所有的变量和常量都是在 main 方法的开头声明的。这种做法让人更容易获悉这些变量和常量的类型以及算法涉及了哪些数据。

为提高可读性，可用一个空行将算法的主要步骤分隔开，且每个主要步骤都以注释打头。这个程序还包含文档注释（/**）。

很多算法（包括程序 Convert）都结合使用了除法和求模运算。在程序Convert 中，这两种运算使用的除数相同，都是 IN_PER_FOOT。

常见的编程风格是将过长（超过 80 个字符）的语句分成多行，以便阅读时不用水平滚动。

## 3.10 Scanner类的bug

在有了一些使用 Scanner 的经验后，有必要提醒一下，它存在一个出人意料的行为。下面的代码片段让用户输入姓名和年龄：

```java
package Chapter3;
import java.util.Scanner;
public class Work8 {
    public static void main(String[] args) {

        int age;
        String name;
        Scanner in = new Scanner(System.in);
        System.out.print("请输入您的姓名：");
        name = in.nextLine();
        System.out.print("请输入您的年龄：");
        age = in.nextInt();
        System.out.printf("您的姓名是：%s\n您的年龄是：%d", name, age);
    }
}
```

其输出是正确的：

```
请输入您的姓名：mzk
请输入您的年龄：23
您的姓名是：mzk
您的年龄是：23
```

**先读取 String 再读取 int 时，一切都正常，但如果先读取 int 再读取String，将发生怪异的事情。**

```java
System.out.print("请输入您的年龄：");
age = in.nextInt();
System.out.print("请输入您的姓名：");
name = in.nextLine();
System.out.printf("您的姓名是：%s\n您的年龄是：%d", name, age);
```

如果尝试运行上述示例代码，你将发现它根本不允许输入姓名，而在你输入年龄后会直接显示输出：

```
请输入您的年龄：23
请输入您的姓名：您的姓名是：
您的年龄是：23
```

要想明白其中的原因，你必须知道的是，Scanner 并不像我们那样将输入视为多行；相反，它获得的是一个下图所示的“字符流”。

| 2    | 3    | \n   | m    | z    | k    | \n   |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |

![image-20230314132549006](C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230314132549006.png)   

其中的箭头指向 Scanner 将读取的下一个字符。调用 nextInt 时，它会不断读取字符，直到遇到非数字字符。下图显示了调用 nextInt 后流的状态。

| 2    | 3    | \n   | m    | z    | k    | \n   |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- |

​                                          ![image-20230314132549006](C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230314132549006.png)         

此时，nextInt 返回 23。接下来，程序显示提示`请输入您的姓名：`，并调用 nextLine；这个方法会不断读取字符，直到遇到换行符。然而，由于下一个字符就是换行符，因此extLine 返回一个空字符串（""）。

为解决这个问题，需要在 nextInt 后面多调用一次 nextLine。

```java
System.out.print("请输入您的年龄：");
age = in.nextInt();
in.nextLine(); // 读取换行符
System.out.print("请输入您的姓名：");
name = in.nextLine();
System.out.printf("您的姓名是：%s\n您的年龄是：%d\n", name, age);
```

读取独占一行的 int 或 double 值时，经常需要使用技巧：先读取数字，再读取当前行余下的全部内容（仅仅是一个换行符）。

完整代码：

```java
package Chapter3;
import java.util.Scanner;
public class Work8 {
    public static void main(String[] args) {

        int age;
        String name;
        Scanner in = new Scanner(System.in);
        System.out.print("请输入您的年龄：");
        age = in.nextInt();
        in.nextLine(); // 读取换行符
        System.out.print("请输入您的姓名：");
        name = in.nextLine();
        System.out.printf("您的姓名是：%s\n您的年龄是：%d\n", name, age);
    }
}
```

输出结果：

```
请输入您的年龄：23
请输入您的姓名：mzk
您的姓名是：mzk
您的年龄是：23
```

## 3.11 术语表

| 术语            | 含义                                                         |
| --------------- | ------------------------------------------------------------ |
| 包(package)     | 一组彼此相关的类。                                           |
| 地址            | 值在计算机内存中的位置，通常用十六进制整数表示。             |
| 库(library)     | 可在其他程序中使用的一系列包和类。                           |
| 导入语句        | 让程序能够使用其他包中定义的类的语句。                       |
| 标记            | 程序的基本元素，如单词、空格、符号或数字。                   |
| 字面量(literal) | 在源代码中出现的值，例如，"Hello" 是一个字符串字面量，而74 是一个整数字面量。 |
| 魔幻数字        | 表达式中没有任何解释的数字，通常应将其替换为常量。           |
| 常量(constant)  | 声明为 final 的变量，其值不可修改。                          |
| 格式字符串      | 传递给 printf 以便指定输出格式的字符串。                     |
| 格式说明符      | 以百分号开头的特殊编码，指定了相应值的数据类型和格式。       |
| 类型转换        | 从一种类型明确地转换为另一种类型的操作。在 Java 中表现为用括号括起的类型名，如（int）。 |
| 求模（余数）    | 一种运算符，用于计算两个整数相除的余数。在 Java 中用百分号表示。例如，5 \% 2 的结果为 1。 |

## 3.12 练习

#### 第一题

编写一个程序，将摄氏温度转换为华氏温度。这个程序应：(1) 提示用户输入摄氏温度值； (2) 从键盘读取一个 double 值；(3) 计算结果；(4)将输出设置为包含一位小数。例如，它应显示 "24.0 C=75.2 F" 这样的输出。
下面是转换公式，请注意，千万不要用整数除法！
$$
F = C * 9/5 + 32
$$

#### 第二题

编写一个程序，将秒数转换为小时数、分钟数和秒数。这个程序应：(1)提示用户输入秒数；(2) 从键盘读取一个整数；(3) 计算结果；(4) 用printf 显示输出。例如，它应显示 "5000 seconds = 1 hours, 23minutes, and 20 seconds" 这样的输出。
提示：可使用求模运算符。

#### 第三题

编写一个“猜数”游戏，将用户输入作为整数读取，并显示结果。再次编译并测试这个程

序，计算并显示用户猜测的数字和生成的随机数之间的差。其输出应类似于以下这样：

```
I'm thinking of a number between 1 and 100
(including both). Can you guess what it is?
Type a number: 45
Your guess is: 45
The number I was thinking of is: 14
You were off by: 31
```

要想生成随机数，可使用 java.util 中的 Random 类，其工作原理如下：

```java
import java.util.Random;
public class GuessStarter {
	public static void main(String[] args) {
		// 生成一个随机数
		Random random = new Random();
		int number = random.nextInt(100) + 1;
		System.out.println(number);
	}
}
```

要想使用 Random 类，必须先导入。另外，与创建 Scanner 对象一样，必须用 new 运算符创建一个 Random对象（随机数生成器）。然后就可以用方法 nextInt 来生成随机数了。在上面的示例中，**nextInt(100) 的结果是一个 0~99（闭区间）的数字**。通过将这个结果加 1，将得到一个 1~100（闭区间）的数字。

#### 第一题代码

```java
package Chapter3;
import java.util.Scanner;
public class Work9 {
    /**
     * 练习：将摄氏温度转为华氏温度
     * 公式：F = C * (9 / 5) +32
     */
    public static void main(String[] args) {

        double a, b, C, F; // a为摄氏度除后的整数部分，b为摄氏度除后的余数部分
        Scanner in = new Scanner(System.in);
        System.out.print("请输入摄氏温度：");
        C = in.nextDouble();
        F = C * 9 / 5 + 32;
        System.out.printf("%.1f C = %.1f F",C ,F);
    }
}
```

#### 第二题代码

```java
package Chapter3;
import java.util.Scanner;
public class Work10 {
    /**
     * 把秒转化为时分秒的格式
     */
    public static void main(String[] args) {

        int seconds1, seconds2, minutes, hours;
        Scanner in = new Scanner(System.in);
        System.out.print("请输入秒数：");
        seconds1 = in.nextInt();
        hours = seconds1 / 60 / 60;
        minutes = seconds1 / 60 - hours * 60;
        seconds2 = seconds1 %60 %60;
        System.out.printf("%d seconds = %d hours, %d minutes, " +
                "and %d seconds", seconds1, hours, minutes, seconds2);
    }
}
```

#### 第三题代码

```java
package Chapter3;
import java.util.Random;
import java.util.Scanner;
public class Work11 {
    /**
     *猜数游戏
     */
    public static void main(String[] args) {

        int a, b;
        Random random = new Random();
        int number = random.nextInt(100) +1; // [1,101)之间的随机数
        Scanner in = new Scanner(System.in);
        System.out.print("请猜一个1~100之间的数字：");
        a = in.nextInt();
        if (a > number) {
            b = a - number;
            System.out.println("你猜错了");
            System.out.printf("正确答案是：%d\n", number);
            System.out.printf("你猜的数比number大了%d\n", b);
        } else if (a == number) {
            System.out.println("你猜对了");
            System.out.printf("正确答案是：%d\n", number);
            System.out.println("你猜的和正确答案一样");
        } else {
            b = number - a;
            System.out.println("你猜错了");
            System.out.printf("正确答案是：%d\n", number);
            System.out.printf("你猜的数比number小了%d", b);
        }
    }
}
```

# 4 void方法

到目前为止，我们编写的程序都很短，只包含一个类和一个方法（main）。我们将在本章演示如何将较长的程序组织成多个方法和类，还将介绍 Math 类，它提供了执行常见数学运算的方法。

## 4.1 Math类的方法

学习数学时，学过 sin 和 log 这样的函数，还学习过如何计算像sin(π/2) 和 log(1/*x*) 这样的表达式的值：先计算括号内的表达式，它们被称为函数的实参（argument），然后计算函数本身，可能还要用到计算器。

计算 log(1/sin(π/2)) 这样更复杂的表达式时，可重复执行这个过程：**先计算最里面的函数的实参，再计算函数本身，依此类推**。

Java 库包含一个 Math 类，它提供了执行常见数学运算的方法。这个类位于 java.lang 包中，因此无需导入。可像下面这样使用或调用（invoke）Math 类的方法：

```java
double root = Math.sqrt(17.0);
double angle = 1.5;
double height = Math.sin(angle);
```

第 1 行将 root 设置为 17 的平方根；第 3 行计算 1.5（变量 angle 的值）的正弦。

三角函数 sin、cos 和 tan 的实参应以弧度为单位。要想将度数转换为弧度数，可将其除以 180 再乘以 π。好在 Math 类提供了一个名为 PI 的double 常量，它包含 π 的近似值：

```java
double degrees = 90;
double angle = degrees / 180.0 * Math.PI;
```

请注意，常量名 PI 的字母全都是大写；Java 根本不知道 Pi、pi 和pie 为何物。另外，PI 是一个变量而不是方法的名称，因此它后面不带括号。常量 Math.E 亦是如此，它包含欧拉数的近似值。

在度数和弧度数之间进行转换是一种常见的运算，因此 Math 类提供了执行这种运算的方法。

```java
double radians = Math.toRadians(180.0);
double degrees = Math.toDegrees(Math.PI);
```

另一个很有用的方法是 round，它将浮点数圆整为最接近的整数，并将其作为 long 值返回。long 类似于 int，但可表示的值更大。更具体地说，int 长 32 位，可存储的最大值为 2的31次方减1——约为 20 亿；long 长64 位，可存储的最大值为 2的63次方减1——约为 9×10 的18次方。

```java
long x = Math.round(Math.PI * 20.0);
```

结果为 63（这是将 62.8319 向上圆整得到的）。

请花点时间阅读 Math 类的这些方法和其他方法的文档。要想查找有关Java 类的文档，最简单的方法是在网上搜索 Java 和类名。

### 4.1.1 算数计算

- Math.sqrt() ：计算平方根，例如 Math.sqrt(16); 输出4.0，返回的是double型
- Math.cbrt() ： 计算立方根
- Math.pow(a, b) ： 计算a的b次方
- Math.max( , ) ： 计算最大值
- Math.min( , ) ： 计算最小值
- Math.abs( ) ： 取绝对值
- Math.log() ：返回一个数的自然对数

```java
System.out.println(Math.sqrt(25));  //5.0      --计算平方根

System.out.println(Math.cbrt(8));   //2.0       --计算立方根

System.out.println(Math.pow(3,3));  //27.0      --计算a的b次方

System.out.println(Math.max(88,8));  //88      --计算最大值

System.out.println(Math.min(88,8));  //8       --计算最小值

System.out.println(Math.abs(-13.14));  //13.14       --计算绝对值

System.out.println(Math.log(10)); //2.30        --计算一个数的自然对数
```

### 4.1.2 进位取整

- Math.ceil() ： 向上取整
- Math.floor() ：向下取整
- Math.round() ：四舍五入，**float时返回int值，double时返回long值**
- Math.rint() ：四舍五入，**返回double值。注意.5的时候会取偶数**

```java
double a = 2.01;
double b = Math.ceil(a); //向上取整
System.out.println(b);  //3.0

double c = 8.99;
double d = Math.floor(c); //向下取整
System.out.println(d); //8.0

double e = 5.4;
double f = Math.round(e); //向上取整
System.out.println(f); //5.0

double g = 6.51;
double h = Math.rint(g); //四舍五入  注意.5的时候会取偶数
System.out.println(h); //7.0
```

### 4.1.3 随机数

- Math.random() ： 取得一个[0, 1)范围内的随机数

```java
System.out.println(Math.random()); // [0, 1)的double类型的数

System.out.println(Math.random() * 2);//[0, 2)的double类型的数

System.out.println(Math.random() * 2 + 1);// [1, 3)的double类型的数
```

### 4.1.4 静态常量

Math 类中包含 E 和 PI 两个静态常量，正如它们名字所暗示的，它们的值分别等于 e（自然对数）和 π（圆周率）。`Math.E Math.PI`

- Marh.exp(x) ：计算e^x

```java
System.out.println(Math.exp(1)); //2.718281828459045
```

### 4.1.5 弧度角度转化

- Math.toDegrees() ：将弧度转换成角度，例如 Math.toDegrees(Math.PI/4); 输出 45.0，返回的是double型
- Math.toRadians() ：将角度转换为弧度，例如 Math.toRadians(45); 输出 π/4

```java
System.out.println(Math.toDegrees(Math.PI / 4)); //45.0

System.out.println(Math.toRadians(45)); //0.7853981633974483
```

### 4.1.6 三角函数

- Math.sin() 计算正弦值，例如 Math.sin(Math.PI/2); 输出1.0；返回的是double型

- Math.cos() 计算余弦值，例如 Math.cos(Math.PI); 输出-1.0；返回的是double型

- Math.tan() 计算正切值，例如 Math.tan(Math.PI/4); 输出1.0；返回的是double型
- Math.asin() 通过正弦值计算角度，输出的是弧度制，例如 Math.asin(0.5); 输出 π/6
- Math.acos() 通过余弦值计算角度，输出的是弧度制，例如 Math.acos(0.5); 输出 π/3

- Math.atan() 通过正切值计算角度，输出的是弧度制，例如 Math.atan(1); 输出 π/4

```java
System.out.println(Math.sin(Math.PI / 2)); //1.0

System.out.println(Math.cos(Math.PI)); //-1.0

System.out.println(Math.tan(Math.PI / 4)); //1.0

System.out.println(Math.asin(0.5)); // π/6  0.5235987755982989

System.out.println(Math.acos(0.5)); // π/3  1.0471975511965979

System.out.println(Math.atan(1)); // π/4  0.7853981633974483
```

## 4.2 组合

与数学函数一样，Java 方法也是可以组合的，这意味着可在一个表达式中包含另一个表达式。例如，可将任何表达式用作方法的实参：

```java
double x = Math.cos(angle + Math.PI / 2.0);
```

这条语句将 Math.PI 除以 2，再将结果与 angle 相加，然后计算得到的和的余弦。还可将一个方法的结果用作另一个方法的实参：

```java
double x = Math.exp(Math.log(10.0));
```

在 Java 中，方法 log 总是以 e 为底，因此这条语句计算以 e 为底的 10的对数，再将结果作为指数计算 e 的相应次幂，然后将得到的结果赋给变量 x。

Math 类的有些方法接受多个实参，例如，Math.pow 接受两个实参，并计算第一个实参的第二个实参次幂。下面的这行代码将值 1024.0 赋给变量 x：

```java
double x = Math.pow(2.0, 10.0);
```

在用 Math 类的方法时，遗漏 Math 是一种常见的错误。例如，如果试图调用 pow(2.0, 10.0)，将出现类似于以下的错误消息：

```
File: Test.java [line: 5]
Error: cannot find symbol
  symbol: method pow(double,double)
  location: class Test
```

消息 cannot find symbol 令人迷惑，但最后一行提供了有用的线索：编译器试图在调用方法 pow 的类（Test）中查找它。如果没有指定类名，编译器将在当前类中查找。

## 4.3 添加方法

在一个类中可定义多个方法，如下例所示：

```java
public class NewLine {

	public static void newLine() {
		System.out.println();
	}

	public static void main(String[] args) {
		System.out.println("First line.");
		newLine();
		System.out.println("Second line.");
	}
}
```

类名为 NewLine。根据约定，类名的首字母要大写。NewLine 包含两个方法：newLine 和 main。别忘了，Java 区分大小写，因此 NewLine 和newLine 不是一回事。

方法名的首字母应小写，并采用“骆驼拼写法”，即类似于jammingWordsTogetherLikeThis 这样的格式。可给方法指定任何名称，但 main 和其他 Java 关键词除外。

newLine 和 main 是公有的，这意味着可在其他类中调用。它们都是静态的，那么静态是什么意思呢？现在暂时无法解释。另外，它们的返回类型都是 void，这意味着它们不会像 Math 类的方法那样返回结果。

方法名后面的括号包含了一个变量列表，这些变量被称为形参（parameter），用于存储方法的实参。**main 只有一个名为 args 的形参，类型为 String[]，这意味着调用这个 main 方法时，必须提供一个字符串数组。**

由于 newLine 没有形参，所以调用时不需要提供实参，如在 main 方法中的调用所示。另外，由于 newLine 和 main 位于同一个类中，因此在main 中调用 newLine 时无需指定类名。

上面程序输出结果：

```
First line.

Second line.
```

注意，输出行之间有空行。如果要想让输出行相距得更远，可多次调用方法 newLine：

```java
public static void main(String[] args) {
	System.out.println("First line.");
	newLine();
	newLine();
	newLine();
	System.out.println("Second line.");
}
```

我们也可以再编写一个显示三个空行的方法（完整代码）：

```java
package Chapt4;

public class Work1 {
    public static void newLine() {
        // 方法名首字母小写，后面单词首字母大写
        System.out.println();
    }
    public static void threeLine() {
        newLine();
        newLine();
        newLine();
    }
    public static void main(String[] args) {
        System.out.println("First line.");
        threeLine();
        System.out.println("Second line.");
    }
}
```

输出结果：

```
First line.



Second line.
```

## 4.4 执行流程

将 4.3 节中的代码组合起来可以得到类似于下面这样的完整程序：

```java
package Chapt4;

public class Work1 {
    public static void newLine() {
        // 方法名首字母小写，后面单词首字母大写
        System.out.println();
    }
    public static void threeLine() {
        newLine();
        newLine();
        newLine();
    }
    public static void main(String[] args) {
        System.out.println("First line.");
        threeLine();
        System.out.println("Second line.");
    }
}
```

阅读包含多个方法的类定义时，你可能很想按照从头到尾的顺序阅读。但这样做很可能让你感到迷惑，因为程序的执行流程（flow of excution）并不是这样的。

**不管 main 方法位于源代码文件的什么地方，程序总是从这个方法的第一条语句开始执行。**语句按顺序以每次一条的方式执行，直到遇到方法调用。我们可将方法调用视为改道：不是直接执行下一条语句，而是跳转到被调用的方法的第一行，执行完这个方法的全部语句后，再回到离开的地方继续执行。

这好像很简单，但别忘了，一个方法可以调用另一个方法。执行 main 方法时，中途离开去执行 threeLine 的语句；执行 threeLine 时，又中途离开去执行 newLine；而 newLine 调用 println，导致再次改道。

好在 Java 擅于跟踪当前的运行方法，因此，println 执行完毕后，它会回到离开 newLine 的地方；newLine 执行完毕后，回到离开threeLine 的地方；而 threeLine 执行完毕后，又回到离开 main 的地方。

总之，阅读程序时，不要按照从头到尾的顺序阅读，而应按执行流程阅读。

## 4.5 形参和实参

前面使用的有些方法需要实参，实参是调用方法时提供的值。例如，要计算一个数字的正弦就必须提供这个数字，因此，sin 接受一个double 实参。要显示一条消息就必须提供这条消息，因此，println接受一个 String 实参。

在使用方法时提供的是实参，在编写方法时指定的是形参。形参列表指定了必须提供哪些实参，以下是一个示例：

```java
package Chapt4;

public class Work2 {

    public static void printTwice(String s) {
        // printTwice 包含了一个名为 s，类型为 String 的形参
        // 调用printTwice 时，必须提供一个类型为 String 的实参
        System.out.println(s);
        System.out.println(s);
    }
    public static void main(String[] args) {
        printTwice("Hello,world!");
        // printTwice 里面必须是类型为 String 的实参
    }
}
```

**printTwice 包含了一个名为 s，类型为 String 的形参。调用printTwice 时，必须提供一个类型为 String 的实参。**

方法执行前，实参会赋给形参。在这个示例中，实参 "Don't make me say this twice!" 被赋给形参 s 。

这个过程被称为参数传递（parameter passing），因为值从方法外传到了方法内。实参可以是任何表达式，因此，如果声明了一个 String 变量，就可将其用作实参：

```java
package Chapt4;

public class Work3 {

    public static void printTwice(String s) {
        System.out.println(s);
        System.out.println(s);
    }
    public static void main(String[] args) {
        String a = "mzk"; // 声明了String变量
        printTwice(a);
    }
}
```

用作实参的值必须与形参的类型相同，例如，如果你试图像下面这样做：

```java
printTwice(17); // 语法错误
```

将出现类似于下面这样的错误消息：

```
File: Test.java [line: 10]
Error: method printTwice in class Test cannot be applied
		to given types;
	required: java.lang.String
	found: int
	reason: actual argument int cannot be converted to
	java.lang.String by method invocation conversion
```

在有些情况下，Java 能够自动将实参从一种类型转换为另一种类型。例如，Math.sqrt 需要接受一个 double 实参，但如果你调用了Math.sqrt(25)，整数值 25 将自动转换为浮点值 25.0。但就printTwice 而言，Java 并不能（或不会）将提供给它的整数 17 转换为 String。

形参和其他变量只存在于当前的方法中；在 main 中，没有 s 这样的变量，如果试图在这个方法中使用它，将导致编译错误。同样，printTwice 中没有 args 变量，这个变量位于 main 中。

鉴于变量只在定义它的方法中存在，因此它们常被称为局部变量（local varible）。

## 4.6 多个形参

下面是一个接受两个形参的方法：

```java
package Chapt4;

public class Work4 {

    public static void printTime(int hour, int minute) {
        // 两个形参必须都要声明int，如果只声明一个int需要在实参那边重新定义int类型
        System.out.print(hour);
        System.out.print(":");
        System.out.println(minute);
    }
    public static void main(String[] args) {
        printTime(4, 32);
        // 形参已经定义了两个变量为int
    }
}

// 输出：4:32
```

你可能很想将上述的形参列表写成下面这样：

```java
public static void printTime(int hour, minute) {
	System.out.print(hour);
	System.out.print(":");
	System.out.println(minute);
}
```

但这种格式（省略第二个 int）只适用于变量声明；在形参列表中，必须分别指定每个变量的类型。**要调用这个方法，必须提供两个整数实参：**

```java
int hour = 11;
int minute = 59;
printTime(hour, minute);
```

常见的错误是像下面这样声明实参的类型：

```java
int hour = 11;
int minute = 59;
printTime(int hour, int minute); // 语法错误
```

这是一种语法错误：在编译器看来，int hour 和 int minute 是变量名，而不是表达式。如果将整数字面量用作实参，则不能声明它们的类型：

```java
printTime(int 11, int 59); // 语法错误
```

## 4.7 栈图

将 4.6 节的代码片段组合起来可以得到完整的类定义，如下：

```java
package Chapt4;

public class Wrok5 {

    public static void printTime(int hour, int minute) {
        // 两个形参必须都要声明int，如果只声明一个int需要在实参那边重新定义int类型
        System.out.print(hour);
        System.out.print(":");
        System.out.println(minute);
    }
    public static void main(String[] args) {
        int hour = 11;
        int minute = 59;
        printTime(hour, minute);
    }
}

// 输出结果： 11:59
```

printTime 有两个形参——hour 和 minute。main 有两个变量，也分别名为 hour 和 minute。虽然名称相同，但这些变量是不同的变量：printTime 中的 hour 和 main 中的 hour 指向不同的存储位置，可以有不同的值。

例如，你可以像下面这样调用 printTime：

```java
int hour = 11;
int minute = 59;
printTime(hour + 1, 0)

// 输出结果：12:0
```

调用这个方法前，Java 会先计算实参的值，这里分别为 12 和 0，然后将这些值赋给形参。在 printTime 中，hour 的值为 12，而不是 11，而 minute 的值为 0，而不是 59。另外，即便 printTime 修改了其形参的值，但不会影响 main 中的变量。

要想对程序的方方面面进行跟踪，一种方法是绘制栈图（stack diagram）。栈图是一种显示方法调用的状态图（参见 2.3 节）。对于每一个方法，栈图中都有一个名为栈帧（frame）的方框，其中包含了这个方法的形参和变量。方法名位于栈帧的外面，而变量和形参则位于栈帧内。

与状态图一样，栈图也显示了变量和方法在特定时点的状态。下图是方法 printTime 刚执行时的栈图。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230315101941895.png" alt="image-20230315101941895" style="zoom:50%;" />

## 4.8 阅读文档

Java 的优点之一是自带了庞大的类库和方法。但在使用之前，可能还必须阅读文档，而这并非总是那么容易。

例如，咱们来看看 3.2 节中使用的 Scanner 类文档。要找到这个文档，可在网上搜索 Java Scanner（  https://docs.oracle.com/javase/7/docs/api/java/util/Scanner.html  ），下图是该文档页面的屏幕截图。

![image-20230315102203511](C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230315102203511.png)

其他类的文档格式与此类似。第 1 行是类所属的包，如 java.util；第2 行是类名。截屏中的 All Implemented Interfaces 列举了部分 Scanner能够做的事情。

文档的下一部分是描述，阐述了当前类的用途，还包含了使用示例。要开始使用新类，一种不错的方式是将文档中的示例粘贴到测试文件中，看看它们能否编译并运行。

有个示例演示了如何用 Scanner 从 String 而不是 System.in 读取输入：

```java
String input = "1 fish 2 fish red fish blue fish";
Scanner s = new Scanner(input);
```

描述、代码示例和其他细节的后面是以下几个表格：

- Constructor summary ：创建或构造 Scanner 对象的方式
- Method summary ：Scanner 提供的方法列表
- Constructor detail ：更多与 Scanner 对象创建方式有关的信息
- Method detail ：有关各个方法的详细信息

例如，下面是 nextInt 的摘要信息：

```java
public int nextInt()
Scans the next token of the input as an int.
```

第 1 行是方法的特征标（signature），它指定了方法的名称、形参（无）和返回类型（int）；第 2 行简单地描述了这个方法的功能。

表格 Method detail 更详细地阐述了这个方法：

```java
public int nextInt()
Scans the next token of the input as an int.
    
An invocation of this method of the form nextInt() behaves in
exactly the same way as the invocation nextInt(radix), where
radix is the default radix of this scanner.
    
Returns:
the int scanned from the input
Throws:
InputMismatchException - if the next token does not match
	the Integer regular expression, or is out of range
NoSuchElementException - if input is exhausted
IllegalStateException - if this scanner is closed
```

其中的 Returns 部分描述了这个方法成功时返回的结果，而 Throws 部分描述了可能发生的错误及其引发的异常。

要想熟练地阅读文档并就哪些部分可以忽略作出准确的判断，可能需要一段时间的学习，但这样的付出是值得的。知道 Java 库有哪些类可避免重复劳动，只需阅读少量的文档就可避免繁重的调试工作。

## 4.9 编写文档

Java 语言提供了一项很好的功能，即可以在源代码中嵌入文档。这让你能够在编写代码的同时编写文档，同时，更容易在修改代码时确保文档与代码一致。

可用工具 Javadoc 自动提取包含在源代码中的文档，并生成格式良好的HTML。这个工具包含在标准 Java 开发环境中，被大家广泛使用。事实上，Java 库的在线文档就是用 Javadoc 生成的。

Javadoc 扫描源代码文件以查找格式特殊的文档注释——也称为 Javadoc注释。这种注释以 /**（两个星号）打头，并以 */（一个星号）结尾，位于它们之间的所有内容都被视为文档。下面的类定义包含两条 Javadoc 注释，其中一条是针对类的，另一条是针对方法 main 的：

```java
/**
 * 演示print和println的示例程序
 */

public class Goodbye {

	/**
	 * 打印问候语
	 */
	public static void main(String[] args) {
		System.out.print("Goodbye, "); // 请注意其中的空格
		System.out.println("cruel world");
	}
}
```

类注释阐述了类的目的，而方法注释阐述了方法的作用。

注意，这个示例还包含了一条以 // 打头的内嵌注释。一般而言，内嵌注释是对程序复杂部分进行诠释的短语，旨在帮助其他程序员理解和维护源代码。

相反，Javadoc 注释更长，通常是完整的句子。它们阐述每个方法的功能，但不涉及其工作原理的细节，旨在让人无需查看源代码就能使用这些方法。

## 4.10术语表

| 术语     | 含义                                                         |
| -------- | ------------------------------------------------------------ |
| 实参     | 调用方法时提供的值，其类型必须与相应形参的类型相同。         |
| 调用     | 执行方法。                                                   |
| 形参     | 运行方法所需要的信息。形参也是变量，包含值和类型。           |
| 执行流程 | Java 执行方法和语句的顺序，这种顺序并不一定是从上到下、从左到右的。 |
| 参数传递 | 将实参的值赋给形参变量的过程。                               |
| 局部变量 | 在方法内声明的变量；在所属方法外不能访问。                   |
| 栈图     | 各个方法中的变量的图形化表示。执行流程中的方法调用按从上到下的顺序堆叠。 |
| 栈帧     | 在栈图中表示特定方法中的变量和形参及其当前值的部分。         |
| 特征标   | 方法的第一行，定义了方法的名称、返回类型和形参。             |
| Javadoc  | 读取 Java 源代码并生成 HTML 格式文档的工具。                 |
| 文档     | 描述类或方法用法的注释。                                     |

## 4.11 练习

#### 第一题

这个练习旨在确保你明白如何编写和调用接受参数的方法。

(1) 编写方法 zool 的第一行，这个方法包含三个形参：一个 int 形参

和两个 String 形参。

(2) 编写调用 zool 的代码，它传递的实参为值 11、你养的第一个宠物

的名字以及你小时候居住的街道。

#### 第二题

这个练习的目的在于将之前编写的代码封装到一个接受参数的方法中。

做这个练习前，必须先完成练习 2-2。

(1) 编写一个名为 printAmerican 的方法，让其接受参数 day、date、

month 和 year，并以美国格式显示。

(2) 对这个方法进行测试：在 main 中调用该方法并传递合适的实参。输

出应类似于以下这样（只是日期可能不同）：

```
Saturday, July 22, 2015
```

(3) 确定方法 printAmerican 正确无误后，再编写一个以欧洲格式显示

日期的方法，并将其命名为 printEuropean。

#### 第一题代码

```java
package Chapt4;

public class Work6 {

    /**
     *第一题
     */
    public static void zool(int a, String b, String c) {
        System.out.println("小狗的年龄是：" + a + "。");
        System.out.println("小狗的名字是：" + b + "。");
        System.out.println("小狗的地址是：" + c + "。");

    }
    public static void main(String[] args) {
        int age = 11;
        String name = "大黄";
        String address = "中国";
        zool(age, name, address);
    }
}
```

#### 第二题代码

```java
package Chapt4;

public class Work7 {

    /**
     * 第二题
     */
    public static void printAmerican(String a, int b, String c, int d) {
        System.out.print(a + ", ");
        System.out.print(b + ", ");
        System.out.print(c + ", ");
        System.out.println(d + ".");
    }
    public static void main(String[] args) {
        String day = "Saturday";
        int date = 22;
        String month = "July";
        int year = 2015;
        System.out.print("America: ");
        printAmerican(day, date, month, year);
        System.out.print("Europe: ");
        printEuropean(date, month, year);
    }
    public static void  printEuropean(int a, String b, int c) {
        System.out.print(a + ".");
        System.out.print(b + " ");
        System.out.println(c + ".");
    }
}
```

# 5 条件和逻辑

能让程序作出决策的功能：一种名为boolean 的数据类型、表示逻辑的运算符以及 if 语句。

## 5.1 关系运算符

关系运算符（relational operator）用于检查条件，如两个值是否相等或一个值是否大于另一个值。以下的表达式演示了关系运算符的用法：

```java
x == y // x等于y
x != y // x与y不相等
x > y // x大于y
x < y // x小于y
x >= y // x大于或等于y
x <= y // x小于或等于y
```

关系运算符的结果为 true 或 false 这两个特殊值中的一个。这些值属于 boolean 数据类型；事实上，它们是仅有的两个 boolean 值。你可能熟悉这些运算，但注意，表示这些运算时，Java 使用的运算符不同于数学中使用的符号（如 =、≠和≤）。一**种常见的错误是使用单个等号(=)而不是两个(==)**。别忘了，**= 是赋值运算符，而 == 是一个比较运算符**。另外，没有诸如 =< 和 => 这样的 Java 运算符。

**关系运算符的两边必须兼容**，例如，表达式 5 < "6" 是非法的，因为 5是一个 int，而 "6" 是一个 String。比较不同类型的数值时，Java 应用前面介绍过的赋值运算符的转换规则。

例如，计算表达式 5 < 6.0 时，Java 自动将 5 转换为 5.0。大多数的关系运算符都不可用于字符串，但令人迷惑的是，== 和 != 可以，只是它们的行为并非你预期的那样，我们将在后面有所介绍。在此之前，不要将它们用于字符串，而应使用方法 equals：

```java
String fruit1 = "Apple";
String fruit2 = "Orange";
System.out.println(fruit1.equals(fruit2)); // 输出为 boolean 值 false
```

## 5.2 逻辑运算符

Java 提供了三个逻辑运算符（logical operator）：**&&、|| 和 !，分别表示与、或、非**。这些运算符的结果与其在英语中的含义类似。

例如，如果 x 大于 0 且小于 10，那么 x > 0 && x < 10 的结果为true；对于表达式 evenFlag || n \% 3 == 0，只要其中一个条件为true，即如果 evenFlag 为 true 或数字 n 能被 3 整除，那么这个表达式的结果就为 true。最后，运算符 ! 对 boolean 表达式求反，因此，如果 evenFlag 不为 true，则 !evenFlag 为 true。

逻辑运算符仅在必要时才计算第二个表达式的值。例如，true ||anything 的结果在任何情况下都为 true，因此 Java 无需计算表达式anything 的值。同样，false && anything 的结果在任何情况下都为 false。在可能的情况下忽略第二个操作数被称为短路（shortcircuit）求值，可与电路类比。短路求值可节省时间，在 anything 的值需要很长时间才能计算出时尤其如此。如果 anything 可能出现问题的话，这还可以避免不必要的错误。

如果你曾必须对包含逻辑运算符的表达式求反，以后也很可能遇到这样的情况。在这种情况下，德 · 摩根定律（De Morgan's laws）可以提供帮助：

- !(A && B) 与 !A || !B 等价
- !(A || B) 与 !A && !B 等价

上述列表表明，要对逻辑表达式求反，可分别对每一项求反，并使用相反的运算符。运算符 ! 的优先级比 && 和 || 高，因此不需要将 !A 和 !B分别放在括号中。

德 · 摩根定律也适用于关系运算符。在这种情况下，**对每一项求反意味着使用“相反”的运算符**：

- !(x < 5 && y == 3 ) 与 x > =5 || y! = 3 等价
- !(x >= 1 || y! = 7 ) 与 x < 1 && y == 7 等价

将这些示例大声地朗读出来可能会有所帮助。例如，“如果不希望 x 小于 5，且不希望 y 为 3，就意味着 x 必须大于或等于 5，且 y 不能为3。”

## 5.3 if 条件语句

为了编写有用的程序，几乎都需要检查添加并采取相应的措施。条件语句（conditional statement）提供了这样的功能。if 语句是 Java 中最简单的条件语句：

```java
if (x > 0) {
	System.out.println("x is positive");
}
```

括号内的表达式被称为条件，如果它为 true，那么将执行大括号内的语句，否则将跳过这个代码块。括号内的条件可以是任何 boolean 表达式。

还有一种包含两种可能性（分别由 if 和 else 标识）的条件语句。这些可能性称为分支（branch），由条件决定将执行哪个分支：

```java
if (x % 2 == 0) {
	System.out.println("x is even");
} else {
	System.out.println("x is odd");
}
```

如果 x 除以 2 的余数为 0，则 x 为偶数，因此上述代码片段显示相应的消息。如果不满足这个条件，则执行第二条打印语句。由于要么满足条件，要么不满足条件，因此只有一个分支会被执行。

包含多种可能性则需要用到 if else （切记最后一个必须要为else，否则会提示始终为true）：

```java
if (x / 2 > 0) {
    System.out.println("x is > 2");
}else if (x / 2 = 0) {
    System.out.println("x is = 2");
}else {
    System.out.println("x is < 0")
}
```

对于只有一条语句的分支来说，大括号是可选的，因此前一个示例可以写成下面这样：

```java
if (x % 2 == 0)
	System.out.println("x is even");
else
	System.out.println("x is odd");
```

然而，即便大括号是可有可无的，最好不要省略，这样可避免在 if 或else 代码块中添加语句时因忘记加大括号而导致错误。

```java
if (x > 0)
	System.out.println("x is positive");
	System.out.println("x is not zero");
```

这些代码没有正确地缩进，因此极具误导性。由于省略了大括号，只有第一个 println 是 if 语句的一部分。在编译器看来，上述代码实际上是以下这样的：

```java
if (x > 0) {
	System.out.println("x is positive");
}
	System.out.println("x is not zero");
```

因此，在任何情况下都将执行第二条 println 语句。即便是经验丰富的程序员也会犯这样的错误，只要在网上搜索 goto fail 就会有所了解了。

## 5.4 串接和嵌套

有时需要检查多个相关的条件，并在多种措施中选择一种方式。其中一种方法是将一系列的 if 和 else 语句串接（chaining）起来：

```java
if (x > 0) {
	System.out.println("x is positive");
} else if (x < 0) {
	System.out.println("x is negative");
} else {
	System.out.println("x is zero");
}
```

你可以想串接多长就串接多长，但太长可能难以阅读。为提高可读性，可使用标准的缩进方式，如这里的示例所示。将语句和大括号对齐可降低出现语法错误的可能性。

除了串接，还可以在一个条件语句中嵌套（nesting）另一个条件语句以作出复杂的决策。可将前面的示例重写为下面这样：

```java
package Chapter5;

import java.util.Scanner;
public class Work1 {
    /**
     * if条件语句,嵌套
     */
    public static void main(String[] args) {
        int a;
        Scanner in = new Scanner(System.in);
        System.out.print("请输入一个数字：");
        a = in.nextInt();
        if (a > 50) {
            System.out.println("你输入的数字大于50");
        } else {
            if (a == 50) {
                System.out.println("你输入的数字等于50");
            } else {
                System.out.println("你输入的数字小于50");
            }
        }
    }
}
```

外面的条件语句有两个分支，第一个分支包含一条打印语句，第二个分支包含另一个条件语句，该条件语句也有两个分支。这两个分支都是打印语句，但它们本来也可以是条件语句。这样的嵌套结构很常见，但很难快速地阅读它们。因此我们必须使用正确的缩进，以便这种结构易于理解。

## 5.5 标志变量

要想存储 true 或 false 的值，需要使用 boolean 变量，而要创建boolean 变量，可像下面这样做：

```java
boolean flag;
flag = true;
boolean testResult = false;
```

第 1 行是变量声明，第 2 行是赋值语句，而第 3 行在声明变量的同时给它赋值。由于关系运算符的结果为 boolean 值，因此可将比较结果存储在一个变量中：

```java
boolean evenFlag = (n % 2 == 0); // n为偶数时为true
boolean positiveFlag = (x > 0); // x为正数时为true
```

其中的括号并非必不可少，但可以让代码更容易理解。**以这种方式定义的变量被称为标志（flag）**，因为它指出或“标志”着条件是否满足。定义标志变量后，就可以在条件语句中使用了：

```java
if (evenFlag) {
	System.out.println("n was even when I checked it"); // evev 偶数
}
```

注意，你无需这样书写：if (evenFlag == true)，因为 evenFlag就是 boolean 值，可用于表示条件。同理，要检查标志是否为false，可像下面这样做：

```java
if (!evenFlag) {
	System.out.println("n was odd when I checked it"); // odd 奇数
}
```

演示代码：

```java
package Chapter5;

import java.util.Scanner;
public class Work2 {
    /**
     * 使用 boolean 变量判断数字是偶数还是奇数
     */
    public static void main(String[] args) {
        int n;
        Scanner in = new Scanner(System.in);
        System.out.print("请输入一个数字：");
        n = in.nextInt();
        boolean evenFlag = (n % 2 == 0);
        if (evenFlag) {
            System.out.println("你输入的数字是偶数");
        } else {
            System.out.println("你输入的数字是奇数");
        }
    }
}
```

## 5.6 return语句

return 语句允许还未到达末尾就终止方法。使用 return 语句的原因之一是检测到了错误条件：

```java
public static void printLogarithm(double x) {
	if (x <= 0.0) {
		System.err.println("Error: x must be positive."); // positive 正数
		return;
	}
	double result = Math.log(x);
	System.out.println("The log of x is " + result);
	}
```

这个示例定义了一个名为 printLogarithm 的方法，该方法将一个double 值作为形参（名为 x），用于检查 x 是否小于或等于 0，如果是这样的，那么就显示一条错误消息，再用 return 退出方法。这样将立即返回到调用这个方法的地方，而不执行这个方法的后面代码。

这个示例使用了 System.err，这是一个 OutputStream，通常用于显示错误消息和警告。对于 System.err 的输出，有些开发环境用不同的颜色显示或在独立的窗口中显示。

完整代码：

```java
package Chapter5;

import java.util.Scanner;
public class Work3 {
    /**
     * 定义一个 printLogarithm 方法求对数
     */
    public static void printLogarithm(double x) {
        if (x <= 0.0) {
            System.err.println("你输入的数字小于 0，输入错误");
            return;
        }
        double y = Math.log(x);
        System.out.println("你输入的数字的对数是：" + y);
    }
    public static void main(String[] args) {
        double x;
        Scanner in = new Scanner(System.in);
        System.out.print("请输入一个数字：");
        x = in.nextDouble();
        printLogarithm(x);
    }
}
```

## 5.7 验证输入

以下的方法调用了 5.6 节中的 printLogarithm：

```java
public static void scanDouble() {
	Scanner in = new Scanner(System.in);
	System.out.print("Enter a number: ");
	double x = in.nextDouble();
	printLogarithm(x);
}
```

这个示例调用了 nextDouble，因此 Scanner 将尝试读取一个 double值。如果用户输入的是一个浮点数，Scanner 将把它转换为 double值；但如果用户输入的是其他类型的值， Scanner 将引发InputMismatchException 异常。为防范这种错误，可在分析前检查输入：

```java
public static void scanDouble() {
	Scanner in = new Scanner(System.in);
	System.out.print("Enter a number: ");
	if (!in.hasNextDouble()) {
		String word = in.next();
		System.err.println(word + " is not a number");
		return;
	}
	double x = in.nextDouble();
	printLogarithm(x);
}
```

Scanner 类提供了方法 hasNextDouble，该方法**用于检查能否将输入流中的下一个标记转换为 double 值**。如果答案是肯定的，那么就可以调用 nextDouble，且不会引发异常。如果答案是否定的，那么就显示一条错误消息并返回。从 main 方法返回将导致程序终止。

完整代码：

```java
package Chapter5;

import java.util.Scanner;
public class Work4 {
    /**
     * 求对数并验证输入
     */
    public static void printLogarithm(double num) {
        if (num < 0) {
            System.out.println(num + " 小于 0，没有对数");
            return;
        } else if (num ==0) {
            System.out.println("0 没有对数");
            return;
        }
        double Logarithm = Math.log(num);
        System.out.println(num + " 的对数是：" + Logarithm);
    }

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("请输入一个数字：");
        /* 验证输入，hasNextDouble用于检查能否将输入流中的下一个标记转换为double值,
           !in.hasNexDouble() 这个语句会检查是否有下一个 double 类型的输入，
           如果没有，则会提示用户输入的不是数字，并且直接结束程序 */
        if (!in.hasNextDouble()) {
            String word = in.next();
            System.err.println(word + " 不是一个数字");
            return; // 结束 if 条件语句
        }
        double num = in.nextDouble(); 
        printLogarithm(num);
    }
}
```

## 5.8 递归方法

介绍了条件语句后，现在可以探索程序能做的最神奇的事情之一了——递归（recursion）。思考下面的示例：

```java
public static void countdown(int n) {
    if (n == 0) {
        System.out.println("Blastoff!");
    } else {
        System.out.println(n);
        countdown(n - 1);
    }
}
```

这个方法名为 countdown，它将一个整数作为参数。如果这个参数为零，它就显示单词 Blastoff，否则就显示这个数字，再用实参 n-1 调用自己。调用自己的方法称为递归方法（recursive method）。

如果在 main 中调用 countdown(3)，结果将如何？

```
这次执行 countdown 时，n==3；由于 n 不为零，因此它显示值3，再调用自己……
	这次执行 countdown 时，n==2；由于 n 不为零，因此它显示值2，再调用自己……
		这次执行 countdown 时，n==1；由于 n 不为零，因此它显示值1，再调用自己……
			这次执行 countdown 时，n==0；由于n 为零，因此它显示值“Blastoff!”再返			回。
		使用 1 调用的 countdown 返回。
	使用 2 调用的 countdown 返回。
使用 3 调用的 countdown 返回。
```

至此返回了 main，于是输出类似于下面这样：

```
3
2
1
Blastoff!
```

再来看一个示例。在这个示例中，我们将重新编写 4.3 节中的方法newLine 和 threeLine：

```java
public static void newLine() {
	System.out.println();
}
public static void threeLine() {
	newLine();
	newLine();
	newLine();
}
```

虽然这些方法管用，但如果要显示 2 个或 100 个空行，它们并不能提供帮助。下面是一种更佳的解决方案：

```java
public static void nLines(int n) {
	if (n > 0) {
		System.out.println();
		nLines(n - 1);
	}
}
```

这个方法将一个整数（n）作为形参，并显示了 n 个空行。其结构与countdown 类似：只要 *n* 大于零，就显示一个空行，然后调用自己再显示 *n*-1 个空行。显示的总空行数为 1+(n - 1)，即我们希望的 *n* 个。

第一个示例代码：

```java
package Chapter5;

import java.util.Scanner;
public class Work5 {
    /**
     * 递归方法，创建一个 countdown 方法进行倒计时
     */
    public static void countdown(int n) {
        if (n == 0) {
            System.out.println("发射！");
        } else if (n > 0) {
            System.out.println(n);
            countdown(n - 1);
        }
    }

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("请输入一个数字：");
        int n = in.nextInt();
        countdown(n);
    }
}
```

第二个示例代码：

```java
package Chapter5;

import java.util.Scanner;
public class Work6 {
    /**
     * 用递归输出 n 个空行
     */
    public static void nLine(int n) {
        if (n > 0) {
            System.out.println();
            nLine(n - 1);
        }
    }

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("你想输出几个空行：");
        int n = in.nextInt();
        nLine(n);
        System.out.println("已输出 " + n + " 个空行");
    }
}
```

## 5.10 二进制数

前面的方法 countdown 由三部分组成：(1) 检查基线条件；(2) 显示输出；(3) 执行递归调用。如果将第 2 步和第 3 步的顺序调换一下，即先执行递归调用再显示输出，你认为结果将如何呢？

```java
public static void countup(int n) {
	if (n == 0) {
		System.out.println("Blastoff!");
	} else {
		countup(n - 1);
		System.out.println(n);
	}
}
```

栈图与以前相同，并且这个方法也将被调用 *n* 次，但System.out.println 将在递归调用返回前执行，因此结果是顺数而不是倒数：

```
Blastoff!
1
2
3
```

在按相反的顺序更容易计算结果时，可利用这种行为。例如，要想将十进制整数转换为用二进制（binary）表示，可反复地除以 2：

```
23 / 2 is 11 remainder 1
11 / 2 is 5 remainder 1
5 / 2 is 2 remainder 1
2 / 2 is 1 remainder 0
1 / 2 is 0 remainder 1
```

从下往上阅读这些余数就可得到 23 的二进制表示——10111。要想了解更多有关二进制的详细信息，请参阅 https://baike.baidu.com/item/%E4%BA%8C%E8%BF%9B%E5%88%B6/361457 。

## 5.11 术语表

| 术语              | 含义                                                         |
| ----------------- | ------------------------------------------------------------ |
| boolean           | 一种只有两个可能取值（true 和 false）的数据类型              |
| 关系运算符        | 对两个值进行比较，从而得到一个表示两者关系的 boolean 值的运算符 |
| 逻辑运算符        | 将两个 boolean 值合并成一个 boolean 值的运算符               |
| 短路              | 执行逻辑运算符的一种方式，仅在必要时计算第二个操作数的值     |
| 德 **·** 摩根定律 | 指出如何对逻辑表达式求反的数学规则                           |
| 条件语句          | 根据条件确定执行哪些语句的语句                               |
| 分支              | 条件语句中多个可能执行的语句块之一                           |
| 串接              | 一种将多个条件语句依次连接起来的方式                         |
| 嵌套              | 在一个条件语句的分支中包含另一个条件语句                     |
| 标志              | 表示条件或状态的变量，通常为 boolean 变量                    |
| 递归              | 在当前执行的方法中再调用该方法的过程                         |
| 递归方法          | 调用自己的方法，通常提供不同的实参                           |
| 基线条件          | 导致递归方法不再进行递归调用的条件                           |
| 二进制(binary)    | 只用 0 和 1 表示数字的计数系统，也被称为“以 2 为基数”的计数系 |

## 5.12 练习

#### 第一题

逻辑运算符可简化嵌套的条件语句。例如，你能只用一条 if 语句重写下面的代码吗？

```java
if (x > 0) {
	if (x < 10) {
		System.out.println("positive single digit number.");
	}
}
```

#### 第二题

这个练习的目的是将一个大问题分解成多个小问题，并编写简单的方法来解决这些小问题。下面是歌曲 *99 Bottles of Beer* 的第一段歌词：
99 bottles of beer on the wall,
99 bottles of beer,ya' take one down, ya' pass it around,
98 bottles of beer on the wall.
接下来的各段歌词与此相同，只是每段中的瓶数依次少 1。而最后一段歌词如下：
No bottles of beer on the wall,
no bottles of beer,
ya' can't take one down, ya' can't pass it around,
'cause there are no more bottles of beer on the wall!
至此，这个歌曲总算结束了。
请编写一个显示这首歌全部歌词的程序。程序应包含一个承担重任的递归方法，但你可能还需要编写其他方法。可在程序编写期间用较少的段数（如 3）进行测试。

#### 第三题

学习条件语句后，现在我们可以回过头去完善练习 3-4 中的“猜数”游戏了。写一个程序，它可以选择一个随机数，让用户猜这个数，并显示用户猜的数字与这个随机数的差距。然后修改这个程序，让程序可以告诉用户他猜的数字太大还是太小，并提示用户再猜一次。每次修改只添加少量的代码，并边修改边测试。这个程序应不断运行，直到用户猜对为止。
提示：使用两个方法，并将其中一个编写为递归方法。

#### 第一题代码：

```java
package Chapter5;

import java.util.Scanner;
public class Work7 {
    /**
     * 练习：用一条 if 语句重写下列代码

     if (x > 0) {
        if (x < 10) {
            System.out.println("正个位数。");
        }
     }
     */

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("请输入一个数字：");
        int x = in.nextInt();
        if (x > 0 && x < 10) {
            System.out.println("正个位数。");
        } else {
            System.out.println("不是正个位数。");
        }
    }
}
```

#### 第二题代码：

```java
package Chapter5;

public class Work8 {
    /**
     * 99 bottles of beer on the wall,
     * 99 bottles of beer,ya' take one down, ya' pass it around,
     * 98 bottles of beer on the wall.
     * 接下来的各段歌词与此相同，只是每段中的瓶数依次少 1。而最后一段歌词如下：
     * No bottles of beer on the wall,
     * no bottles of beer,
     * ya' can't take one down, ya' can't pass it around,
     * 'cause there are no more bottles of beer on the wall!
     */
    public static void lyricLoop(int n) {
        if (n > 1) {
            System.out.println(n + " bottles of beer on the wall,\n" +
                    n + " bottles of beer,ya' take one down, ya' pass it around,\n" +
                    (n - 1) +" bottles of beer on the wall.");
            lyricLoop(n - 1);
        } else if (n == 1) {
            System.out.println("1 bottles of beer on the wall, \n" +
                               "1 bottles of beer,\n" +
                               "no bottles of beer on the wall.");
            lyricLoop(0);
        } else if (n == 0) {
            System.out.println("No bottles of beer on the wall,\n" +
                               "no bottles of beer,\n" +
                               "ya' can't take one down, ya' can't pass it around,\n" +
                               "'cause there are no more bottles of beer on the wall!");
        }
    }

    public static void main(String[] args) {
        int n = 99;
        lyricLoop(99);
    }
}
```

#### 第三题代码：

```java
package Chapter5;

import java.util.Random;
import java.util.Scanner;

public class Work9 {
    /**
     * 写一个程序，它可以选择一个随机数，让用户猜这个数，并显示用户猜的数字与这个随机数的差距。
     * 然后修改这个程序，让程序可以告诉用户他猜的数字太大还是太小，并提示用户再猜一次。
     * 每次修改只添加少量的代码，并边修改边测试。这个程序应不断运行，直到用户猜对为止。
     * 提示：使用两个方法，并将其中一个编写为递归方法。
     */
    public static void compare(int num, int random) {
        Scanner in = new Scanner(System.in);
        if (num > random) {
            System.out.print("你输入的数字大于随机数\n" +
                               "请重新输入一个数字：");
            int x = in.nextInt();
            compare(x, random);
        } else if (num < random) {
            System.out.print("你输入的数字小于随机数\n" +
                               "请重新输入一个数字：");
            int y = in.nextInt();
            compare(y, random);
        } else {
            System.out.println("你输入的数字等于随机数");
        }
    }

    public static void main(String[] args) {
        Random random = new Random();
        int i = random.nextInt(100);
        Scanner in = new Scanner(System.in);
        System.out.print("请输入一个数字：");
        int num = in.nextInt();
        compare(num, i);
    }
}
```

# 6 值方法

在前面，使用的一些方法会返回值，如 Math 类的方法。但编写的方法都是 void 方法，即不返回值。这一章会编写返回值的方法，这些方法被称为值方法（value method）。

## 6.1 返回值

调用 void 方法时，调用代码通常独占一行。例如，以下是 5.8 节中的countup 方法：

```java
public static void countup(int n) {
	if (n == 0) {
		System.out.println("Blastoff!");
	} else {
		countup(n - 1);
		System.out.println(n);
	}
}
```

下面的代码演示了如何调用它：

```java
countup(3);
System.out.println("Have a nice day.");
```

另一方面，调用值方法时，必须对其返回值做些什么。我们通常将其赋给变量或用于表达式中，如下所示：

```java
double error = Math.abs(expected - actual); // abs() 取绝对值
double height = radius * Math.sin(angle); // radius 半径
```

与 void 方法相比，值方法有两个不同之处：声明了返回值的类型，即返回类型（return type）；至少使用了一条 return 语句来提供返回值（return value）。

下面是一个示例：calculateArea 接受一个 double 参数，并返回以该参数值为半径的圆的面积：

```java
public static double calculateArea(double radius) {
	double result = Math.PI * radius * radius;
    return result;
}
```

与前面一样，这个方法也是公有的、静态的，但在以前**为 void 的地方使用了 double，这意味着该方法的返回值为 double 值**。最后一行是一种新型的 return 语句，其中包含一个返回值。这条语句的意思是，立即从这个方法返回，并将接下来的表达式用作返回值。这个表达式的复杂程度没有限制，因此我们可以更简洁地编写这个方法：

```java
public static double calculateArea(double radius) {
	return Math.PI * radius * radius;
}
```

然而，使用 result 这样的临时变量（temporary variable）通常可以简化调试工作，在用交互式调试器以步进方式执行代码时尤其如此。

return 语句中的表达式类型必须与方法的返回类型一致。将返回类型声明为 double 时，其实就是承诺这个方法最终将生成一个 double值；如果使用的 return 语句不包含表达式或包含的表达式的类型不正确，那么编译器将显示错误消息。

有时候，使用多条 return 语句很有用，例如，在条件语句的每个分支中使用一条：

```java
public static double absoluteValue(double x) {
	if (x < 0) {
		return -x;
	} else {
		return x;
	}
}
```

由于这些 return 语句位于条件语句中，因此只会执行其中一条。只要执行了其中任何一条 return 语句，这个方法就会立即结束，不再执行其他的语句。位于 return 语句后，且与之同属一个代码块的代码以及其他地方根本不会执行的代码被称为无用代码（dead code）。如果程序包含无用代码，编译器将显示错误消息——unreachable statement（不可达语句）。

例如，下面的方法就包含无用代码：

```java
public static double absoluteValue(double x) {
	if (x < 0) {
		return -x;
	} else {
		return x;
	}
	System.out.println("This line is dead.");
}
```

**将 return 语句放在条件语句中时，必须确保程序中的每条可能的执行路径都包含一条 return 语句。**如果情况并非如此，编译器将指出这一点。例如，下面的方法就不完整：

```java
public static double absoluteValue(double x) {
	if (x < 0) {
		return -x;
	} else if (x > 0) {
		return x;
	}
	// 语法错误
}
```

**如果 x 为 0，那么将不满足任何上述条件，这会导致方法的执行路径中没有 return 语句。**在这种情况下，编译器显示的错误消息可能类似于这样：missing return statement（缺少 return 语句）。这条错误消息令人迷惑，因为已经有两条 return 语句了。

正确的返回方法必须每条可能性都有 return 语句，比如：

```java
public static double absoluteValue(double x) {
	if (x < 0) {
		return -x;
	} else if (x > 0) {
		return x;
	} else {
        return x;
    }
}
```

完整代码：

```java
package Chapter6;

import java.util.Scanner;

public class Work1 {

    /**
     * 求绝对值
     */
    public static double absoluteValue(double a) {
        if (a > 0) {
            return a;
        } else if (a == 0) {
            return a;
        } else {
            return - a;
        }
    }

    public static void main(String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("请输入一个数字：");
        double n = in.nextDouble();
        System.out.println(absoluteValue(n));
    }
}
```

## 6.2 编写方法

相对于在不尝试编译并运行的情况下就编写大量代码，然后再花大量的时间调试代码，渐进开发（incremental development）是一种更好的方法，这种方法的要点如下。

- 先编写一个能够运行的简单程序，再逐步修改。这样的话，无论什么时候出现错误，你都知道该检查哪些地方。
- 用变量存储中间值，以便能够用打印语句或调试器检查它们。
- 程序能够正确运行后再将多条语句合并为复合表达式（前提是这样不会导致程序更难理解）。

举个例子，假设你要根据两个点的坐标 (*x*1 , *y*1 ) 和 (*x*2 , *y*2 ) 计算它们之间的距离，可使用下面的公式：

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230317162735997.png" alt="image-20230317162735997" style="zoom: 80%;" />

首先要考虑的是，用 Java 编写 distance 方法会是什么样的呢？换而言之，输入（形参）是什么？输出（返回值）又是什么？在这个示例中，输入是两个点；而要表示这两个点，显而易见的方法是使用 4 个double 值。返回值是距离，其类型也应为 double。

据此就可以编写这个方法的轮廓了，这种轮廓有时被称为存根（stub），其中包含了方法的特征标和一条 return 语句：

```java
public static double distance (double x1, double y1, double x2, double y2) {
	return 0.0;
}
```

这条 return 语句是一个占位符，在确保程序能够通过编译方面必不可少。当前，这个程序并没有做什么有用的事情，但添加更多代码前有必要对其进行编译，以便发现语法错误。

开发新方法前先考虑测试是一个不错的主意，能够帮助你搞明白如何实现这些方法。要测试方法，可在 main 中调用，并将样本值用作实参：

```java
double dist = distance(1.0, 2.0, 4.0, 6.0); // dist 距离
```

坐标指定的两点间的水平距离为 3.0，垂直距离为 4.0，因此结果应为5.0。测试方法时知道正确答案很有帮助。

存根通过编译后，我们就可以开始添加代码了——每次一行。每次修改后都再次编译并运行程序。无论什么时候出现错误，我们都很清楚该检查什么地方：添加的最后一行代码。

下一步是计算（*x*2 - *x*1）和（*y*2 - *y*1）的差值。我们将这些值分别存储在临时变量 dx 和 dy 中。

```java
javajavajavapublic static double distance(double x1, double y1, double x2, double y2) {
	double dx = x2 - x1;
	double dy = y2 - y1;
	System.out.println("dx is " + dx);
	System.out.println("dy is " + dy);
	return 0.0;
}
```

打印语句让我们能够检查这些中间值，它们应该分别为 3.0 和4.0，确定它们正确后再继续添加代码。可在方法编写好后删除这些打印语句；类似这样的代码被称为脚手架(scaffolding)，因为它们可以帮助你创建程序，却不是最终产品的组成部分。

下一步是计算 dx 和 dy 的平方和。为此可使用方法 Math.pow，但更简单的方式是将它们分别与自己相乘：

```java
public static double distance(double x1, double y1, double x2, double y2) {
	double dx = x2 - x1;
	double dy = y2 - y1;
	double dsquared = dx * dx + dy * dy;
	System.out.println("dsquared is " + dsquared);
	return 0.0;
}
```

同样，此时应编译并运行该程序，同时也要检查中间值——应为 25.0。

终于，我们可以用 Math.sqrt 来计算并返回结果：

```java
public static double distance(double x1, double y1, double x2, double y2) {
	double dx = x2 - x1;
	double dy = y2 - y1;
	double dsquared = dx * dx + dy * dy;
	double result = Math.sqrt(dsquared);
	return result;
}
```

等编程经验更丰富后，你就可以一次编写并调试多行代码。即便如此，渐进开发也可为你节省大量的时间。

完整代码：

```java
package Chapter6;

import java.util.Scanner;
public class Work2 {
    /**
     * 根据两个点的坐标 (*x*1 , *y*1 ) 和 (*x*2 , *y*2 ) 计算它们之间的距离
     */
    public static double distance (double x1, double y1, double x2, double y2) {
        double dx = x1 - x2;
        double dy = y1 - y2;
        double dsquared = dx * dx + dy * dy;
        return Math.sqrt(dsquared);
    }

    public static void coordinateValue () {
        Scanner in = new Scanner(System.in);
        System.out.print("请输入 x1 ：");
        double x1 = in.nextDouble();
        System.out.print("请输入 y1 ：");
        double y1 = in.nextDouble();
        System.out.print("请输入 x2 ：");
        double x2 = in.nextDouble();
        System.out.print("请输入 y2 ：");
        double y2 = in.nextDouble();
        System.out.println(distance(x1, y1, x2, y2));
    }

    public static void main (String[] args) {
        coordinateValue();
    }
}
```

## 6.3 方法组合

定义新方法后，可将其用于表达式中或用来创建其他方法。例如，假设有人向你提供了两个点——圆心和圆周上的一点，并要求你计算这个圆的面积。那么我们可以假设圆心坐标存储在变量 xc 和 yc 中，而圆周上那个点的坐标存储在 xp 和 yp 中。

第一步要做的是计算出这个圆的半径，即两个点间的距离。所幸我们已经有执行这种计算的方法 —— distance：

```java
double radius = distance(xc, yc, xp, yp);
```

第二步是根据得到的半径计算圆的面积。我们也有执行这种计算的方法—	—calculateArea：

```java
double area = calculateArea(radius);
return area;
```

将这些代码放到一个新的方法中，结果如下：

```java
public static double circleArea (double xc, double yc, double xp, double yp) {
	double radius = distance(xc, yc, xp, yp);
	double area = calculateArea(radius);
	return area;
}
```

临时变量 radius 和 area 对开发和调试来说很有用，但是程序能正确运行后就可以组合方法调用，从而让程序更简洁：

```java
public static double circleArea (double xc, double yc, double xp, double yp) {
	return calculateArea(distance(xc, yc, xp, yp));
}
```

这个示例演示了功能分解（functional decomposition）的过程，即将复杂的计算分成简单的方法，分别对这些方法进行测试，然后再组合这些方法来执行计算。这种做法可缩短调试时间，并且编写出来的代码准确度更高且更容易维护。

完整代码：

```java
package Chapter6;

import java.util.Scanner;
public class Work3 {
    /**
     * 计算圆的面积 圆心点：(xc , yc)  圆上点：(xp, yp)
     */

    // 圆的面积
    public static double circleArea(double xc, double yc, double xp, double yp) {
        double radius = distance(xc, yc, xp, yp); // 调用 radius 方法得到半径
        return calculateArea(radius); // 调用 calculateArea 方法得到面积然后返回给 main
    }

    // 计算面积
    public static double calculateArea(double radius) {
        return Math.PI * radius * radius; // 计算圆的面积然后返回给 circleArea 方法
    }

    // 计算半径
    public static double distance (double xc, double yc, double xp, double yp) {
        double dx = xc - xp; // 计算横坐标之间的距离
        double dy = yc - yp; // 计算纵坐标之间的距离
        double dsquared = dx * dx + dy * dy; // 计算两点之间的距离过程中的一步
        return Math.sqrt(dsquared); // 输出计算两点间的距离，将结果返回给  calculateArea 方法
    }

    public static void main (String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("请输入圆心点的 x ：");
        double xc = in.nextDouble();
        System.out.print("请输入圆心点的 y ：");
        double yc = in.nextDouble();
        System.out.print("请输入圆上点的 x ：");
        double xp = in.nextDouble();
        System.out.print("请输入圆上点的 y ：");
        double yp = in.nextDouble();
        System.out.println(circleArea(xc, yc, xp, yp));
    }
}
```

## 6.4 重载

circleArea 和 calculateArea 的功能类似，都用于计算圆的面积，只是接受的参数不同：要想调用 calculateArea，必须提供半径，而调用 circleArea 则需要提供两个点的坐标。

如果两个方法所做的事情相同，那么自然应该给它们指定相同的名称。**多个方法同名被称为重载（overloading），这在 Java 中是合法的，但前提条件是每个版本接受的参数不同。**因此，我们可以将 circleArea 重命名为 calculateArea：

```java
public static double calculateArea (double xc, double yc, double xp, double yp) {
	return calculateArea(distance(xc, yc, xp, yp));
}
```

请注意，这个方法并不是递归方法。当调用重载的方法时，Java 会根据你提供的实参判断要调用的是哪个版本。如果编写如下代码：

```java
double x = calculateArea(3.0);
```

Java 将查找一个以 double 值作为参数的方法 calculateArea，因此它将使用第一个版本，这个版本将提供的实参视为半径。如果编写如下代码：

```java
double y = calculateArea(1.0, 2.0, 4.0, 6.0);
```

Java 将使用 calculateArea 的第二个版本，将提供的实参视为两个点的坐标。在这个示例中，第二个版本调用了第一个版本。

很多 Java 方法都是重载的，这意味着它们有不同的版本，但每个版本的形参类型或数量各不相同。例如，print 和 println 都有接受单个参数（任何数据类型均可）的版本；而 Math 类的 abs 方法既有用于doube 值的版本，也有用于 int 值的版本。

虽然重载是一项很有用的功能，但还是应该慎用。如果在调试方法的一个版本时，不小心调用了另一个版本，可能会把自己绕进去。

## 6.5 boolean方法

方法可返回任何类型的值，当然也包括 boolean 值。返回 boolean 值的方法非常适合隐藏测试，如下所示：

```java
public static boolean isSingleDigit(int x) {
	if (x > -10 && x < 10) {
		return true;
	} else {
		return false;
	}
}
```

这个方法名为 isSingleDigit。通常会给 boolean 方法指定一个像一般疑问句的名称。因为返回类型为 boolean，所以 return 语句中的表达式必须是 boolean 表达式。

虽然这些代码比实际需要的要长，但是很简单。表达式 `x >- 10 && x< 10` 的类型就是 boolean，因此完全可以直接返回它（不需要 if 语句）：

```java
public static boolean isSingleDigit(int x) {
	return x > -10 && x < 10;
}
```

在 main 中，你可以像通常那样调用这个方法：

```java
System.out.println(isSingleDigit(2));
boolean bigFlag = !isSingleDigit(17);
```

第 1 行显示 true，因为 2 是一个个位数；第 2 行将 bigFlag 设置为true，因为 17 不是个位数。

条件语句常常将 boolean 方法的结果用作条件：

```java
if (isSingleDigit(z)) {
	System.out.println("z is small");
} else {
	System.out.println("z is big");
}
```

像这样的语句几乎都可解读为“如果 z 是个位数，就打印……否则打印……”。

完整代码：

```java
package Chapter6;

import java.util.Scanner;
public class Work4 {

    /**
     * 检查 x 是否为个位数
     *
     * @param x 需要检查的整数
     * @return 如果 x 是个位数，返回 true，否则返回 false
     */
    public static boolean isSingleDigit (int x) {
       return x > -10 && x < 10;
   }
   
   public static void resultPrint (int z) {
        // 接收 isSingleDigit 方法返回的boolean值进行判断
       if (isSingleDigit(z)) {
           System.out.println(z + " is a single digit.");
       } else {
           System.out.println(z + " is not a single digit.");
       }
   }

   public static void main (String[] args) {
       Scanner in = new Scanner(System.in);
       System.out.print("请输入一个数字：");
       int x = in.nextInt();
       resultPrint(x); // 调用 resultPrint 方法输出判断结果
   }
}
```

## 6.6 Javadoc标签

在 4.9 节中讨论了如何用 /** 编写文档注释。一般而言，最好给每个类和方法都编写文档，这样其他程序员无需阅读代码就能知道它们是做什么的。

为将文档分成多个部分，Javadoc 支持以 @ 打头的可选标签（tag）。例如，可用标签 @param 和 @return 提供有关形参和返回值的额外信息。

```java
/**
* 检查整数x是否是个位数
*
* @param x 要检查的整数
* @return 如果x是个位数，返回true，否则返回false
*/
public static boolean isSingleDigit(int x) {
    if (x > -10 && x < 10) {
		return true;
	} else {
		return false;
	}
}
```

如果方法有多个形参，那么应该用不同的 @param 标签描述每个形参。void 方法没有返回值，因此不需要 @return 标签。

## 6.7 递归

学习完返回值的方法后，你掌握的 Java 编程知识就是图灵完备的（Turing complete）了。这意味着你能用 Java 来计算任何可计算的东西，只要“可计算”的定义是合理的。这个概念是由阿隆佐 · 邱奇（Alonzo Church）和阿兰 · 图灵（Alan Turing）提出的，因此被称为邱奇—图灵论题。

为了让你了解学过的工具能做哪些事情，我们来看一些方法，这些方法可用于计算以递归方式定义的函数。递归定义引用了当前定义的东西，从这种意义上说，它类似于循环定义。

当然，真正意义上的循环定义用处不大，请看以下定义。

- 递归（recursive）

  用于描述递归的方法。

如果在字典中看到这个定义，你可能非常恼火。但如果用 Google 搜索 recursion，它将显示 Did you mean: recursion，这是一个只有知道内情的人才懂的玩笑。

很多数学函数都是以递归的方式定义的，因为这常常是最简单的方式。

例如，整数 *n* 的阶乘（factorial，表示为 *n*!）的定义类似于以下这样：

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230320093746558.png" alt="image-20230320093746558" style="zoom: 50%;" />

**请不要将数学符号 ! 同 Java 运算符 ! 混为一谈，前者表示阶乘，后者表示逻辑非。**上述定义指出，factorial(0) 为 1，而 factorial(n) 为n*factorial(n - 1)。

因此，`factorial(3) 为 3*factorial(2)；`
`factorial(2) 为2*factorial(1)；`
`factorial(1) 为1*factorial(0)；`
`factorial(0) 为 1。`通过整合，可以得到factorial(3) 为 `3*2*1*1`，即 6。

如果能用公式表示递归定义，那么就可以轻松地编写有关的计算方法。为此，首先需要确定形参和返回类型。因为阶乘是针对整数定义的，所以计算阶乘的方法接受一个 int 形参，并返回一个 int 值。以下代码很好地表示了这一点：

```java
public static int factorial(int n) {
	return 0;
}
```

接下来需要考虑基线条件。如果提供的实参为 0，则返回 1。

```java
public static int factorial(int n) {
	if (n == 0) {
		return 1;
}
	return 0;
}
```

否则，就需要执行递归调用来计算 *n*-1 的阶乘，并将结果乘以 *n*（这是比较有趣的部分）：

```java
public static int factorial(int n) {
	if (n == 0) {
		return 1;
	}
	int recurse = factorial(n - 1);
	int result = n * recurse;
	return result;
}
```

这个程序的执行流程与 5.8 节中的 countdown 类似。如果用 3 来调用 factorial，执行流程将如下所示。

```
因为 n 为 3，所以执行第二个分支——计算 n-1 的阶乘……
	因为 n 为 2，所以执行第二个分支——计算 n-1 的阶乘……
		因为 n 为 1，所以执行第二个分支——计算 n-1 的阶乘……
			因为 n 为 0，所以执行第一个分支——立即返回 1。
		将返回值（1）乘以 n（1），并将结果返回。
	将返回值（1）乘以 n（2），并将结果返回。
将返回值（2）乘以 n（3），并将结果（6）返回给 factorial(3) 的调用者。
```

下图显示了这个调用序列的栈图，其中的返回值沿栈向上传递。注意，最后一个栈帧中没有 recurse 和 result，这是因为当 n == 0时，声明了这些变量的代码不会被执行。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230320094607316.png" alt="image-20230320094607316" style="zoom: 50%;" />

完整代码：

```java
package Chapter6;
// 递归阶乘运算
import java.util.Scanner;
public class Work5 {
    /**
     * 使用递归计算阶乘
     * @param n 计算 n 的阶乘
     * @return 返回阶乘的结果
     */
    public static int factorial (int n) {
        if (n == 0) { // 用于返回1的阶乘的结果
            return 1;
        }
        //保存前一项阶乘的结果 ，factorial(n - 1)会不断递归到 factorial(0)，用它来计算1的阶乘
        int recurse = factorial(n - 1); // n - 1 的阶乘
        int result = n * recurse; // n 的阶乘
        return result; // 这里是返回阶乘结果 n * ( n - 1 ) * …… 1
    }

    public static void main (String[] args) {
         Scanner in = new Scanner(System.in);
         System.out.print("请输入一个数字：");
         int n = in.nextInt();
         System.out.println(factorial(n));
    }
}
```

## 6.8 姑且相信

遵循执行流程是阅读程序的方式之一，但这种方式很快就会让你不堪重负。另一种方式是姑且相信（leap of faith）：遇到方法调用时，不沿执行流程前行，而假设被调用的方法能够正确地工作并返回合适的值。

事实上，你在用 Java 库中的方法时，就践行了姑且相信的理念：调用Math.cos 或 System.out.println 时，你并不检查这些方法的实现，而是假定它们能够正确地工作。

对于自己编写的方法，你也应该采取这种做法。例如，我们在 6.5 节中编写了一个名为 isSingleDigit 的方法，用来判断一个数字是否在0~9。通过测试和检查代码确定这个方法正确后，我们就可在使用时免去重复查看实现。

递归方法也应如此。遇到递归调用时，应假定递归调用可以正确工作，而不沿执行流程前行。例如，“如果能计算出 *n*-1 的阶乘，就能计算出 *n* 的阶乘，这样对吗？”没错，只需再乘以 *n* 即可。

当然，假定未编写好的方法能够正确地运行让人觉得很别扭，这正是我们称之为“姑且相信”的原因所在！

## 6.9 再举一个例子

另一个以递归方式定义的常见函数是斐波纳契数列，其定义如下：

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230320101754490.png" alt="image-20230320101754490" style="zoom:50%;" />

如果将该定义转换为 Java 代码，结果如下：

```java
public static int fibonacci(int n) {
	if (n == 1 || n == 2) {
		return 1;
	}
	return fibonacci(n - 1) + fibonacci(n - 2);
}
```

如果试图沿着上述代码的流程执行，即便 n 的值很小，你也会遇到很多麻烦。但如果采取姑且相信的做法，即假设两个递归调用能够正确地工作，那么就能清楚地知道结果就是这两个递归调用的返回值之和。

## 6.10 术语表

| 术语       | 含义                                                         |
| ---------- | ------------------------------------------------------------ |
| void方法   | 不返回值的方法。                                             |
| 值方法     | 返回值的方法。                                               |
| 返回类型   | 方法返回的值的类型。                                         |
| 返回值     | 方法调用的结果。                                             |
| 临时变量   | 短期的变量，通常用于调试。                                   |
| 无用代码   | 程序中根本不会执行的代码，通常是因为其位于 return 语句的后面。 |
| 渐行开发   | 创建程序的一种流程，每次只编写几行代码，并立即进行编译和测试。 |
| 存根       | 未完成的方法的占位符，旨在让类能够通过编译。                 |
| 脚手架     | 在程序开发期间使用但不包含在最终版本中的代码。               |
| 功能分解   | 将复杂的计算分成多个简单的方法，再组合这些方法来执行计算。   |
| 重载       | 定义了多个名称相同但形参不同的方法。                         |
| 标签       | 以 @ 打头的标记，Javadoc 根据它们将文档分成多个部分。        |
| 图灵完备的 | 编程语言能够实现任何理论上可行的算法。                       |
| 阶乘       | 将从 1 到给定整数的所有整数相乘。                            |
| 姑且相信   | 阅读递归程序的一种方式，假设递归调用可以正确地工作，而不沿执行流程前行。 |

## 6.11 练习

#### 第一题

编写一个名为 isDivisible 的方法，让它接受两个整数——n 和 m，并在 n 能被 m 整除时返回 true，否则返回 false。

#### 第二题

给定 3 根棍子，可能能够将它们排列成三角形，也可能不行。例如，如果其中一根棍子长 12 英寸，另外两根都为 1 英寸，那么就无法将 3 根棍子相互相连。给定任意 3 根棍子的长度，可通过下面的简单测试来判断它们能否组成三角形：
只要其中 1 根棍子的长度大于其他 2 根棍子的总长，它们就无法组成三角形。
请编写一个名为 isTriangle 的方法，让它接受 3 个整数参数，并根据长度分别为这 3 个整数的棍子能否组成三角形而返回 true 或 false。

#### 第三题

很多计算都可用“乘加”运算来更简洁地表示出来，这种运算接受 3 个操作数，并计算 a * b + c 的结果。有些处理器甚至提供了对浮点数执行这种运算的硬件实现。
(1) 创建一个程序。
(2) 编写一个名为 multadd 的方法，让它接受 3 个 double 参数，并返回 a * b + c。
(3) 编写一个 main 方法，并在其中测试方法 multadd：调用 multadd并传递几个简单的实参，如 1.0、2.0、3.0。
(4) 另外，在 main 中用方法 multadd 来计算下述表达式的值：
<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230320111609294.png" alt="image-20230320111609294" style="zoom:50%;" />
(5) 编写一个名为 expSum 的方法，让它接受一个 double 参数，并调用multadd 来计算下述表达式的值：
<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230320111640580.png" alt="image-20230320111640580" style="zoom:50%;" />



#### 第一题代码：

```java
package Chapter6;
/*
   练习1
*/
import java.util.Scanner;
public class Work6 {
    /**
     * 方法 isDivisible 判断 m 是否能被 n 整除
     * @param n 被除数
     * @param m 除数
     * @return 如果 m 能被 n 整除，返回 true，反之返回 false
     */
    public static boolean isDivisible (int n, int m) {
        int divide = m % n;
        return divide == 0;
    }

    public static void main (String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("请输入 m ：");
        int m = in.nextInt();
        System.out.print("请输入 n ：");
        int n = in.nextInt();
        System.out.println(isDivisible(n, m));
    }
}
```

#### 第二题代码：

```java
package Chapter6;
/*
   练习2
*/
import java.util.Scanner;
public class Work7 {

    /**
     * 判断是否为三角形
     * @param x 三角形的长
     * @param y 三角形的宽
     * @param z 三角形的高
     * @return 如果两边之和与第三边相减大于 0，返回 true，反之返回 false
     */
    public static boolean isTriangle (int x, int y, int z) {
        int a = x + y - z;
        int b = x + z - y;
        int c = y + z - x;
        int multiply = a * b * c; 
        // 将三次两边之和与第三边相减得出来的结果相乘，判断是否大于 0
        return multiply > 0;
    }

    public static void sidePrint () {
        Scanner in = new Scanner(System.in);
        System.out.print("请输入长：");
        int x = in.nextInt();
        System.out.print("请输入宽：");
        int y = in.nextInt();
        System.out.print("请输入高：");
        int h = in.nextInt();
        System.out.println("这是个三角形吗？");
        System.out.println(isTriangle(x, y, h));
    }
    public static void main (String[] args) {
    sidePrint();
    }
}
```

#### 第三题代码：

```java
package Chapter6;
/*
   练习3
*/
import java.util.Scanner;
public class Work8 {
    /**
     * 接受 3 个 double 参数，并返回 a * b + c
     * @return 返回 x * y + z
     */
    public static double multadd (double x, double y, double z) {
        return x * y + z;
    }
    // 用重载使用 void 编写一个 multadd 方法计算 (4) 中表达式
    public static void multadd () {
        double x = Math.sin(Math.PI / 2) + Math.cos(Math.PI / 4) / 2;
        double y = Math.log(10) + Math.log(20);
        System.out.println("(4)的第一行表达式的值为：" + x);
        System.out.println("(4)的第二行表达式的值为：" + y);
    }

    public static double exqSum (double x) {
        // 计算 x * e的-x次方
        double a = x * Math.pow(Math.E, -x);
        // 计算 根号(1 - e的-x次方)
        double b = Math.sqrt(1 - Math.pow(Math.E, -x));
        return a + b;
    }

    public static void main (String[] args) {
        double x = 1.0;
        double y = 2.0;
        double z = 3.0;
        System.out.println("(2)的结果为：" + multadd(x, y, z));
        multadd();
        Scanner in = new Scanner(System.in);
        System.out.print("请给(5)输入一个数字：");
        double a = in.nextDouble();
        System.out.println("(5)的结果为：" + exqSum(a));
    }
}
```

# 7 循环

计算机常用于自动完成重复的任务。重复执行任务而不出错是计算机的强项，也是人类的弱项。

**多次运行相同的代码被称为迭代（iteration）**。前面已经见过用递归来迭代的方法，如 countdown(倒数) 和 factorial(阶乘)。虽然递归既优雅又强大，但需要使用一段时间才能习惯。Java 提供的语言功能简化了迭代，这些语言功能指的是 while 语句和 for 语句。

## 7.1 while语句

可用 while 语句改写前面的 countdown 方法：

```java
public static void countdown(int n) {
	while (n > 0) {
		System.out.println(n);
		n = n - 1;
	}
	System.out.println("Blastoff!");
}
```

while 语句平白如话：只要 n 大于0，就打印 n 的值并将它减 1；n 为0后，打印“Blastoff!”。

括号内的表达式称为条件；而大括号内的语句称为循环体（loop body）。while 语句的执行流程如下：

1. 计算条件，结果为 true 或 false。
2. 如果条件为 false，就跳过循环体，接着执行循环体后面的语句。
3. 如果条件为 true，就执行循环体，再回到第 1 步。

这种流程被称为循环（loop），因为执行完最后一步还会再回到第一步。

**循环体应修改一个或多个变量的值，让条件最终为 false，从而结束循环。**否则循环将没完没了地执行，这样的循环被称为无限循环（infinite loop）。计算机科学家总喜欢拿洗发水说明开涮，说其中的“抹洗发水、冲掉、再来”就是无限循环。

就前面的 countdown 方法而言，我们能够证明其中的循环肯定会结束。但一般而言，循环会不会结束并不那么容易判断。例如，下面的循环就会不断执行，直到 n 为 1（导致条件为 false）：

```java
public static void sequence(int n) {
	while (n != 1) {
		System.out.println(n);
		if (n % 2 == 0) { // n为偶数
			n = n / 2;
		} else { // n为奇数
			n = n * 3 + 1;
		}
	}
}
```

每次执行循环时都会显示 n 的值，然后再检查它是奇数还是偶数。如果是偶数，就除以 2；如果是奇数，就将它设置为 3*n*+1。例如，如果起始值（传递给 sequence 的实参）为 3，将生成数列 3、10、5、16、8、4、2。

因为 n 时而增大时而减小，所以没有明显的证据可以证明 n 终将变成1，从而导致这个程序终止。n 为某些值时，我们能够证明这个程序终将终止。例如，如果 n 的起始值为 2 的幂，则每次执行循环时，n 都将为偶数，并最终会变成 1。在前面的数列中，从 n 为 16 开始就是一个这样的数列。

不管 n 的初始值是多少，这个程序最终都将结束吗？这是一个难以回答的问题。到目前为止，既没人能够证明这一点，也没人能够证伪。

完整代码：

```java
package Chapter7;

import java.util.Scanner;
public class Work1 {
    // 倒数
    public static void countNum(int n) {
        while (n > 0) {
            System.out.println(n);
            n = n - 1;
        }
        System.out.println("Blastoff!");
    }
    // 将 n 除以 2 最终为 1
    public static void evenDividedBy2Equals1 (int n) {
        while (n != 1) {
            System.out.println(n);
            if (n % 2 == 0) {
                n = n / 2;
            } else {
                n = n * 3 + 1;
            }
        }
    }

    public static void main (String[] args) {
        Scanner in = new Scanner(System.in);
        System.out.print("请输入一个数字：");
        int n = in.nextInt();
        //countNum(n);
        evenDividedBy2Equals1(n);
    }
}
```

## 7.2 生成表格

循环非常适合用于生成和显示表格型数据。计算机还未面世时，人们必须手工计算对数、正弦、余弦等常见的数学函数。为简化这种工作，有些书提供了表格，让你能够查找各种函数的值，但手工创建这样的表格既缓慢又繁琐，并且结果常常错误百出。

计算机面世后，大家最初的反应之一是：太好了，可用计算机来生成这样的表格了，并确保它们没有任何错误。事实证明确实如此，但人们的目光还是太短浅了，不久后，计算机就非常普及，这些打印出来的表格也就被淘汰了。

但对于有些运算来说，计算机依然要先在值表中查找近似结果，再通过计算来提高结果的精度。然而，有些值表存在错误，其中最著名的是最初的 Intel 奔腾处理器用来计算浮点数除法的值表、。

虽然“对数表”不再像以前那么有用了，但它依然是迭代的典范。下面的循环显示了一个表格，其中左边一列是一系列值，而右边一列是这些值的对数：

```java
int i = 1;
while (i < 10) {
	double x = (double) i;
	System.out.println(x + " " + Math.log(x));
	i = i + 1;
}
```

这个程序的输出如下：

```
1.0	0.0
2.0 0.6931471805599453
3.0 1.0986122886681098
4.0 1.3862943611198906
5.0 1.6094379124341003
6.0 1.791759469228055
7.0 1.9459101490553132
8.0 2.0794415416798357
9.0 2.1972245773362196
```

Math.log 计算自然对数，即以 e 为底的对数。在计算机应用领域常常需要计算以 2 为底的对数，为此可使用下面的公式：

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230320154042262.png" alt="image-20230320154042262" style="zoom:50%;" />

我们可将前面的循环修改成下面这样：

```java
int i = 1;
while (i < 10) {
	double x = (double) i;
	System.out.println(x + " " + Math.log(x) / Math.log(2));
	i = i + 1;
}
```

结果如下：

```
1.0 0.0
2.0 1.0
3.0 1.5849625007211563
4.0 2.0
5.0 2.321928094887362
6.0 2.584962500721156
7.0 2.807354922057604
8.0 3.0
9.0 3.1699250014423126
```

我们在每次循环中都将 x 的值加 1，从而得到一个等差数列。如果不将x 加 1，而是乘以一个常数，将得到一个等比数列：

```java
final double LOG2 = Math.log(2);
int i = 1;
while (i < 100) {
	double x = (double) i;
	System.out.println(x + " " + Math.log(x) / LOG2);
	i = i * 2;
}
```

第 1 行将 Math.log(2) 存储在一个 final 变量中，以免反复计算这个

表达式的值；最后一行将 x 乘以 2。结果如下：

```
1.0 0.0
2.0 1.0
4.0 2.0
8.0 3.0
16.0 4.0
32.0 5.0
64.0 6.0
```

这个表格列出了 2 的幂及其以 2 为底的对数。虽然对数表已毫无用处，但对计算机科学家来说，知道 2 的幂大有裨益。

完整代码：

```java
package Chapter7;

import java.util.Scanner;
public class Work2 {
    // 做一个左边数字x，右边对应数字的自然对数的表格
    public static void tableELogarithm () {
        int i = 1;
        while (i < 10) {
            double x = (double) i;
            System.out.println(x + "    " + Math.log(x));
            i = i + 1;
        }
    }
    // 做一个左边数字x，右边以2为底x的对数的表格
    public static void table2Logarithm() {
        int i = 1;
        while (i < 10) {
            double x = (double) i;
            System.out.println(x + "    " + Math.log(x) / Math.log(2));
            i = i + 1;
        }
    }
    // 用等比数列做一个左边数字x，右边以2为底x的对数的表格
    public static void table2EqualRatioLogarithm () {
        final double Log2 = Math.log(2); // final定义常量
        int i = 1;
        while (i < 100) {
            double x = i;
            System.out.println(x + "    " + Math.log(x) / Log2);
            i = i * 2;
        }
    }

    public static void main (String[] args) {
        //tableELogarithm();
        //table2Logarithm();
        table2EqualRatioLogarithm();
    }
}
```

## 7.3 封装和泛化

6.2 节介绍了一种名为渐进开发的程序编写方法，本节介绍另一种程序开发（program development）流程——封装和泛化，步骤如下。

(1) 在 main 或其他方法中编写几行代码，并进行测试。

(2) 如果能够正确运行，就将它们封装到一个方法中，并再次测试。

(3) 如果这个方法没问题，就将其中的字面量替换为变量和形参。

其中的第二步被称为封装（encapsulation），第 3 步被称为泛化（generalization）。

为演示这种流程，我们将开发几个显示乘法表的方法。下面的循环显示2 的幂，这些幂值都显示在一行中：

```java
int i = 1;
while (i <= 6) {
	System.out.printf("%4d", 2 * i);
	i = i + 1;
}
System.out.println();
```

第 1 行初始化变量 i，这个变量将充当循环变量（loop variable）：每次执行循环时，都将变量 i 的值加 1；循环在 i 为 7 后终止。

每次循环都显示 2 * i 的值，并在它前面添加空格，使结果为 4 字符宽。由于我们使用的是 System.out.printf，因此所有输出都显示在一行中。

循环结束后，我们调用 println 打印一个换行符，从而换到下一行。别忘了，输出在有些环境中要遇到换行符后才显示。因此，上述代码的输出如下：

```
   2   4   6   8  10  12
```

下一步是将这些代码“封装”到一个新方法中。这个方法类似于下面这样：

```java
public static void printRow() {
	int i = 1;
	while (i <= 6) {
		System.out.printf("%4d", 2 * i);
		i = i + 1;
	}
	System.out.println();
}
```

接下来，我们用一个形参 n 替换常量值 2。这一步被称为泛化，因为它让这个方法更通用（不那么具体）。

```java
public static void printRow(int n) {
	int i = 1;
	while (i <= 6) {
		System.out.printf("%4d", n * i);
		i = i + 1;
	}
	System.out.println();
}
```

如果用实参 2 调用这个方法，得到的输出将与前面相同。使用实参 3 调

用这个方法时，输出如下：

```
   3   6   9  12  15  18
```

下面是用实参 4 调用这个方法得到的输出：

```
   4   8  12  16  20  24
```

至此你可能猜到了我们将如何显示乘法表：反复调用方法 printRow，但每次指定不同的实参。实际上，我们将用另一个循环来遍历所有行。

```java
int i = 1;
while (i <= 6) {
	printRow(i);
	i = i + 1;
}
```

输出类似于以下这样：

```
   1   2   3   4   5   6
   2   4   6   8  10  12
   3   6   9  12  15  18
   4   8  12  16  20  24
   5  10  15  20  25  30
   6  12  18  24  30  36
```

printRow 中的格式说明符 %4d 确保了输出都是垂直对齐的，不管结果是个位数还是十位数。

最后，我们将第二个循环封装到一个方法中：

```java
public static void printTable() {
	int i = 1;
	while (i <= 6) {
		printRow(i);
		i = i + 1;
	}
}
```

编程时面临的挑战之一是如何将程序划分成多个方法，对初学者来说尤其如此。封装和泛化流程能够让你一边编程一边设计。

完整代码：

```java
package Chapter7;

public class Work3 {

    public static void multiply2Print () {
        int i = 1;
        while (i <= 6) {
            System.out.printf("%4d", i * 2);
            i = i + 1;
        }
        System.out.println();
    }

    public static void multiplyNPrint (int n) {
        int i = 1;
        while (i <= 6) {
            System.out.printf("%4d", i * n);
            i = i + 1;
        }
        System.out.println();
    }

    public static void printTable () {
        int i = 1;
        while (i <= 6) {
            multiplyNPrint(i);
            i = i+1;
        }
    }

    public static void main (String[] args) {
        //multiply2Print();
        //multiplyNPrint(4);
        printTable();
    }
}
```

## 7.4 泛化

前面的 printTable 版本总是显示 6 行，我们可对其进行泛化，用形参替换字面量 6：

```java
public static void printTable(int rows) {
	int i = 1;
	while (i <= rows) {
		printRow(i);
		i = i + 1;
	}
}
```

下面是用实参 7 调用这个方法得到的输出：

```
   1   2   3   4   5   6
   2   4   6   8  10  12
   3   6   9  12  15  18
   4   8  12  16  20  24
   5  10  15  20  25  30
   6  12  18  24  30  36
   7  14  21  28  35  42
```

这个版本更好，但还存在一个问题：每次显示的列数相同。要想进一步泛化，可给 printRow 再添加一个形参：

```java
public static void printRow(int n, int cols) {
	int i = 1;
	while (i <= cols) {
		System.out.printf("%4d", n * i);
		i = i + 1;
	}
	System.out.println();
}
```

现在 printRow 接受两个形参——n 和 cols，n 指定要计算哪个值的整数倍，而 cols 指定列数。因为我们给 printRow 添加了一个形参，所以还需要修改 printTable 中调用 printRow 的代码行：

```java
public static void printTable(int rows) {
	int i = 1;
	while (i <= rows) {
		printRow(i, rows);
		i = i + 1;
	}
}
```

这行代码执行时会将 rows（这里为 7）作为实参传递给 printRow。在printRow 中，这个值被赋给 cols，这导致列数等于行数，因此得到的是一个 7×7 的方形表格：

```
   1   2   3   4   5   6   7
   2   4   6   8  10  12  14
   3   6   9  12  15  18  21
   4   8  12  16  20  24  28
   5  10  15  20  25  30  35
   6  12  18  24  30  36  42
   7  14  21  28  35  42  49
```

合理地泛化方法常常会得到计划外的功能。例如，你可能注意到了，前面的乘法表是对称的，这是因为 *ab*=*ba*，所以这个表格中的每项都出现了两次。为节省油墨，可只打印这个表格的一半，为此只需要修改printTable 中的一行代码：

```java
printRow(i, i);
```

这使得每行的长度与其行号相同，结果是一个三角形乘法表：

```
   1
   2   4
   3   6   9
   4   8  12  16
   5  10  15  20  25
   6  12  18  24  30  36
   7  14  21  28  35  42  49
```

泛化可让代码更通用、更易于重用甚至更容易编写。九九乘法表在后。

完整代码：

```java
package Chapter7;

public class Work4 {

    public static void multiplyNPrint(int m, int n) {
        int i = 1;
        while (i <= n) {
            System.out.printf("%4d", i * m);
            i = i + 1;
        }
        System.out.println();
    }

    public static void printTable(int n) {
        int i = 1;
        while (i <= n) {
            multiplyNPrint(i, i);
            i = i + 1;
        }
    }

    public static void main (String[] args) {
        printTable(7);
    }
}
```

九九乘法表：

```java
package Chapter7;
// 九九乘法表
public class Work5 {

    public static void printNMultiply (int m, int n) {
        int i = 1;
        while (i <= n) {
            System.out.printf("%d * %d = %2d  ", i, n, i*n);
            i = i + 1;
        }
        System.out.println();
    }

    public static void printTable (int n) {
        int i = 1;
        while (i <= n) {
            printNMultiply(i ,i);
            i = i + 1;
        }
    }

    public static void main (String[] args) {
        printTable(9);
    }
}
```

## 7.5 for语句

前面编写的循环有几个共同之处：都先初始化一个变量，都有一个依赖于这个变量的条件，且都在循环体内修改这个变量。这种循环很常见，为了以更简洁的方式表示，Java 提供了另一条语句——for 循环。

例如，我们可以将 printTable 重写为下面这样：

```java
public static void printTable(int rows) {
	for (int i = 1; i <= rows; i = i + 1) {
		printRow(i, rows);
	}
}
```

**for 循环在括号内包含 3 个由分号分隔的部分：初始化部分、条件部分和更新部分。**

1. 初始化部分只在循环开始时运行一次。
2. 每次循环前都检查条件部分，如果它为 false，循环将终止；否则就再次执行循环。
3. 每次迭代结束时，都运行更新部分再返回到第 2 步。

通常来说，for 循环更容易理解，因为它将所有与循环相关的语句都放在了循环开头。

while 循环和 for 循环的一个不同之处在于：若在初始化部分声明了变量，那么该变量只在 for 循环中可用。例如，下面是一个使用 for 循环的 printRow 版本：

```java
public static void printRow(int n, int cols) {
	for (int i = 1; i <= cols; i = i + 1) {
		System.out.printf("%4d", n * i);
	}
	System.out.println(i); // 编译错误
}
```

最后一行试图显示 i（这样做只是为了演示），但行不通。要想在循环外使用循环变量，就必须在循环外声明它，如下所示：

```java
public static void printRow(int n, int cols) {
	int i;
	for (i = 1; i <= cols; i = i + 1) {
		System.out.printf("%4d", n * i);
	}
	System.out.println(i);
}
```

在 for 循环中，很少用 i = i + 1 这样的赋值语句，因为 Java 提供了表示加 1 和减 1 的更简洁方式。具体地说，**++ 是递增（increment）运算符，与 i = i + 1 等效；而 -- 是递减（decrement）运算符，与 i = i - 1 等效**。

**如果给变量加上或减去的值不是 1，而是其他值，可用运算符 += 或 -=。例如，i += 2 表示将变量 i 加 2。**

代码：

```java
package Chapter7;

public class Work6 {

    public static void printNMultiply (int m, int n) {
        for (int i = 1; i <= m; i = i + 1) {
            System.out.printf("%4d", i * n);
        }
        System.out.println();
    }
    public static void printTable (int n) {
        for (int i = 1; i <= n; i++) { // i++和i=i+1等效
            printNMultiply(i, i);
        }
    }

    public static void main (String[] args) {
        printTable(9);
    }
}
```

## 7.6 do-while循环

while 语句和 for 语句都是先测试循环（pretest loop），即在每次循环前都要测试条件。

Java 还提供了一种后测试循环（posttest loop）——do-while 语句。在至少需要运行循环一次时，这种循环很有用。

例如，在 5.7 节中用了 return 语句来避免读取无效的用户输入。我们也可以用 do-while 循环不断读取输入，直到用户输入有效为止：

```java
Scanner in = new Scanner(System.in);
boolean okay;
do {
	System.out.print("Enter a number: ");
	if (in.hasNextDouble()) {
        // hasNextDouble 用于检查能否将输入流中的下一个标记转换为 double 值。
		okay = true;
	} else {
		okay = false;
		String word = in.next();
		System.err.println(word + " is not a number");
	}
} while (!okay);
double x = in.nextDouble();
```

这些代码看似很复杂，但其实只包含三个步骤。

1. 显示提示。
2. 检查输入。如果无效就显示错误消息并重新开始。
3. 读取输入。

上述代码使用了标志，变量 okay 来指出是否要再次执行循环体。如果hasNextDoublec() 返回 false，那么就调用 next() 来提取无效输入，再通过 System.err 显示一条错误消息， hasNextDouble() 返回true 后终止循环。

完整代码：

```java
package Chapter7;

import java.util.Scanner;
public class Work7 {

    public static void main (String[] args) {
        Scanner in = new Scanner(System.in);
        boolean okay;
        do {
            System.out.print("请输入一个数字：");
            if (in.hasNextDouble()) {
                okay = true;
            } else {
                okay = false;
                String word = in.next();
                System.out.println(word + " 不是一个数字");
            }
        } while (!okay);
        double x = in.nextDouble();
    }
}
```

## 7.7 break和continue

在有些情况下，先测试循环和后测试循环都无法完全满足需求。前一个示例就需要在循环中间进行测试，因此我们结合使用了一个标志变量和一个嵌套的 if-else 语句。

对于这个问题，更简单的解决方案是使用 break 语句。程序执行到break 语句时退出当前循环。

```java
Scanner in = new Scanner(System.in);
while (true) {
	System.out.print("Enter a number: ");
	if (in.hasNextDouble()) {
		break;
	}
	String word = in.next();
	System.err.println(word + " is not a number");
}
double x = in.nextDouble();
```

在 while 循环中将 true 用作循环条件是一种惯用法，通常意味着不断循环，但在这个示例中意味着不断循环，直到遇到 break 语句。

除退出循环的 break 语句外，Java 还提供了直接进入下一次迭代的continue 语句。例如，下面的代码不断从键盘读取整数，并计算这些整数的总和；其中的 continue 语句让程序忽略所有的负数。

```java
Scanner in = new Scanner(System.in);
int x = -1;
int sum = 0;
while (x != 0) {
	x = in.nextInt();
	if (x <= 0) {
		continue;
	}
	System.out.println("Adding " + x);
	sum += x; // 变量sum = sum + x
}
```

虽然 break 语句和 continue 语句让你能够更好地控制循环的执行流程，但也可能导致代码难以理解和调试，因此务必慎用。

break代码：

```java
package Chapter7;
// break 和 continue 测试循环
import java.util.Scanner;
public class Work8 {

    public static void main (String[] args) {
        Scanner in = new Scanner(System.in);
        while (true) {
            System.out.print("请输入一个数字：");
            if (in.hasNextDouble()) {
                break;
            }
            String x = in.next();
            System.out.println(x + " 不是一个数字");
        }
        double x = in.nextDouble();
    }
}
```

continue代码：

```java
package Chapter7;

import java.util.Scanner;
public class Work9 {
    public static void main (String[] args) {
        Scanner in = new Scanner(System.in);
        int x = -1;
        int sum = 0;
        while (x != 0) {
            x = in.nextInt();
            if (x <= 0) {
                continue;
            }
            System.out.println("加 " + x);
            sum += x;
        }
        System.out.println("和为 " + sum);
    }
}
```

## 7.8 术语表

| 术语       | 含义                                                         |
| :--------- | :----------------------------------------------------------- |
| 迭代       | 反复地执行一系列语句。                                       |
| 循环       | 反复地执行一系列语句的语句。                                 |
| 循环体     | 循环中的语句。                                               |
| 无限循环   | 条件始终为 true 的循环。                                     |
| 程序开发   | 程序编写流程，至此，我们介绍了两种程序开发流程——渐进开发以及封装和泛化。 |
| 封装       | 将一系列语句放在方法中。                                     |
| 泛化       | 将具体的信息（如常量值）替换为通用信息（如变量或形参）。     |
| 循环变量   | 为控制循环而被初始化、测试和修改的变量。                     |
| 递增       | 增大变量的值。                                               |
| 递减       | 减小变量的值。                                               |
| 先测试循环 | 在每次迭代前检查条件的循环。                                 |
| 后测试循环 | 在每次迭代后检查条件的循环。                                 |

## 7.9 练习

#### 第一题

请看下面的方法，并思考问题：

```java
public static void main(String[] args) {
	loop(10);
}
public static void loop(int n) {
	int i = n;
	while (i > 1) {
		System.out.println(i);
		if (i % 2 == 0) {
			i = i / 2;
		} else {
			i = i + 1;
		}
	}
}
```

绘制一个表格，用来显示变量 i 和 n 在循环期间的值。在这个表格中，每次迭代要占据一行，每列对应一个变量。

#### 第二题

给定数字 *a*，要求你计算它的平方根。一种解决方案是先粗略地猜测结果 *x*0，再用下面的公式提高结果的精度：
<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230322084719363.png" alt="image-20230322084719363" style="zoom:50%;" />

例如，要计算 9 的平方根，可从 *x*0=6 开始，再用前面的公式计算*x*1=（6+9/6）/2 = 3.75，这更接近于准确的结果。我们可重复这个过程，根据 *x*1 计算 *x*2，再依次类推。就此例而言，*x*2=3.075，*x*3=3.00091。这种计算的速度非常快，很快就能找到正确的答案。

请编写一个名为 squareRoot 的方法，让它接受一个 double 值，并用前面的技巧计算其平方根的近似值。不能用 Math.sqrt 。

为计算初始结果，可使用公式 *a*/2。这个方法应该不断迭代，直到两个相邻近似结果的差小于 0.0001。可用 Math.abs 计算差的绝对值。

#### 第三体

在练习 6-9 中，你编写了一个以迭代方式计算幂的方法，它接受double 值 x 和整数值 n，并返回 *x* *n*。现在请编写一个迭代方法来执行这种计算。

#### 第四题

6.7 节中介绍了一个计算阶乘的递归方法，请编写方法 factorial 的迭代版本。

#### 第五题

要想计算 e *x* 的值，一种办法是使用如下的无穷级数展开：<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230323081740645.png" alt="image-20230323081740645" style="zoom:50%;" />
在上述级数中，第 *i* 项为“*x* *i* /*i* !”。
(1) 编写一个名为 myexp 的方法，它接受形参 x 和 n，并将上述级数的前 n 项相加来计算 e *x* 的近似值。为计算阶乘，可使用 6.7 节中的方法factorial，也可使用前一个练习中编写的迭代版本。
(2) 在上述级数中，每一项的分子都是前一项的分子乘以 x，而每一项的分母都是前一项的分母乘以 i。利用这一点可避免使用方法Math.pow 和 factorial，从而提高这个方法的效率。请按这种方式修改你在第 1 步编写的方法，并确定得到的结果相同。
(3) 编写一个名为 check 的方法，它接受形参 x，并显示 x、myexp(x) 和 Math.exp(x) 的值，其输出类似于下面这样：
1.0 2.708333333333333 2.718281828459045
要想用制表符分隔各列的值，可使用转义序列 "\t"。
(4) 修改级数包含的项数（check 向 myexp 传递的第二个实参），并查看这种修改对结果准确度的影响。在 x 为 1 的情况下调整值，直到估算值与正确的结果相同为止。
(5) 在方法 main 中编写一个循环，依次用实参值 0.1、1.0、10.0 和100.0 调用 check。随着 x 值不断变化，结果的准确度将如何变化？比较估算值和实际值有多少位相同。
(6) 在方法 main 中编写一个循环，依次用实参值 - 0.1、- 1.0、- 10.0 和 -100.0 调用 check，看看准确度将如何变化。

1. 要想计算 exp(-*x* 2 ) 的值，一种办法是用如下的无穷级数展开：<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230323081801681.png" alt="image-20230323081801681" style="zoom:50%;" />
   在上述级数中，第 *i* 项为“(-1) *i**x* 2*i* /*i* !”。请编写一个名为 gauss 的方法，它接受形参 x 和 n，并返回上述级数中前 n 项的和。编写这个方法时，不能使用方法 factorial 和 pow 。

#### 第一题代码

```java
package Chapter7;
// 练习1
public class Work10 {
    // 计算每个数是否被 2 整除，是则除以 2 输出，不是则加 1 后循环迭代
    public static void loop (int n) {
        int i = n;
        while (i > 1) {
            System.out.printf("%4d ", i);
            if (i % 2 == 0) {
                i = i / 2;
            } else {
                i = i + 1;
            }
        }
        System.out.println(); // 每次迭代后进入下一行
    }

    public static void printTable (int n) {
        for (int i = n; i > 0; i--) {
            loop(i);
        }

    }

    public static void main (String[] args) {
        //loop(10);
        printTable(10);
    }
}
```

#### 第二题代码

```java
package Chapter7;
// 练习2
public class Work11 {

    public static void formulaCalculate (int a, double x) {
        double y = a / x;
        double x1 = (x + y) / 2;
        if (Math.abs(x1 - Math.sqrt(a)) <  0.0001) {
            // 猜测数字和正确答案之间的差的绝对值小于 0.0001
            System.out.println(x1);
        } else {
            //System.out.println(x1); //验证输出
            formulaCalculate(a, x1); // 循环这段语句直到求出答案
        }
    }

    public static void main (String[] args) {
        int a = 9;
        formulaCalculate(a, 6.0); // a 为要求平方根的数字，x 为猜测数字
        //System.out.println(Math.sqrt(a)); //验证输出
    }
}
```

#### 第三题代码

```java
package Chapter7;
// 练习3
public class Work12 {
    // 使用迭代计算 x 的 n 次幂
    public static void calculatedNPower (double x, int n) {
        double i;
        double result = 0;
        for (i = x; n > 0; n--) {
            result = i * i;
        }
        System.out.println(result);
    }

    public static void main(String[] args) {
        calculatedNPower(2, 2);
    }
}
```

#### 第四题代码

```java
package Chapter7;
// 练习4
import java.math.BigInteger;
public class Work13 {
    // 使用迭代计算 n 的阶乘
    public static void factorial (int n) {
        int i = n; // 循环参数，具体为循环 n 次，应用到 while 语句
        int x = n; // 阶乘参数，应用到 if 语句
        long result = 1; // 保存的结果，初始应为 1, 0和 1的阶乘都为 1
            while (i > 0) { // 循环，当 i 不满足条件时结束循环
                if (x > 0) { // 确保 x 大于 1，当 x 不满足条件时结束计算
                    //System.out.printf("%d * %d = ", result, x); // 验证输出
                    result = result * x; // 计算阶乘结果
                    //System.out.println(result); // 验证输出
                    x--; // 阶乘参数每次运行完都要减 1
                }
                //System.out.println(i);
                i--; // 循环参数每次循环执行后都要减 1
            }
        System.out.printf("%d 的阶乘为 %d", n, result);
    }

    public static void main (String[] args) {
        factorial(5);
    }
}
```

#### 第五题代码

```java
package Chapter7;
// 练习5
public class Work14 {
    // 阶乘
    public static int factorial (int n) {
        if (n == 0) { // 用于返回1的阶乘的结果
            return 1;
        }
        //保存前一项阶乘的结果 ，factorial(n - 1)会不断递归到 factorial(0)，用它来计算1的阶乘
        int recurse = factorial(n - 1); // n - 1 的阶乘
        return n * recurse; // 这里是返回阶乘结果 n * ( n - 1 ) * …… 1
    }
    // (1) 计算近似值
    public static double myexp (double x, int n) {
        double oneResult; // 定义每一项的值
        double result = 0; // 定义最终结果，为每项相加的值
        int m = n - 1; // 因为 n的第一项为 0，比输入的小 1，所以要用 n减掉 1，使 n从 1开始算起
        while (m >= 0) {
            double molecule = Math.pow(x, m); // 定义分子: x的 n次方
            int denominator = factorial(m); // 定义分母: 阶乘
            oneResult = molecule / denominator; // 每项的值
            result = result + oneResult; // 最终结果
            //System.out.println(result); // 测试输出
            m--;
        }
        //System.out.println(result);
        return result;
    }
    // (2) 不用 Math.pow和 factorial方法计算近似值
    public static void myexpX (double x, int n) {
        double molecule = 1; // 定义分子，初始为 1
        double denominator = 1; // 定义分母，初始为 1
        double oneResult; // 定义每一项的值
        double result = 0; // 定义最终结果，为每项相加的值
        result = result + 1; // 当 n为 1时，第一项为 1，for循环不会实现
        for (int a = 1; a < n; a++) {
            /* 第 n项分子的值.因为输入的 n比项数要大 1，所以定义中减掉，
               然后 a > 0则是当分母为 0时结束循环输出 1 */
            molecule = molecule * x; // 计算分子
            denominator = denominator * a; // 计算分母
            oneResult = molecule / denominator;
            result = result + oneResult;
        }
        //System.out.println(molecule); // 测试输入项分子输出
        //System.out.println(denominator); // 测试输出项分母输出
        System.out.printf("%f  ", result); // 16位数，15位小数
    }
    // (3) 接受形参 x，并显示 x、myexp(x)和 Math.exp(x)的值
    public static void check (double x, int n) {
        System.out.print(x + "  ");
        myexpX(x, n);
        System.out.println(Math.exp(x));
    }
    // (4) 对比输出直到估算值相等，输出 x, n, myexp(x,n), Math.exp(x)
    public static void checkX (double x, int n) {
        double a = myexp(x, n); // 定义 a为估算值
        double b = Math.exp(x); // 定义 b为计算值
        double c = 0.00001; // 定义 c为估算值与计算值之间最小差，此处取小数点后五位
        System.out.println(" x    n   myexp(x,n)   Math.exp(x)");
        while (Math.abs(a - b) >= c) { // 绝对值小于 0.00001时结束循环
            a = myexp(x, n);
            n++;
            System.out.printf("%2.1f  %2d    %6.5f      %6.5f\n", x, n, a, b);
            // %2.1f意思是取两位数，1位小数
        }
    }

    public static void main (String[] args) {
        // System.out.println(myexp(3, 10)); // (1)
        // myexpX(3, 10); // (2)
        //check(3, 10); // (3)
        //checkX(1, 1); // (4)

        /*
        // (5) 当 x = 0.1, 1.0, 10.0, 100.0
        double i = 0.1;
        while (i <= 100.0) {
            check(i, 100);
            System.out.println();
            i = i * 10;
        }
        */

        /*
        // (6) 当 x = -0.1, -1.0, -10.0, -100.0
        double j = -0.1;
        while (j <= 100.0) {
            check(j, 100);
            System.out.println();
            j = j * 10;
        }
        */
    }
}
```

# 8 数组

到目前为止，我们使用的变量只能存储单个值，如数字或字符串。在本章中学习如何用单个变量存储多个同类型的值。这种语言功能让你能够编写程序以便操作大量的数据。

## 8.1 创建数组

数组（array）包含一系列的值，这些值被称为元素（element）。你可以创建 int 数组、double 数组或其他任何类型的数组，但在同一个数组中，所有值的类型必须相同。

要想创建数组，必须先声明数组类型的变量，再创建数组本身。数组类型与其他 Java 类型看起来很像，但后面跟着方括号（[ ]）。例如，下面的代码行将 counts 和 values 分别声明为 int 数组和 double 数组：

```java
int[] counts;
double[] values;
```

**要创建数组本身，必须使用 3.2 节中首次见到的运算符 new：**

```java
counts = new int[4];
int size = 4;
values = new double[size];
```

第 1 条赋值语句让 count 指向一个包含 4 个整数的数组；第 2 条语句让 values 指向一个 double 数组，而 values 中包含的元素数取决于size 的值。

当然，也可在同一个代码行内声明变量并创建数组：

```java
int[] counts = new int[4];
int size = 4;
double[] values = new double[size];
```

可用任何整数表达式指定数组的长度，只要值不为负即可。例如，如果你试图创建一个包含- 4 个元素的数组，将引发 `NegativeArraySizeException` 异常。数组可不包含任何元素，这种数组有其特殊用途，我们将在后面介绍。

## 8.2 访问数组

创建 int 数组时，其元素默认初始化为 0，下图是前面创建的数组counts 的状态图。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230323103231474.png" alt="image-20230323103231474" style="zoom:50%;" />	

箭头表明 counts 的值是一个指向数组的引用（reference）。你应将数组和指向它的变量视为两码事，稍后你将看到，既可以给另一个变量赋值，使其与 counts 指向同一个数组，也可以修改 counts 的值，使其指向另一个数组。

方框内的数字表示的是数组的元素，方框外的数字是索引（index），用于标识数组中的各个位置。注意，第一个元素的索引为 0，而不是你预期的 1。

运算符 [ ] 用于选择数组中的元素：

```java
System.out.println("The zeroth element is " + counts[0]);
```

可在表达式的任何地方使用运算符 []：

```java
counts[0] = 7;
counts[1] = counts[0] * 2;
counts[2]++;
counts[3] -= 60;
```

下图显示了执行这些语句的结果（执行多条赋值语句后的状态图）：

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230323112915640.png" alt="image-20230323112915640" style="zoom:50%;" />	

可将任何表达式用作索引，只要其类型为 int。最常见的做法之一是将循环变量用作数组的索引，如下所示：

```java
int i = 0;
while (i < 4) {
	System.out.println(counts[i]);
	i++;
}
```

while 循环从 0 数到 4；i 为 4 时不满足条件，循环结束。因此，仅在i 为 0、1、2 和 3 时，循环体才被执行。

**我们在每次的循环中都将 i 用作数组的索引，以显示第 i 个元素。**这种数组处理方式通常是用 for 循环来实现的：

```java
for (int i = 0; i < 4; i++) {
	System.out.println(counts[i]);
}
```

对数组 counts 来说，只有索引 0、1、2 和 3 是合法的。如果索引为负或大于 3，将引发 ArrayIndexOutOfBoundsException 异常。

示例代码：

```java
package Chapter8;

public class Work1 {

    public static void main (String[] args) {
        int[] counts = new int[4];
        counts[0] = 7;
        counts[1] = counts[0] * 2;
        counts[2]++;
        counts[3] -= 60;
        int size = 4;
        double[] values = new double[size];
        System.out.println(counts[2]);
        int i = 0;
        while (i < 4) {
            System.out.print(counts[i] + "  ");
            i++;
        }
        System.out.println();
        for (int j = 0; j < 4; j++) {
            System.out.print(counts[j] + "  ");
        }
    }
}
```

## 8.3 显示数组

可用 println 显示数组，但结果很可能不是你所希望的。例如，下面的代码片段声明了一个数组变量，让它指向一个包含 4 个元素的数组，并试图用 println 显示这个数组的内容：

```java
int[] a = {1, 2, 3, 4};
System.out.println(a);
```

遗憾的是，输出类似于以下这样：

```
[I@bf3f7e0
```

方括号表明值是一个数组，I 表示整数，余下的内容是这个数组的地址。要想显示数组的元素，需要分别显示它们：

```java
public static void printArray(int[] a) {
	System.out.print("{" + a[0]);
	for (int i = 1; i < a.length; i++) {
		System.out.print(", " + a[i]);
	}
	System.out.println("}");
}
```

给定前面的数组，该方法的输出如下：

```
{1, 2, 3, 4}
```

Java 库包含实用工具类 **java.util.Arrays**，这个类提供了处理数组的方法。其中一个方法是 **toString**，用于返回数组的字符串表示。你可以像下面这样调用：

```java
System.out.println(Arrays.toString(a));
```

输出如下：

```
[1, 2, 3, 4]
```

与往常一样，必须先导入才能使用 `java.util.Arrays`。注意，字符串格式与前面的输出格式稍有不同，它使用方括号而不是大括号。但以这种格式输出时无需编写方法 printArray。

示例代码：

```java
package Chapter8;

import java.util.Arrays;
public class Work2 {

    public static void main (String[] args) {
        int[] a = { 1, 2, 3, 4 };
        System.out.print("{" + a[0]);
        for (int i = 1; i < a.length; i++) {
            System.out.print(" ," + a[i]);
        }
        System.out.println("}");
        System.out.println(Arrays.toString(a));
    }
}
```

## 8.4 复制数组

8.2 节中说过，数组变量包含指向数组的引用。**给数组变量赋值时，只复制指向数组的引用，而不会复制数组本身**！请看下面的示例：

```java
double[] a = new double[3];
double[] b = a;
```

这些语句创建了一个包含 3 个元素的 double 数组，并让两个变量指向它，如下图所示。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230323162116193.png" alt="image-20230323162116193" style="zoom:50%;" />	*显示两个变量指向同一个数组的状态图*

通过其中任何一个变量修改数组都将影响另一个变量。例如，如果我们设置 a[0] = 17.0，再显示 b[0]，结果将为 17.0。因为 a 和 b 是表示同一样东西的不同名称，所以它们有时被称为别名（alias）。

如果要复制数组本身而不是指向它的引用，那么就必须创建一个新的数组，并将旧数组中的每个元素都复制到新数组中，如下所示：

```java
double[] b = new double[3];
for (int i = 0; i < 3; i++) {
	b[i] = a[i];
}
```

另一种选择是**使用 java.util.Arrays，它提供了复制数组的方法copyOf**，可像下面这样调用这个方法：

```java
double[] b = Arrays.copyOf(a, 3);
```

其中的**第二个参数用来指定要复制的元素个数**，因此你也可以只复制数组的一部分。

示例代码：

```java
package Chapter8;

import java.util.Arrays;
public class Work3 {

    public static void main (String[] args) {
        int[] a = new int[3];
        int[] b = a; // 定义不会复制，只会使数组多一个变量名
        a[2] = 4;
        // 用 for循环复制数组
        int[] c = new int[3];
        for (int i = 0; i < 3; i++) {
            c[i] = a[i];
        }
        // 用 Arrays方法复制数组
        int[] d = Arrays.copyOf(a, 3);
        a[1] = 3;
        System.out.println(Arrays.toString(b));
        System.out.println(Arrays.toString(c));
        System.out.println(Arrays.toString(d));
    }
}
```

## 8.5 数组的长度

前面的示例仅在数组包含 3 个元素时才管用，因此，最好对这些代码进行泛化，使其适用于任何长度的数组。为此，可将魔幻数字 3 替换为`a.length`：

```java
double[] b = new double[a.length];
for (int i = 0; i < a.length; i++) {
b[i] = a[i];
}
```

所有数组都有一个内置常量 length，其中存储了数组包含的元素数。表达式 a.length 看起来像方法调用，但没有括号，也没有实参。这个循环最后一次执行时，i 的值为 a.length-1，这是最后一个元素的索引。i 的值为 a.length 时不满足条件，因此不会执行循环体，这是件好事，因为试图访问 a[a.length] 将引发异常。还可将 a.length 用作 Arrays.copyOf 的第二个实参：

```java
import java.util.Arrays;
public calss Arrays {
	public static viod main (String[] args) {
		double[] a = new double[a.length]
		double[] b = Arrays.copyOf(a, a.length);
	}
}
```

## 8.6 数组遍历

很多计算可通过循环访问数组的每个元素并对其执行特定的操作来实现。例如，下面的循环计算了一个 double 数组的各个元素的平方：

```java
for (int i = 0; i < a.length; i++) {
	a[i] = Math.pow(a[i], 2.0);
}
```

循环访问数组的每个元素被称为遍历（traversal）。另一种常见的模式是查找（search），这需要遍历数组，在其中查找特定的元素。

例如，下面的方法接受一个 int 数组和一个 int 值，并返回 int 值在数组中所处位置的索引：

```java
public static int search(double[] a, double target) {
	for (int i = 0; i < a.length; i++) {
		if (a[i] == target) {
			return i;
		}
	}
	return -1;
}
```

如果在数组中找到目标值，那么就立即返回其索引；如果循环结束时也没有找到目标值，那么就返回 -1——用于表示查找失败的特殊值。

另一种常见的遍历是归并（reduce）操作，用于将数组归并为单个值。

归并操作包括计算各个元素的和或积、找出最大值或最小值。下面的方法接受一个 double 数组，并返回其中所有元素的和：

```java
public static int sum(double[] a) {
	double total = 0.0;
	for (int i = 0; i < a.length; i++) {
		total += a[i];
	}
	return total;
}
```

循环前将 total 初始化为零。在每次循环时都将 total 加上一个数组元素的值；循环结束后，total 为数组中所有元素的和。以这种方式使用的变量有时被称为累加器（accumulator）。

示例代码：

```java
package Chapter8;

import java.util.Arrays;
public class Work4 {

    // 查找元素位置
    public static int search (int[] a, double target) {
        for (int i = 0; i < a.length; i++) {
            if (a[i] == target) {
                return i;
            }
        }
        return -1;
    }

    // 计算数组中所有元素的和
    public static double sum (double[] b) {
        double sum = 0;
        for (int i = 0; i < b.length; i++) {
            sum = sum + b[i];
        }
        return sum;
    }

    public static void main (String[] args) {
        int[] a = {1,2,3,4};
        double[] b = new double[4];
        // 复制数组 a到数组 b中并将所有元素乘二次方
        for (int i = 0; i < a.length; i++) {
            b[i] = Math.pow(a[i], 2);
        }
        System.out.println(Arrays.toString(b));
        // 查找 i在数组 a的位置
        int i = search(a, 4);
        System.out.println(i);
        // 计算数组 b的所有元素的和
        System.out.println(sum(b));
    }
}
```

## 8.7 随机数

大多数计算机程序每次运行时所做的事情相同，这样的程序是确定的（deterministic）。确定性是件好事，因为我们希望同样的计算得到同样的结果。但对有些应用程序来说，我们希望它们的行为是不可预测的，游戏就是一个显而易见的例子，当然还有很多其他的例子。

实际上，很难让程序的行为是不确定的（nondeterministic），因为要让计算机生成真正的随机数很难。但存在一些算法，可用于生成被称为伪随机数（pseudorandom number）的不可预测序列。对大多数应用程序来说，伪随机数的随机程度已经足够高了。

如果你完成了练习 3-4，就会知道 java.util.Random 生成的就是伪随机数。这个类的方法 nextInt 接受 int 实参 n，并返回一个位于 0~n-1（闭区间）的随机数。如果你生成大量的随机数，每个值出现的次数将大致相同。要验证nextInt 的这种行为，可以用它生成大量的随机数，然后将这些随机数存储在一个数组中，并计算每个值出现的次数。

下面的方法创建了一个 int 数组，并用 0~99 的随机数来填充它。数组的长度由传递的实参指定，且返回值是一个引用，指向新创建的数组。

```java
public static int[] randomArray(int size) {
	Random random = new Random();
	int[] a = new int[size];
	for (int i = 0; i < a.length; i++) {
		a[i] = random.nextInt(100);
	}
	return a;
}
```

下面的代码片段创建了一个数组，并用 8.3 节的方法 printArray 显示

这个数组：

```java
int numValues = 8;
int[] array = randomArray(numValues);
printArray(array);
```

输出类似于以下这样：

```
{15, 62, 46, 74, 67, 52, 51, 10}
```

运行这些代码生成的随机数可能与这里显示的不同。

示例代码：

```java
package Chapter8;

import java.util.Arrays;
import java.util.Random;
public class Work5 {
    // 生成具有随机数的数组
    public static int[] randomArray (int size) {
        Random random = new Random();
        int[] a = new int[size];
        for (int i = 0; i < a.length; i++) {
            a[i] = random.nextInt(100);
        }
        return a;
    }
    // 用 {}展示数组
    public static void printArray (int[] a) {
        System.out.print("{" + a[0]);
        for (int i = 1; i < a.length; i++) {
            System.out.print(", " + a[i]);
        }
        System.out.println("}");
    }

    public static void main (String[] args) {
        // 用 []展示数组
        System.out.println(Arrays.toString(randomArray(8)));

        int[] array = randomArray(8);
        printArray(array);
    }
}
```

## 8.8 遍历和计数

如果前面的值表示的是考试成绩，并且这些成绩非常糟糕，老师可能会在课程上以直方图（histogram）的方式呈现它们。直方图在统计学中是一组计数器，记录了每个值出现的次数。

就考试成绩而言，我们可能需要 10 个计数器，用来指出考试成绩为90~100 分、80~90 分等的学生分别有多少。为此，我们可以遍历数组，并计算值在给定范围内的元素数。

下面的方法接受一个数组和两个整数（low 和 high），并返回值在范围 low~high 的元素数。

```java
public static int inRange(int[] a, int low, int high) {
	int count = 0;
	for (int i = 0; i < a.length; i++) {
		if (a[i] >= low && a[i] < high) {
			count++;
		}
	}
	return count;
}
```

你应该很熟悉这种模式：这也是一种归并操作。注意，范围包含low（>=），但不包含 high（<）。这种细节可避免我们将一个分数算两次。

现在可以计算每个范围内的考试成绩数了：

```java
int[] scores = randomArray(30);
int a = inRange(scores, 90, 100);
int b = inRange(scores, 80, 90);
int c = inRange(scores, 70, 80);
int d = inRange(scores, 60, 70);
int f = inRange(scores, 0, 60);
```

示例代码：

```java
package Chapter8;

import java.util.Arrays;
import java.util.Random;
public class Work6 {

    // 生成具有随机数的数组
    public static int[] randomArray (int size) {
        Random random = new Random();
        int[] a = new int[size];
        for (int i = 0; i < a.length; i++) {
            a[i] = random.nextInt(100);
        }
        return a;
    }
    // 返回数组内指定范围内的数
    public static int inRange (int[] a, int low, int high) {
        int count = 0;
        for (int i = 0; i < a.length; i++) {
            if (a[i] >= low && a[i] <= high) {
                count++;
            }
        }
        return count;
    }

    public static void main (String[] args) {
        int[] scores = randomArray(30); // 随机生成 30人的成绩
        // 保存数据，输出每个成绩阶段的人数
        int a = inRange(scores, 90, 100);
        int b = inRange(scores, 80, 90);
        int c = inRange(scores, 70, 80);
        int d = inRange(scores, 60, 70);
        int e = inRange(scores, 0, 60);
        System.out.printf("成绩在 90 ~100 的人数是：%d\n成绩在 80 ~ 90 的人数是：%d\n成绩在 70 ~ 80 的人数是：%d\n成绩在 60 ~ 70 的人数是：%d\n成绩在  0 ~ 60 的人数是：%d\n", a, b, c, d, e);
    }
}
```

## 8.9 生成直方图

前面的代码有些重复，但只要范围数不多，这是完全可以接受的。然而，如果我们要计算每个分数出现的次数，就必须编写 100 行代码：

```java
int count0 = inRange(scores, 0, 1);
int count1 = inRange(scores, 1, 2);
int count2 = inRange(scores, 2, 3);
...
int count99 = inRange(scores, 99, 100);
```

我们需要存储 100 个计数器，最好还能用索引来访问计数器。换言之，我们需要一个数组！

下面的代码片段创建了一个包含 100 个计数器的数组，每种可能的分数一个。它遍历分数，并用 inRange 计算每种分数出现的次数，并将结果存储在数组中：

```java
int[] counts = new int[100];
for (int i = 0; i < counts.length; i++) {
	counts[i] = inRange(scores, i, i + 1);
}
```

注意，我们在三个地方使用了循环变量 i：一处用作索引访问数组counts，两处用于设置 inRange 的两个实参。这些代码可行，但在效率方面还有改进空间。这个循环每次调用 inRange 时都遍历整个数组。

**更好的做法是只遍历数组一次；计算每个成绩所在的范围，并将相应的计数器加 1。**下面的代码在只遍历数组一次的情况下生成直方图：

```java
int[] counts = new int[100];
for (int i = 0; i < scores.length; i++) {
	int index = scores[i];
	counts[index]++;
}
```

这个循环每次执行时，都选择数组 scores 中的一个元素，并将其用作索引来将数组 counts 中相应的元素加 1。因为这些代码只遍历数组scores 一次，所以其效率高得多。

示例代码：

```java
package Chapter8;
// 计算每个分数出现的次数
import java.util.Arrays;
import java.util.Random;
public class Work7 {

    // 生成具有随机数的数组
    public static int[] randomArray (int size) {
        Random random = new Random();
        int[] a = new int[size]; // 生成和 size一样长的数组 a
        for (int i = 0; i < a.length; i++) {
            a[i] = random.nextInt(100);
        }
        return a;
    }
    // 返回数组内指定范围内的数
    public static int inRange (int[] a, int low, int high) {
        int count = 0;
        for (int i = 0; i < a.length; i++) {
            if (a[i] >= low && a[i] <= high) {
                count++;
            }
        }
        return count;
    }
    // 把每个分数出现的次数保存到数组中输出
    public static void counts (int[] scores) {
        int[] counts = new int[100];
        for (int i = 0; i < counts.length; i++) {
            counts[i] = inRange(scores, i, i+1);
        }
        System.out.println(Arrays.toString(counts));
    }
    // 上个方法的升级版，只遍历一次数组，无需调用 inRange方法
    public static void countsX (int[] scores) {
        int[] counts = new int[100];
        for (int i = 0; i < scores.length; i++) {
            int index = scores[i];
            counts[index]++;
        }
        System.out.println(Arrays.toString(counts));
    }

    public static void main (String[] args) {
        int[] scores = randomArray(100);
        counts(scores);
        countsX(scores);
    }
}
```

## 8.10 改进的for循环

考虑到遍历数组的操作极其常见，Java 提供了一种让代码更紧凑的语法。例如，请看下面的 for 循环，它将数组的每个元素都单独显示在一行中：

```java
for (int i = 0; i < values.length; i++) {
	System.out.println(values[i]);
}
```

对于这个循环，我们可将其重写成下面这样：

```java
for (int value : values) {
	System.out.println(value);
}
```

**这条语句被称为改进的 for 循环（enhanced for loop），你可将其解读为“对于 values 中的每个值 value”。根据约定，数组变量应使用复数名词，元素变量应使用单数名词**。

通过使用改进的 for 循环并删除临时变量，我们可用更简洁的方式编写前一节生成直方图的代码：

```java
int[] counts = new int[100];
for (int score : scores) {
	counts[score]++;
}
```

改进的 for 循环通常可提高代码的可读性，对计算累积值的代码来说尤其如此。但如果需要引用索引（如执行查找操作时），这种 for 循环就并没有太大的用处了。

示例代码：

```java
package Chapter8;

import java.util.Arrays;
public class Work8 {

    public static void main (String[] args) {
        int[] values = {2,5,1,7,6,5};
        /*
        // 普通版 for循环输出数组每个元素
        for (int i = 0; i < values.length; i++) {
            System.out.println(values[i]);
        }
        */
        /*
        // 升级版 for循环输出数组每个元素
        for (int value : values) {
            System.out.println(value);
        }
        */
        // 使用升级版 for输出直方图
        int[] counts = new int[8];
        for (int value : values) {
            counts[value]++;
        }
        System.out.println(Arrays.toString(counts));
    }
}
```

## 8.11 方法

### 运算符 **new**     

创建数组。(8.1)

```java
int[] a = new int[10];
double[] b = new double[10];
```

### 运算符 **[ ]**      

访问数组，选择数组中的元素。(8.2)

```java
int[] a = {0,1,2,3,4,5}
System.out.println("数组中第一个数是：" + a[0]);
```

### Arrays.toString()    

用于输出数组的字符串表示。(8.3)

```java
int[] a = {0,1,2,3,4,5}
System.out.println(Arrays.toString(a));
```

### Arrays.copyOf(array, length)  

复制数组。第二个参数用来指定要复制的元素个数。(8.4)

```java
double[] b = Arrays.copyOf(a, 3);
```

### a.length     

数组的长度。也可以作为`Arrays.copyOf`的第二个参数。(8.5)

```java
double[] a = new double[a.length]
	double[] b = Arrays.copyOf(a, a.length);
```

## 8.12 术语表

| 术语          | 含义                                                         |
| ------------- | ------------------------------------------------------------ |
| 数组(array)   | 一系列的值，所有值的类型都相同，每个值都由一个索引标识。     |
| 元素(element) | 数组中的一个值；可用运算符 [] 选择元素。                     |
| 索引          | 标识数组元素的 int 变量或 int 值。                           |
| 引用          | 标识另一个值（如数组）的值；在状态图中用箭头表示。           |
| 别名          | 与另一个变量指向同一个对象的变量。                           |
| 遍历          | 通过循环访问数组（或其他集合）中的每个元素。                 |
| 查找          | 一种在数组中查找特定元素的遍历模式。                         |
| 归并          | 一种将数组的所有元素合并为单个值的遍历模式。                 |
| 累加器        | 在遍历期存储累积结果的变量。                                 |
| 确定的        | 每次运行时结果都相同的程序。                                 |
| 不确定的      | 每次运行时结果都不同的程序，即便每次运行时输入相同亦如此。   |
| 伪随机数      | 一系列看似随机，但实际是用确定性计算得到的数字。             |
| 直方图        | 一个 int 数组，其中的每个元素指出了有多少个值位于特定范围内。 |
| 改进的for循环 | 另一种遍历数组元素（值）的语法。                             |

## 8.13 练习

#### 第一题

以 8.6 节中的代码为基础，编写一个名为 powArray 的方法，让它接受一个 double 数组 a，并返回一个新数组，其中包含数组 a 中的所有元素的平方。泛化这个方法使其接受另一个参数，该参数要指定计算元素的几次方。

#### 第二题

以 8.10 节的代码为基础，编写一个名为 histogram 的方法，让它接受一个 int 数组，其中存储了 0~100（不包括 100）的成绩，并返回一个包含 100 个计数器的直方图。泛化这个方法使其接受另一个指定计数器数量的参数。

#### 第三题

编写一个名为 indexOfMax 的方法，让它接受一个 int 数组，并返回其中最大元素的索引。你能用改进的 for 循环来编写这个方法吗？为什么？（不能，因为i用到了）

#### 第四题

埃拉托斯特尼筛法是一种古老而简单的算法，用于找出小于指定值的所有素数。请编写一个名为 sieve 的方法，让它接受一个 int 参数 n，并返回一个boolean 数组，指出 0~n-1 的各个数是否为素数。

#### 第五题

编写一个名为 areFactors 的方法，让它接受一个 int 参数 n 和一个int 数组，并在这个数组的所有元素都是 n 的因数（即 n 可被所有元素整除）时返回 true。

#### 第六题

编写一个名为 arePrimeFactors 的方法，让它接受一个 int 参数 n 和一个 int 数组，并在这个数组的所有元素都为素数且它们的乘积为 n 时返回 true。

#### 第七题

(1) 编写一个名为 maxInRange 的方法，让它接受一个 int 数组和两个索引（lowIndex 和 highIndex），并在这两个索引指定的范围内（闭区间）找出最大的元素。
这个方法必须是递归的。如果范围为 1，即 lowIndex==highIndex，那么就意味着这个范围只包含一个元素，因此它就是最大的。所以这是基线条件。
如果这个范围包含多个元素，我们可将这个范围分成两部分，并在两部分中分别找出最大的元素，再在这两个最大的元素中找出更大的那个。

(2) maxInRange 这样的方法可能难以使用。要找出数组中的最大元素，我们必须将范围指定为整个数组。

```java
int max = maxInRange(a, 0, a.length - 1);
```

编写一个名为 max 的方法，让它接受一个数组，然后用 maxInRange 找出并返回其中的最大元素。



#### 第一题代码

```java
package Chapter8;
// 练习1
import java.util.Arrays;
public class Work9 {
    // 将原始数组的每个元素平方，保存到另一个数组输出
    public static double[] powArray (double[] a) {
        double[] b = new double[a.length];
        for (int i = 0; i < a.length; i++) {
            b[i] = Math.pow(a[i], 2);
        }
        return b;
    }
    // 将原始数组的每个元素乘以 n次方，保存到另一个数组输出
    public static double[] powArray (double[] a, int n) {
        double[] b = new double[a.length];
        for(int i = 0; i < a.length; i++) {
            b[i] = Math.pow(a[i] ,n);
        }
        return b;
    }

    public static void main (String[] args) {
        double[] a = {1.0, 2.0, 3.0, 4.0, 5.0};
        // 输出原数组、平方后的数组、n次方后的数组
        System.out.println(Arrays.toString(a));
        System.out.println(Arrays.toString(powArray(a)));
        System.out.println(Arrays.toString(powArray(a, 3)));
    }
}
```

#### 第二题代码

```java
package Chapter8;
// 练习2
import java.util.Arrays;
import java.util.Random;
public class Work10 {

    /**
     * 生成 n个随机数作为成绩
     * @param n 生成随机数的个数
     * @return 返回生成的随机数组 a
     */
    public static int[] randomScores (int n) {
        int[] a = new int[n];
        Random random = new Random();
        for (int i = 0; i < a.length; i++) {
            a[i] = random.nextInt(n);
        }
        return a;
    }
    /**
     * 将每个成绩出现的次数用直方图排序保存到数组
     * @param scores 输入的成绩的数组
     * @return 返回每个成绩次数的直方图
     */
    public static int[] histogram (int[] scores) {
        int[] counts = new int[scores.length];
        for (int count : scores) {
            counts[count]++;
        }
        return counts;
    }

    public static void main (String[] args) {
        int[] scores = randomScores(100); // 生成 100个成绩
        int[] histogram = histogram(scores); // 将成绩做成直方图
        System.out.println(Arrays.toString(histogram));
    }
}
```

#### 第三题代码

```java
package Chapter8;
// 练习3

public class Work11 {
    /**
     * 返回数组中最大值的坐标
     * @param a 需要返回最大值的数组
     * @return 返回坐标
     */
    public static int indexOfMax (int[] a) {
        int max = a[0]; // 定义数组中第一个数字
        int n = 0; // 定义坐标值
        for (int i = 0; i < a.length; i++) {
                if (a[i] > max) {
                    max = a[i]; // 找到最大值
                    n = i; // 确定最大值坐标
                }
        }
        return n;
    }

    public static void main (String[] args) {
        int[] a = {5,1,2,6,3,5};
        int max = indexOfMax(a);
        System.out.println(max);
    }
}
```

#### 第四题代码

```java
package Chapter8;
// 练习4
import java.util.Arrays;
public class Work12 {
    /*构造n以内的素数表，思路如下：
    1.令 i, j为 2
    2.将 2i、3i、4i直到 i*j < n的数标记为非素数
    3.令 i为下一个没有被标记为非素数的数，重复 2步；直到所有的数都被已经尝试完毕
    解决方案如下：
    构造 0~n-1(n个数) 的素数表
    1.创建数组 a为 boolean[n]，初始化其所有元素为 true，a[i]为 true表示 i是素数
    2.令 i=2
    3.如果 i是素数，则对于（i=2;i*j<n;++i)令 a[i*j]=false
      令 i++，如果 i<n，重复 3步，否则结束
     */
    public static boolean[] sieve (int n) {
        boolean[] a = new boolean[n]; // 定义一个 boolean型数组
        for (int i = 2; i < n; i++) {
            a[i] = true; // 将 2~n-1初始化为 true
        }
        for (int i = 2; i < n; i++) {
            // 标记 i是否为素数
            for (int j = 2; i * j < n; j++) {
                // 把 i的倍数(小于 n)全部标记为非素数
                // 结束循环，获得下一个 i
                if (a[i]) { // 查看 i是否为 true
                    // 如果 i是 true则把 i的倍数标记为 false
                    // 如果 i是 false则让第二个 for循环至结束
                    a[i * j] = false; // 标记 i的倍数(小于 n)为 false
                }
            }
        }
        return a;
    }

    public static void main(String[] args) {
        System.out.println(Arrays.toString(sieve(10)));
    }
}
```

#### 第五题代码

```java
package Chapter8;
// 练习5
import java.util.Arrays;
public class Work13 {
    /**
     * 接受一个 int参数 n和一个 int数组，并在这个数组的
       所有元素都是 n的因数（即 n可被所有元素整除）时返回 true
     * @param factors 接受的 int数组
     * @param n 接受的 int参数
     * @return 返回 true或者 false
     */
    public static boolean areFactors (int[] factors, int n) {
        boolean divisor = true; // 先定义整除为 true
        for (int factor : factors) { // 循环数组查看是否每个元素被 n整除
            if (n % factor != 0) { // 用 n除以元素,看看能否被整除
                divisor = false; // 如果不能被整除，返回值为 false
                break; // 结束 if语句
            }
        }
        return divisor;
    }

    public static void main (String[] args) {
        int[] factors = {1,2,5};
        int n = 10;
        System.out.println(areFactors(factors, n));
    }
}
```

#### 第六题代码

```java
package Chapter8;
// 练习6
public class Work14 {
    /**
     * 接受一个 int参数 n和一个 int数组，
       并在这个数组的所有元素都为素数且它们的乘积为 n时返回 true
     * @param factors 接受的数组
     * @param n 接受的整数
     * @return 返回是否为 ture
     */
    public static boolean arePrimeFactors (int[] factors, int n) {
        boolean divisor = true; // 定义整除为 true
        int product = 1; // 定义数组内所有数的乘积，初始为 1
        if (arePrime(factors)) { // 先判断是否为素数数组
            for (int factor : factors) {
                // 循环将所有数相乘，保存到 product中
                product = product * factor;
            }
            if (product != n) { // 判断乘积是否等于 n
                divisor = false; // 不等于 n则返回值为 false
            }
        }
        return divisor;
    }

    // 判断数组是否为素数
    public static boolean arePrime (int[] primes) {
        boolean arePrime = true; // 定义是素数为 true
        // 循环检查每个数是否为素数
        for (int i = 0; i < primes.length; i++) {
            // 从第一个数开始依次检查数组内的数字是否为素数
            for (int j = 2; j < primes[i]; j++) {
                if (primes [i] == 2) {
                    // 如果循环到数组内数字是 2则结束这次循环，2是素数
                    break;
                } else if (primes[i] % j == 0) {
                    // 不是 2则将这个数除以从 2开始比它小的所有数查看有无余数
                    // 无余数则不是素数，将 arePrime定义为 false并结束循环
                    // 但凡有一个数字不是素数，arePrime被定义为 false，后面无论是否有素数都会输出 false
                    arePrime = false;
                    break;
                }
            }
            if (primes[i] == 0 || primes[i] == 1) {
                // 再判断数组内是否有元素等于 0或 1，是的话重新定义返回值为 false
                arePrime = false;
            }
        }
        return arePrime;
    }

    public static void main (String[] args) {
        int[] a = {2,3};
        System.out.println(arePrimeFactors(a, 6));
    }
}
```

#### 第七题代码

```java
package Chapter8;
// 练习7
public class Work15 {
    // (1)接收一个数组和两个索引值，输出索引值之间的最大值
    public static int maxInRange (int[] arrays,int lowIndex, int highIndex) {
        int max = 0; // 定义并初始化最大值为 0
        for (int i = lowIndex; i <= highIndex; i++) {
            // i在两个索引值之间，闭区间
            if (max < arrays[i]) {
                max = arrays[i];
            }
        }
        return max;
    }
    // (2)将在 main中输出最大值的方法简化，只需要接收一个数组
    public static int max (int[] arrays) {
        return maxInRange(arrays, 0, arrays.length - 1);
    }

    public static void main (String[] args) {
        int[] arrays = {1,2,9,4,5};
        int max = max(arrays);
        System.out.println(max);
    }
}
```

# 9 字符串

## 9.1 字符

字符串提供了**提取字符的方法 charAt**，这个方法会返回一个 char，这是一种存储单个字符（而不是字符串）的基本类型。

```java
String fruit = "banana";
char letter = fruit.charAt(0);
```

实参 0 表示要提取位置 0 处的字符。与数组索引一样，字符串索引也从0 开始，因此，赋给变量 letter 的字符是字母 b。

字符的工作原理与前面介绍过的其他基本类型相似，可用关系运算符来比较它们：

```java
if (letter == 'a') {
	System.out.println('?');
}
```

字符字面量是用单引号括起的，如 'a'。不同于用双引号括起的字符串字面量，字符字面量只能包含一个字符。转义序列（如 '\t'）是合法的字符字面量，因为它们表示的是单个字符。

递增和递减运算符也可用于字符，因此下面的循环显示字母表中的所有字母：

```java
System.out.print("Roman alphabet: ");
for (char c = 'A'; c <= 'Z'; c++) {
	System.out.print(c);
}
System.out.println();
```

Java 用 Unicode 表示字符，因此字符串可存储西里尔文字和希腊文字，还可存储非字母文字（如中文），详情可见 CSDN 或 https://home.unicode.org/ 。在 Unicode 中，每个字符由一个字符编码表示，我们可将字符编码视为整数。大写的希腊字母的字符编码为 913~937，因此我们可以像下面这样显示希腊字母表：

```java
System.out.print("Greek alphabet: ");
for (int i = 913; i <= 937; i++) {
	System.out.print((char) i);
}
System.out.println();
```

这个示例使用了类型转换将指定范围内的每个整数都转换为相应的字符。

示例代码：

```java
package Chapter9;

public class Work1 {

    public static void main (String[] args) {
        System.out.println("显示字母表：");
        for (char c = 'A'; c <= 'Z'; c++) {
            System.out.print(c + " ");
        }
        System.out.println();

        System.out.println("显示希腊字母表：");
        for (int i = 913; i <= 937; i++) {
            char c = (char) i;
            System.out.print(c + " ");
        }
        System.out.println();
    }
}
```

## 9.2 字符串是不可修改的

字符串提供了**方法 toUpperCase 和 toLowerCase，它们可分别转换为大写和小写。**这些方法常常令人迷惑，因为它们好像修改了字符串，但实际上，这些方法以及其他字符串操作方法都不能修改字符串，因为字符串是不可修改的（immutable）。

对字符串调用 toUpperCase 将生成并返回一个新的字符串对象。请看下面的示例：

```java
String name = "Alan Turing";
String upperName = name.toUpperCase();
```

这些语句执行后，upperName 将指向字符串 "ALAN TURING"，但 name依然指向字符串 "Alan Turing"。

另一个很有用的方法是 **replace，它在字符串中查找并替换指定的子串**。例如，下面的代码将 "Computer Science" 替换为 "CS"：

```java
String text = "Computer Science is fun!";
text = text.replace("Computer Science", "CS");
```

这个示例演示了使用字符串方法的一种常见方式。它调用text.replace，然后 text.replace 方法返回一个引用，该引用指向新字符串 "CS is fun!"。接下来，它将这个引用赋给变量 text，使其不再指向原来的字符串。

这个赋值操作很重要；如果不保存返回的值，调用 text.replace 将不会有任何影响。

示例代码：

```java
package Chapter9;

public class Work2 {

    public static void main (String[] args) {
        String name = "Dog Japanese";
        String uppName = name.toUpperCase();
        System.out.println(uppName);
        System.out.println(name);
        name = name.toUpperCase();
        System.out.println(name);

        String text = "日本人是（⊂((・⊥・))⊃）";
        System.out.println(text);
        text = text.replace("（⊂((・⊥・))⊃）" , " ^(*￣(oo)￣)^");
        System.out.println(text);
    }
}
/* 输出：
DOG JAPANESE
Dog Japanese
DOG JAPANESE
日本人是（⊂((・⊥・))⊃）
日本人是 ^(*￣(oo)￣)^
*/
```

## 9.3 字符串遍历

下面的循环遍历了字符串变量 fruit 中的字符，并以每个字符独占一行的方式显示：

```java
for (int i = 0; i < fruit.length(); i++) {
	char letter = fruit.charAt(i);
	System.out.println(letter);
}
```

字符串提供了一个名为 **length** 的方法，该方法返回了字符串包含的字符数。**因为这是一个方法，所以调用它时必须指定空的实参列表——()。**

条件为 i<fruit.length()，这意味着当 i 与字符串长度相等时，这个条件为 false，循环将终止。

遗憾的是，改进的 for 循环不能用于遍历字符串。但你可以**将任何字符串转换为字符数字，再用改进的 for 循环来迭代：**

```java
for (char letter : fruit.toCharArray()) {
	System.out.println(letter);
}
```

为获取字符串的最后一个字符，你可能试图像下面这样做：

```java
int length = fruit.length();
char last = fruit.charAt(length); // 不对！
```

这些代码能够通过编译并运行，但其中对方法 charAt 的调用将引发`StringIndexOutOfBoundsException` 异常，这是因为 "banana" 没有索引为 6 的字符。由于索引从 0 开始，这 6 个字符的索引为 0~5。要获取最后一个字符，必须将 length 减 1。

```java
int length = fruit.length();
char last = fruit.charAt(length - 1); // 正确
```

很多字符串遍历操作涉及读取一个字符串并创建另一个字符串。例如，要想反转字符串，可按从后到前的顺序将字符依次加入到另一个字符串中：

```java
public static String reverse(String s) {
	String r = "";
	for (int i = s.length() - 1; i >= 0; i--) {
		r = r + s.charAt(i);
	}
	return r;
}
```

r 的初始值为 ""，即空字符串（empty string）；其中的循环按从后到前的顺序遍历 s 中的所有字符。每次执行循环时都创建一个新的字符串，并将其赋给 r。循环结束时，r 包含 s 的所有字符，但排列顺序相反。因此，reverse("banana") 的结果为 "ananab"。

示例代码：

```java
package Chapter9;

public class Work3 {

    public static void main (String[] args) {
        
        String fruit = "banana";
        
        // 遍历字符串变量 fruit中所有字符
        for (int i = 0; i < fruit.length(); i++) {
            char letter = fruit.charAt(i);
            //System.out.println(letter);
        }
        
        // 改进版的 for循环，先把字符变成数字再把数字变回字符
        for (char letter : fruit.toCharArray()) {
            //System.out.println(letter);
        }
        
        // 输出 fruit中最后一个字符
        int length = fruit.length();
        char letter = fruit.charAt(length - 1);
        //char letter = fruit.charAt(fruit.length() - 1)
        System.out.println(letter);
        
        // 翻转 fruit中的字符
        String flipFruit = "";
        for (int i = fruit.length() - 1; i >= 0; i--) {
            flipFruit = flipFruit + fruit.charAt(i);
        }
        System.out.println(flipFruit);
    }
}
```

## 9.4 子串

**方法 substring 返回一个新的字符串，其中包含已有字符串中从指定索引到末尾的字符。**

- fruit.substring(0) 返回 "banana"
- fruit.substring(2) 返回 "nana"
- fruit.substring(6) 返回 ""

第一个示例返回整个字符串的副本；第二个示例返回除前两个字符之外的所有其他字符；最后一个示例表明，如果实参为字符串的长度，则substring 将返回一个空字符串。

为理解方法 substring 的工作原理，绘制类似于图 9-1 所示的示意图大有裨益。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230325151409789.png" alt="image-20230325151409789" style="zoom:50%;" />	

图 **9-1**：包含 **6** 个字符的字符串状态图

与大多数的字符串方法一样，substring 也被重载；也就是说，substring 还有接受不同参数的其他版本。用两个实参调用substring 时，这两个实参将分别视为起始索引和终止索引：

- fruit.substring(0, 3) 返回 "ban"
- fruit.substring(2, 5) 返回 "nan"
- fruit.substring(6, 6) 返回 ""

注意，返回的字符串中不包含终止索引处的字符。substring 方法的这个版本简化了一些常见的操作。例如，要想从索引 i 处开始提取长度为len 的子串，可编写代码 `fruit.substring(i, i+len)`。

示例代码：

```java
package Chapter9;

public class Work4 {

    public static void main (String[] args) {

        String fruit = "banana";

        System.out.println(fruit.substring(0));
        System.out.println(fruit.substring(1));
        System.out.println(fruit.substring(2));
        System.out.println(fruit.substring(3));
        System.out.println(fruit.substring(4));
        System.out.println(fruit.substring(5));
        System.out.println(fruit.substring(6));
    }
}
/* 输出结果：
banana
anana
nana
ana
na
a
*/
```

## 9.5 方法indexOf

方法 indexOf 用于在字符串中查找字符。

```java
String fruit = "banana";
int index = fruit.indexOf('a');
```

这个示例确定了字符 'a' 在字符串中的索引，但因为这个字符出现了三次，所以 indexOf 的结果是什么并不那么明显。文档指出，**这个方法返回的是字符第一次出现处的索引。**

要想确定后面位置出现的索引，可使用另一个版本的 indexOf，它接受第二个实参，指定从字符串的什么位置开始查找。

```java
int index = fruit.indexOf('a', 2);
```

这些代码从索引 2（第一个 'n'）处开始查找下一个 'a'，这个 'a' 的索引为 3。如果要查找的字符刚好在起始索引处，结果将为起始索引，因此 `fruit.indexOf('a', 5)` 返回 5。

如果字符串中没有指定的字符，indexOf 将返回 -1。因为索引不可能为负，所以这个值表明没有找到指定的字符。

还可用 indexOf 查找子串，而不仅仅是单个字符。例如，表达式`fruit.indexOf("nan")` 返回 2。

```java
package Chapter9;

public class Work5 {

    public static void main (String[] args) {
        String fruit = "banana";
        int index1 = fruit.indexOf('a');
        int index2 = fruit.indexOf('a', 2);
        System.out.println(index1);
        System.out.println(index2);
    }
}
/* 输出结果
   1
   3
*/
```

## 9.6 字符串比较

你可能想用运算符 == 和 != 来比较两个字符串：

```java
String name1 = "Alan Turing";
String name2 = "Ada Lovelace";
if (name1 == name2) { // 不对!
	System.out.println("The names are the same.");
}
```

这些代码能够通过编译并运行，且在大多数情况下能得到正确的答案。但这并不是正确的，有时得到的答案也不对。这是因为运算符 == 通过比较引用来判断两个变量指向的是否为同一个对象。如果你让它比较两个包含相同字符的字符串，结果将为 false。

要比较字符串，正确的做法是像下面这样使用**方法 equals**：

```java
if (name1.equals(name2)) {
	System.out.println("The names are the same.");
}
```

这个示例对 name1 调用 equals，并将实参指定为 name2。如果两个字符串包含相同的字符，方法 equals 将返回 true，否则返回 false。

如果两个字符串不同，可用 compareTo 来确定按字母表顺序排列时哪个字符串在前：

```java
int diff = name1.compareTo(name2);
if (diff == 0) {
	System.out.println("The names are the same.");
} else if (diff < 0) {
	System.out.println("name1 comes before name2.");
} else if (diff > 0) {
	System.out.println("name2 comes before name1.");
}
```

**compareTo 的返回值为两个字符串中第一个不同的字符的差。如果两个字符串相等，则差为零；如果按字母表顺序排列时，第一个字符串（对其调用这个方法的字符串）在前，则差值为负，否则为正。**

在前面的代码中，compareTo 返回 8，这是因为 "Ada" 的第二个字母比 "Alan" 的第二个字母靠前 8 个位置。equals 和 compareTo 都区分大小写。因为大写字母排在小写字母前，所以 "Ada" 排在 "ada" 前。

```java
package Chapter9;

public class Work6 {

    public static void main (String[] args) {
        String name1 = "Dog Japanese";
        String name2 = "Pig Japanese";
        /*
        // 比较两个字符串用 equals
        if (name1.equals(name2)) {
            System.out.println("Japanese is dog.");
        } else {
            System.out.println("Ohh, Japanese is not only dog, and it also is pig!!!");
        }
        */
        // 用 compareTo来确定按字母表顺序排列时哪个字符串在前
        int diff = name1.compareTo(name2);
        if (diff == 0) {
            System.out.println("Japanese is dog.");
        } else if (diff < 0) {
            System.out.println("Japanese is dog and pig.");
        } else {
            System.out.println("Japanese is pig and dog.");
        }
    }
}
```

## 9.7 设置字符串的格式

我们在 3.6 节中学习了如何用 printf 以特定的格式显示输出。在有些情况下，程序需要创建特定格式的字符串，但不马上显示它们，甚至根本不显示。例如，下面的方法返回了一个以 12 小时制表示时间的字符串：

```java
public static String timeString(int hour, int minute) {
	String ampm;
	if (hour < 12) {
		ampm = "AM";
		if (hour == 0) {
			hour = 12; // 午夜
		}
	} else {
		ampm = "PM";
		hour = hour - 12; // 12小时制
	}
	return String.format("%02d:%02d %s", hour, minute, ampm);
}
```

**String.format** 接受的参数与 System.out.printf 相同：一个格式说明符和一系列的值。主要的差别在于，System.out.printf 将结果显示到屏幕上，而 String.format 创建一个新的字符串，但什么都不显示。

在这个示例中，格式说明符 %02d 表示将整数显示为两位（不够两位就添加前导零），因此 timeString(19, 5) 返回字符串 "07:05 PM"。

`%2d`和`%02d`的区别：

`%2d` 表示输出一个占位符，占用两个字符的宽度，左对齐，默认情况下右侧填充空格。例如，以下代码：

```java
int num = 5;
System.out.printf("%2d", num);
/* 输出为：
 5
```

注意到结果前面有一个空格，这是因为数字 5 只占用了一个字符的宽度，右侧填充了一个空格。

相反，`%02d` 表示输出一个占位符，占用两个字符的宽度，右对齐，默认情况下左侧填充 0。例如，以下代码：

```java
int num = 5;
System.out.printf("%02d", num);
/* 输出为：
05
```

注意到结果前面有一个 0，这是因为数字 5 只占用了一个字符的宽度，左侧填充了一个 0。

综上所述，`%2d` 和 `%02d` 的区别在于对齐方式和填充字符不同。`%2d` 左对齐并填充空格，`%02d` 右对齐并填充 0。

```java
package Chapter9;
// 十二小时制时间
public class Work7 {

    public static String timeString (int hour, int minute) {
        String ampm;
        if (hour == 0) {
            hour = 12; // 午夜 12点为 PM
            ampm = "PM";
        } else if (hour < 12) {
            ampm = "AM"; 
        } else if (hour == 12) {
            ampm = "AM"; // 中午 12点为 AM
        } else {
            hour = hour - 12; // 12小时制
            ampm = "PM";
        }
        return String.format("%02d : %02d %s", hour, minute, ampm);
    }

    public static void main (String[] args) {
        String time = timeString(0, 33);
        System.out.println(time);
    }
}
```

## 9.8 包装类

基本类型（如 int、double 和 char）不提供方法。例如，你不能对int 值调用 equals：

```java
int i = 5;
System.out.println(i.equals(5)); // 编译错误
```

但 Java 库包含与每种基本类型对应的类，这些类被称为包装类（wrapper class）。**与 char 对应的包装类为 Characte；与 int 对应的包装类为 Integer；其他包装类包括 Boolean、Long 和 Double。**这些包装类都位于 java.lang 包中，因此无需导入就可使用。

每个包装类都定义了常量 MIN_VALUE 和 MAX_VALUE。例如，**Integer.MIN_VALUE** 的值为 -2147483648，而**Integer.MAX_VALUE** 的值为 2147483647。因为包装类提供了这些常量，所以无需记住，也不用在程序中定义。

包装类提供了将字符串转换为其他类型的方法。例如，**Integer.parseInt 将字符串转换为整数**：

```java
String str = "12345";
int num = Integer.parseInt(str);
```

这里的分析（parse）指的是读取并转换。

其他的包装类提供了类似的方法，如 **Double.parseDouble 和Boolean.parseBoolean**。包装类还提供了方法 **toString**，它返回值的字符串表示：

```java
int num = 12345;
String str = Integer.toString(num);
```

结果为字符串 "12345"。

#### Characte的方法：

包装类 Character 是 Java 中用来包装基本数据类型 char 的类，它提供了一些方法来操作和转换字符。

- isLetter(char c)：判断指定的字符是否是字母；
- isDigit(char c)：判断指定的字符是否是数字；
- isWhitespace(char c)：判断指定的字符是否是空白字符；
- toUpperCase(char c)：将指定的字符转换为大写形式；
- toLowerCase(char c)：将指定的字符转换为小写形式；
- toString(char c)：将指定的字符转换为字符串。

#### Boolean的方法：

包装类Boolean是Java中的一个类，它用于封装基本类型boolean的值，以便可以将其作为对象来处理。

- Boolean.valueOf(String s)：将字符串转换为布尔值。
- Boolean.toString(boolean b)：将布尔值转换为字符串。
- boolean booleanValue()：返回Boolean对象的布尔值。
- Boolean.parseBoolean(String s)：将字符串解析为布尔值。
- Boolean.TRUE：表示布尔值为true的Boolean对象。
- Boolean.FALSE：表示布尔值为false的Boolean对象。

#### Double的方法：

包装类Double是用来将基本数据类型double封装成一个对象的类，它实现了Serializable接口和Comparable接口。

- parseDouble(String s)：将字符串s解析为double类型。
- valueOf(double d)：返回一个Double对象，它的值等于指定的double值d。
- doubleValue()：返回此Double对象所表示的基本double类型的值。
- toString()：返回此Double对象的字符串表示形式。
- compareTo(Double anotherDouble)：比较此Double对象和另一个Double对象的大小。
- isNaN()：判断此Double对象是否表示“非数字”（NaN）。
- isInfinite()：判断此Double对象是否表示无穷大或无穷小。

#### Integer的方法：

包装类 Integer 是 Java 中提供的一个类，它是 int 类型的包装器，可以将一个 int 类型的变量包装成一个对象。

- byteValue()：将 Integer 对象转换为 byte 类型的值。
- compare()：比较两个 Integer 对象的大小。
- parseInt()：将字符串解析为 int 类型的整数。
- valueOf()：将字符串解析为 Integer 类型的整数。
- toString()：将 Integer 对象转换为字符串。
- toBinaryString()：将整数转换为二进制字符串。
- toHexString()：将整数转换为十六进制字符串。
- toOctalString()：将整数转换为八进制字符串。

#### Long的方法：

包装类 Long 用于将 long 基本类型转换为 Long 对象，并在对象中封装它。Long 类型是一个 64 位的带符号的二进制补码整数，它的取值范围为 -2^63 到 2^63-1。

- Long.parseLong(String s)：将字符串 s 转换为 long 类型。
- Long.valueOf(String s)：将字符串 s 转换为 Long 类型的对象。
- Long.compare(long x, long y)：比较两个 long 类型的数值 x 和 y 的大小，返回值为 -1、0 或 1，分别表示 x < y、x = y 或 x > y。
- Long.bitCount(long i)：返回 long 型整数 i 的二进制补码表示中 1 的个数。

- Long.MAX_VALUE：Long 类型的最大值，即 2^63-1。
- Long.MIN_VALUE：Long 类型的最小值，即 -2^63。

## 9.9 命令行实参

前面一直对 main 方法的形参 args 置之不理，现在你已经熟悉了数组和字符串，我们终于可以说说 args 了。如果你不熟悉命令行界面，请阅读 A.3 节。

下面来编写一个程序以找出一系列数字的最大值。这里不从 System.in读取数字，而是通过命令行实参来传递它们。这个程序的初始版本如下：

```java
public class Work8 {
	public static void main(String[] args) {
		System.out.println(Arrays.toString(args));
	}
}
```

要运行这个程序，可在命令行中执行如下命令：

```
java .\Work8.java
```

输出表明，args 是个空数组（empty array），即不包含任何元素：

```
[]
```

但如果在命令行中提供了额外的值，它们将作为实参传递给 main。例如，如果你像下面这样运行这个程序：

```
java .\Work8.java 10 -3 55 0 14
```

输出如下：

```
[10, -3, 55, 0, 14]
```

别忘了，args 的元素为字符串。要想找出最大的数字，必须将这些实参转换为整数。

下面的代码片段结合使用了改进的 for 循环和包装类 Integer 来分析实参并找出最大的值：

```java
int max = Integer.MIN_VALUE;
for (String arg : args) {
	int value = Integer.parseInt(arg);
	if (value > max) {
		max = value;
	}
}
System.out.println("The max is " + max);
```

max 的初始值为 int 类型可表示的最小值，因此任何其他 int 值都比它大。如果 args 为空数组，结果将为 MIN_VALUE。

## 9.10 方法

### a.chart()

这个方法会返回一个 char，这是一种存储单个字符(而不是字符串)的基本类型。(9.1)

```java
a = "abcde";
char letter = a.charAt(0); // letter输出为 a
```

### a.toUpperCase()

转换为大写。(9.2)

```java
String name = "Dog Japanese";
String upperName = name.toUpperCase(); // 输出为 DOG JAPANESE
```

### a.toLowerCase()

转换为小写。(9.2)

```java
String name = "Dog Japanese";
String lowerName = name.toLowerCase(); // 输出为 dog janpanese
```

### a.length()

返回字符串包含的字符数。因为这是一个方法，所以调用它时必须指定空的实参列表——()。(9.3)

```java
int a = b.length(); // 定义 a的数值为数组 b的长度
```

### a.substring()

返回一个新的字符串，其中包含已有字符串中从指定索引到末尾的字符。(9.4)

```java
String a = "abcde";
String b = a.substring(2); // 字符串 b为 'cde'
```

### a.indexOf() 

用于在字符串中查找字符。(9.5)

```java
String a = "abcde";
int index = a.indexOf('a'); // index值为 0
```

### a.equals()     

比较字符串。(9.6)

```java
if (a.equals(b)) {
	System.out.println("a 和 b 相同");
}
```

### a.compareTo()

来确定按字母表顺序排列时哪个字符串在前。(9.6)

```java
int diff = a.compareTo(b);
```

### String.format()      

接受的参数与 System.out.printf 相同：一个格式说明符和一系列的值。主要的差别在于，System.out.printf 将结果显示到屏幕上，而 String.format 创建一个新的字符串，但什么都不显示。(9.7)

```java
String.format("%d %s", n, a);
```

### Integer.parseInt()     

将字符串转换对应的 `int` 类型的值。Integer方法在(9.8)

```java
String str = "12345";
int num = Integer.parseInt(str);
```

### Double.parseDouble

将字符串转换为对应的 `double` 类型的值。(9.8)

```java
double value = Double.parseDouble(str);
```

### Boolean.parseBoolean

将字符串转换为对应的 `boolean` 类型的值。(9.8)

```java
boolean value = Boolean.parseBoolean(str);
```

### a.toString()     

将对应的基本类型转换为字符串形式。(9.8)

```java
int i = 42;
String str = Integer.toString(i); // 将 int 类型的 i 转换为字符串
```

### Integer.MIN_VALUE

常量，表示整型数据类型 int 的最小值  -2147483648。(9.8)

### Integer.MAX_VALUE    

常量，表示整型数据类型 int 的最大值   2147483647。(9.8)

## 9.11 术语表

| 术语       | 含义                                                   |
| ---------- | ------------------------------------------------------ |
| 对象       | 一系列相关的数据以及一组操作这些数据的方法。           |
| 基本类型   | 存储单个值且没有提供任何方法的数据类型。               |
| Unicode    | 字符编码的一种标准，涵盖全球大部分语言中的字符。       |
| 不可修改的 | 一旦创建就不能修改的对象。字符串就被设计成不可修改。   |
| 空字符串   | 不包含任何字符且长度为零的字符串，用 "" 表示。         |
| 包装类     | java.lang 中的一些类，提供了处理基本类型的常量和方法。 |
| 分析       | 读取字符串并对其进行解读或转换。                       |
| 空数组     | 不包含任何元素且长度为零的数组。                       |

## 9.12 练习

#### 第一题

（1）创建一个新程序，并在 main 方法中编写一些用运算符 + 将不同数据类型“相加”的表达式。例如，如果将字符串和char“相加”，结果将会如何？这会执行字符加法运算还是执行字符串拼接操作呢？结果是什么类型？你又是如何确定结果类型的？
（2）在任何两种类型的交叉位置指出对它们使用运算符 + 是否合法，如果合法，将执行什么样的操作（加法运算还是拼接操作）？结果是什么类型呢？
（3）通常情况下，语句 x++ 与 x = x + 1 完全等价，但如果 x 为char，情况就不是这样了。在这种情况下，x++ 是合法的，但 x = x +1 将导致错误。请尝试这样做，看看将出现什么样的错误消息，并试着找出错误的原因。
（4）将 ""（空字符串）与其他类型的值相加（如 ""+5）时，结果将如何？

（5）可将哪些类型的值赋给各种类型的变量？例如，可将 int 值赋给double 变量，但反过来不行。

#### 第二题

编写一个名为 letterHist 的方法，让它接受一个字符串参数，并返回一个表示该字符串各字母出现次数的直方图。在返回的直方图中，第 0个元素为字母 a（不区分大小写）在这个字符串中出现的次数，第 25 个元素为字母 z 出现的次数。你的解决方案只能遍历该字符串一次。

#### 第三题

（1）编写一个方法，让它接受一个字符串参数，检查它包含的左括号数和右括号数是否相等，返回一个数字，如果是 0 ，则为相等。

（2）泛化这些代码使其适用于任何字符串，可以检查这个字符串任意一个字符的出现次数。

#### 第四题

创建一个程序，并在其中输入以下方法：

```java
// 返回给定字符串中的第一个字符。
public static char first(String s) {
	return s.charAt(0);
}
// 返回给定字符串中除第一个字符外的其他所有字符。
public static String rest(String s) {
	return s.substring(1);
}
// 返回给定字符串中除第一个和最后一个字符外的其他所有字符。
public static String middle(String s) {
	return s.substring(1, s.length() - 1);
}
// 返回给定字符串的长度。
public static int length(String s) {
	return s.length();
}
```

(1) 在 main 中编写一些代码以测试上述的每个方法。确认它们能够正确地工作，并确保你明白它们的功能。

(2) 编写一个名为 printString 的方法，让它接受一个字符串参数，并显示这个字符串中的所有字符，且每个字符独占一行。编写这个方法时，只能用前面定义的方法，不能用其他字符串方法。另外，这个方法应为 void 方法。

(3) 编写一个名为 printBackward 的方法，其功能与 printString 相同，但按相反的顺序显示字符串中的字符，且每个字符也独占一行。同样，在编写这个方法时，你只能用前面定义的方法。

(4) 编写一个名为 reverseString 的方法，让它接受一个字符串参数，并返回一个新的字符串。这个新字符串包含的字符与参数字符串相同，但排列顺序相反。

(5) 回文指的是顺着读和倒着读一样的单词，如 otto 和 palindromeemordnilap。一种判断单词是否为回文的方式如下：

只包含一个字母的单词是回文；单词包含两个字母时，如果这两个字母相同，那么这个单词是回文；对于其他的单词，如果第一个字母和最后一个字母相同，且余下的部分为回文，则这个单词为回文。

请编写一个名为 isPalindrome 的递归方法，让它接受一个字符串，并返回一个 boolean 值来指出这个字符串是否为回文。

#### 第五题

如果一个单词包含的字母是按字母表顺序排列的，那么这个单词就是 abecedarian 单词。例如，下面列出了所有按字母顺序排列的含 6 个字母的英语单词：

abdest, acknow, acorsy, adempt, adipsy, agnosy, befist, behint, beknow,

bijoux, biopsy,cestuy, chintz, deflux, dehors, dehort, deinos, diluvy, dimpsy

请编写一个名为 isAbecedarian 的方法，让它接受一个字符串，并返回一个 boolean 值，指出这个字符串表示的单词是否是按字母顺序排列的。编写的方法可以是迭代的，也可以是递归的。

#### 第六题

如果一个单词包含的每个字母都刚好出现两次，那么它就是 doubloon 单词。下面是字典中的一些 doubloon 单词：

Abba, Anna, appall, appearer, appeases, arraigning, beriberi, bilabial,

boob, Caucasus, coco, Dada, deed, Emmett, Hannah, horseshoer,

intestines, Isis, mama, Mimi, murmur, noon, Otto, papa, peep, reappear,

redder, sees, Shanghaiings, Toto

请编写一个名为 isDoubloon 的方法，让它接受一个字符串，并检查它是否为 doubloon 单词。为忽略大小写，可在检查前调用方法 toLowerCase。

#### 第七题

如果两个单词包含的字母相同，且其中的每个字母出现的次数也相同，那么这两个单词就是重组词。例如，单词 stop 是 pots 的重组词，而allen downey 是 well annoyed 的重组词。

请编写一个方法，让它接受两个字符串，并检查它们是否为重组词。

#### 第八题

在拼字游戏 Scrabble 中，每个玩家都有一组字母卡片，玩家需要用这些卡片拼出单词。其中的计分系统非常复杂，但一般而言，拼出的单词越长，得分越高。

假设以一个字符串（如 "quijibo"）的方式指定了你手中有哪些字母卡片，并要求你判断能否用这些卡片拼出另一个字符串，如 "jib"。

请编写一个名为 canSpell 的方法，让它接受两个字符串，并判断用第一个字符串指定的字母卡片能否拼出第二个字符串指定的单词。可能会有多个包含相同字母的卡片，但每个卡片只能用一次。



#### 第一题代码

```java
package Chapter9;
// 练习1（1）
public class Work9 {

    public static void main (String[] args) {
        String name = "Dog Japanese";
        char letter = 'a';
        System.out.println(name + letter); // 输出 String和 Char相加
        System.out.println((name + letter).getClass()); // 输出数据类型
    }
}
/* 
运行结果：
Dog Japanesea
class java.lang.String
执行的是字符串拼接操作
结果的数据类型是字符串类型
通过 get.Class()方法查看的数据类型
*/
```

| （2）   | boolean | char                                                         | int      | double                     | String                    |
| ------- | ------- | ------------------------------------------------------------ | -------- | -------------------------- | ------------------------- |
| boolean | null    | null                                                         | null     | null                       | null                      |
| char    | null    | 加法运算。结果仍然是char类型。例如，'a' + 'b'的结果为字符'蚤'（Unicode码值为195） | 加法运算 | 加法运算                   | 拼接操作                  |
| int     | null    | 加法运算。char 和 int 相加时，char 类型会被自动转换为 int 类型，然后进行计算，得到的结果也是 int 类型 | 加法运算 | 加法运算。结果为double类型 | 拼接操作。结果为Sting类型 |
| double  | null    | 加法运算。当char类型和double类型进行运算时，char类型会被自动转换为double类型，然后进行运算，最终结果也是double类型 | 加法运算 | 加法运算                   | 拼接操作                  |
| String  | null    | 拼接操作。结果是String类型                                   | 拼接操作 | 拼接操作                   | 拼接操作                  |

（3）代码：

```java
char x = 'a';
char y = 'a';
int n = 1;
x = x + 1; // 错误
int result = x + 1; // 正确
y = 'y' + 1; // 正确
//System.out.println(y);
```

错误消息：

```
ava: 不兼容的类型: 从int转换到char可能会有损失
```

错误原因：x为 char类型，1为 int类型，两个类型相加后的结果是 int类型，不可以直接相加赋值给 x，只能定义一个 int类型的数据来接收 char数据类型和 int数据类型相加后的结果。

解决方法：代码中有。如果像 result这种方法输出的是将 x转化为 int类型后的数字加1，而 y这种方法则是输出 y字母后面的一个字母，即 z，这是先把 y转化为 int加 1，然后再将结果转化为 char类型。

（4）代码：

```java
String nullString = "";
System.out.println(nullString + 5);
```

输出为：

```
5
```

（5）在 Java 中，有一些类型之间是可以互相转换的，这被称为类型转换（Type Casting）。在进行类型转换时，需要考虑数据类型的范围和精度。

下面是一些常见的类型转换规则：

1. 小类型可以自动转换成大类型，但大类型不能自动转换成小类型。
2. 在进行运算时，两个操作数的类型必须相同，否则需要将其中一个操作数转换成另一个操作数的类型。
3. 可以将任何类型的字面值直接赋给对应类型的变量。
4. 可以将基本数据类型的值赋给相应的包装类型变量，反之也可以。
5. 可以将字符类型的值赋给整数类型的变量，反之也可以。
6. 可以将整数类型的值赋给浮点数类型的变量，反之也可以，但可能会损失精度。
7. 在进行强制类型转换时，可能会出现数据丢失的情况。

例如，可以将 int 值赋给 double 变量，但反过来不行，因为 double 类型的范围比 int 更大，可以容纳更大的数字。同样，可以将 char 类型的值赋给 int 类型的变量，但反过来不行，因为 char 类型的范围比 int 更小，不能容纳 int 类型的所有值。

在进行类型转换时，需要注意数据类型的范围和精度，以确保转换后的值不会发生错误或数据丢失。

#### 第二题代码

```java
package Chapter9;
// 练习2
import java.util.Arrays;
public class Work10 {

    public static int[] letterHist (String words) {
        char[] upLetters = new char[26]; // 大写字母数组
        char[] downLetters = new char[26]; // 小写字母数组
        int[] results = new int[26]; // 26个字的数组，对应不区分大小写的 26个英文
        // 大写字母的次数
        // 将大写字母写入数组
        for (int i = 0; i < 26; i++) {
            upLetters[i] = (char)('A' + i);
        }
        // 遍历形参 words，查看形参中每个字母的出现次数
        for (int i = 0; i < words.length(); i++) {
            char word = words.charAt(i); // 从 0开始第 i个字母
            // 遍历大写字母数组，查看形参中的字母在哪个位置，加 1
            for (int j = 0; j < upLetters.length; j++) {
                if (upLetters[j] == word) {
                    results[j]++;
                }
            }
        }
        // 小写字母的次数（步骤同上）
        for (int i = 0; i < 26; i++) {
            downLetters[i] = (char)('a' + i);
        }
        for (int i = 0; i < words.length(); i++) {
            char word = words.charAt(i);
            for (int j = 0; j < downLetters.length; j++) {
                if (downLetters[j] == word) {
                    results[j]++;
                }
            }
        }
        return results;
    }

    public static void main (String[] args) {
        String word = "Aa Zz";
        System.out.println(Arrays.toString(letterHist(word)));
    }
}
/*
输出结果：
[2, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 0, 2]
*/
```

#### 第三题代码

```java
package Chapter9;
// 练习3
public class Work11 {
    // (1) 检查左右括号是否相等
    public static int parenthesesEqual (String s) {
        int count = 0;
        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);
            if (c == '(') {
                count++;
            } else if (c == ')') {
                count--;
            }
        }
        return count;
    }
    // (2) 检查字符串中字符出现次数
    public static int characterOccurrence (String s, char x) {
        int count = 0;
        for (int i = 0; i < s.length(); i++) {
            char c = s.charAt(i);
            if (c == x) {
                count++;
            }
        }
        return count;
    }

    public static void main (String[] args) {
        String s = "(1+2).(";
        char x = '+';
        System.out.println(parenthesesEqual(s));
        System.out.println(characterOccurrence(s, x));
    }
}
```

#### 第四题代码

```java
package Chapter9;

public class Work12 {

    // 返回给定字符串中的第一个字符。
    public static char first(String s) {
        return s.charAt(0);
    }

    // 返回给定字符串中除第一个字符外的其他所有字符。
    public static String rest(String s) {
        return s.substring(1);
    }

    // 返回给定字符串中除第一个和最后一个字符外的其他所有字符。
    public static String middle(String s) {
        return s.substring(1, s.length() - 1);
    }

    // 返回给定字符串的长度。
    public static int length(String s) {
        return s.length();
    }

    // 接受一个字符串参数，并显示这个字符串中的所有字符，且每个字符独占一行。
    public static void printString (String s) {
        for (int i = 0; i < s.length(); i++) {
            char character = s.charAt(i);
            System.out.println(character);
        }
    }

    // 其功能与 printString 相同，但按相反的顺序显示字符串中的字符，且每个字符也独占一行。
    public static void printBackward (String s) {
        for (int i = s.length() - 1; i >= 0; i--) {
            char character = s.charAt(i);
            System.out.println(character);
        }
    }

    // 接受一个字符串，将其倒过来返回一个新字符串
    public static String reverseString (String s) {
        String result = "";
        for (int i = s.length() - 1; i >= 0; i--){
            char character = s.charAt(i);
            result = result + character;
        }
        return result;
    }

    // 接受一个字符串，判断是否为回文
    public static boolean isPalindrome (String s) {
        boolean isPalindrome = false;
        String result = "";
        for (int i = s.length() - 1; i >= 0; i--){
            char character = s.charAt(i);
            result = result + character;
        }
        if (result.equals(s)) {
            isPalindrome = true;
        }
        return isPalindrome;
    }

    public static void main (String[] args) {
        String s = "Chinese";
//        System.out.println(first(s));
//        System.out.println(rest(s));
//        System.out.println(middle(s));
//        System.out.println(length(s));
//        printString(s);
//        printBackward(s);
//        System.out.println(reverseString(s));
//        System.out.println(isPalindrome(s));

    }
}
```

#### 第五题代码

```java
package Chapter9;
// 练习5
public class Work13 {
    // 接受一个字符串，并返回一个 boolean 值，指出这个字符串表示的单词是否是按字母顺序排列的。
    public static boolean isAbecedarian (String s) {
        boolean isAbecedarian = true; // 初始化为 true
        // 从第一个字符开始循环
        for (int i = 0; i < s.length(); i++) {
            char characterI = s.charAt(i); // 定义第一个字符
            // 从第二个字符开始循环，与第一个字符比较
            for (int j = i + 1; j < s.length(); j++) {
                char characterJ = s.charAt(j); // 定义第一个字符后面的字符
                // 比较第一个字符与后面字符的大小
                if (characterI >= characterJ) {
                    isAbecedarian = false;
                    break;
                }
            }

        }
        return isAbecedarian;
    }

    public static void main (String[] args) {
        String s = "abdest";
        System.out.println(isAbecedarian(s));
    }
}
```

#### 第六题代码

```java
package Chapter9;
// 练习6
import java.util.Arrays;
public class Work14 {

    public static boolean isDoubloon (String s) {
        boolean isDoubloon = true; // 初始化为 true
        s = s.toLowerCase(); // 将字符全部转换为小写
        char[] arrayS = s.toCharArray(); // 将字符串 s中的字符放在 char数组中保存
        Arrays.sort(arrayS); // 将数组中的字符从小到大排序
        String S = new String(arrayS); // 将 char数组中的元素合并到一起保存到字符串 S中
        // 查看 i和 i+1数是否相等，每次 i都会加 2来防止比较错误
        for (int i = 0; i < S.length(); i = i + 2) {
            char character0 = S.charAt(i); // 保存第 i个数
            char character1 = S.charAt(i + 1); // 保存第 i+1个数
            if (character1 != character0) {
                isDoubloon = false; // 如果不相等则返回值为 false
                break;
            }
        }
        return isDoubloon;
    }

    public static void main (String[] args) {
        String s = "qryqbyRB";
        System.out.println(isDoubloon(s));
    }
}
```

#### 第七题代码

```java
package Chapter9;
// 练习7
public class Work15 {

    public static boolean isRecombinationWord (String S, String s) {
        boolean isRecombinationWord = true; // 初始化
        // 将字符串 S转化为 int数据
        int St = 0; // 定义一个 St，将 S转化为的 Unicode储存到 St中
        for (int i = 0; i < S.length(); i++) {
            char character = S.charAt(i); // 每次循环保存下字符
            St = St + (int) character; // 将字符转化为 Unicode码保存
        }
        // 将字符串 s转化为 int数据
        int st = 0; // 定义一个 st，将 s转化为的 Unicode储存到 st中
        for (int i = 0; i < s.length(); i++) {
            char character = s.charAt(i);
            st = st + (int) character;
        }
        // 检查 St和 st是否相等
        if (St != st) {
            isRecombinationWord = false;
        }
        return isRecombinationWord;
    }

    public static void main (String[] args) {
        String S = "strings arg";
        String s = "trings agrs";
        System.out.println(isRecombinationWord(S, s));
    }
}
```

#### 第八题代码

```java
package Chapter9;
// 练习8
public class Work16 {
    /*
        解题思路：
        1、将两个字符串转成 char数组类型
        2、利用 for循环，从自己拼的单词转换的数组开始遍历(自拼单词)
        3、在 for循环中确立一个 flag，初始化为 false，每次新循环都会变为 false
        4、在 for循环中再套一个 for循环，遍历手上有的字母的数组(字母堆)
        5、在第二个 for循环中，查看自拼单词在字母堆里面是否能找到，能找到则
           把 flag改为 true，并将字母堆里的相同的元素去除掉。此处我写了一个
           新方法 newArray，作用是去除指定元素
        6、离开第二个 for循环，进入 if条件语句。如果发 flag是 true，则条件语句
           直接略过，开始第二次自拼数组遍历。如果 flag是 false，则证明自拼数组中
           的元素在字母堆里面没有找到，将返回值改为 false，之后不管怎么循环，它会一
           直为 false
        7、返回输出结果
     */
    // 检查组合的单词的每个字母是否能在原来的单词堆中找到，而且每个字母数量要相等
    public static boolean canSpell (String letter, String spell) {
        boolean canSpell = true; // 初始化
        char[] letters = letter.toCharArray(); // 把字符串 letter的元素保存到数组
        char[] spells = spell.toCharArray(); // 把字符串 spell的元素保存到数组
        // 查看 spells数组中的元素是否在 letters数组中一一对应
        for (int i = 0; i < spells.length; i++) {
            boolean flag = false; // 定义一个标杆，每次循环开始都为 false
            for (int j = 0; j < letters.length; j++) {
                if (spells[i] == letters[j]) {
                    flag = true; // 如果 spells数组中的元素在 letters数组能找到则为 true
                    letters = newArray(letters, letters[j]); // 将 letters数组中的已经用掉的元素去除
                }
            }
            if (!flag) {
                // 如果 flag为 false则证明上述循环中没有元素对应，则 ！flag为 true，执行以下操作
                canSpell = false;
            }
        }
        return canSpell;
    }

    // 去掉数组中用掉的元素
    public static char[] newArray (char[] array, char elem) {
        // 定义一个比原数组少一个元素的数组
        char[] newArray = new char[array.length - 1];
        int index = 0;
        // 将原数组去掉指定元素保存到新数组
        for (int i = 1; i < array.length; i++) {
            if (array[i] != elem) {
                newArray[index++] = array[i];
            }
        }
        return newArray;
    }

    public static void main (String[] args) {
        String letter = "aabcd";
        String spell = "ab";
        System.out.println(canSpell(letter, spell));
    }
}
```

# 10 对象

我们在前一章说过，对象是提供一组方法的数据集合。例如，String是一个字符串集合，提供了 charAt 和 substring 等方法。

Java 是一种“面向对象”的语言，这意味着它用对象来表示数据并提供与数据相关的方法。这种组织程序的方式是一种功能强大的设计理念，我们将在以下的篇幅中简单地介绍。

本章将介绍两种新的对象类型：Point 和 Rectangle；演示如何编写将对象作为参数的方法以及将对象作为返回值的方法；还将大致探讨一下Java 类库的源代码

## 10.1 Point对象

java.awt 包提供了一个名为 Point 的类，该类用于表示笛卡尔平面中的位置坐标。数学中通常将表示点的坐标放在括号内并用逗号分隔，例如，(0, 0) 表示原点，而 (*x*, *y*) 表示的点位于原点右方 *x* 个单位、上方 *y*个单位。

在 Java 中，`Point` 是一个表示二维空间中的坐标点的类。它通常用于在图形界面中表示鼠标或组件的位置，或者在绘图中表示图形的坐标。

`Point` 类有两个整型属性：x 和 y，表示坐标点的横坐标和纵坐标。`Point` 类还提供了一些有用的方法，如移动点、设置点的位置、判断两个点是否相等等等。

要使用 Point 类的话必须先导入：

```java
import java.awt.Point;
```

然后就可创建新的 Point 对象了。为此，必须使用运算符 new：

```java
Point blank;
blank = new Point(3, 4);
```

第 1 行将 blank 的类型声明为 Point；第 2 行新建了一个以指定实参为坐标的 Point 对象。

运算符 new 的结果为指向新对象的引用，因此 blank 包含一个指向新Point 对象的引用，如图10-1 所示。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230404092602841.png" alt="image-20230404092602841" style="zoom:50%;" /> 
图 **10-1**：指向一个 **Point** 对象的变量的状态图

与往常一样，变量名 blank 位于方框外，其指向的对象的值位于方框内。变量 blank 的值在这里是一个引用，用箭头表示。这个箭头指向新对象，后者包含两个变量——x 和 y。

在Java中，Point是一个用来表示二维平面上的点的类，包含了两个整型变量x和y，分别表示横坐标和纵坐标。Point类提供了一些常用的方法，例如：

- 构造方法：Point(int x, int y) 用给定的横纵坐标创建一个点对象。
- getX() 和 getY()：获取点对象的横纵坐标。
- setLocation(int x, int y)：设置点对象的横纵坐标。
- setLocation(Point p)：设置点对象的坐标为另一个点对象的坐标。
- distance(double x, double y) 和 distance(Point p)：计算点对象到给定点的距离。

Point类常用于表示图形中的一个点，例如画图和计算几何等方面。

## 10.2 属性

属于对象的变量通常称为属性（attribute），也有人称之为“字段”。Java 用句点表示法（dot notation）访问对象的属性，如下所示：

```java
int x = blank.x;
```

表达式 blank.x 的意思是，进入 blank 指向的对象，并获取其中的属性 x 的值。在这里，我们将这个值赋给了局部变量 x。局部变量 x 和属性 x 并不会发生冲突。句点表示法让你能够明确地指出引用的是哪个变量。

可以在表达式中使用句点表示法，如下所示：

```java
Point blank;
blank = new Point(3, 4);
int x = blank.x;
System.out.println(x);
System.out.println(blank.x + ", " + blank.y);
System.out.println(blank.x * blank.x + blank.y * blank.y);
```

第 1 行显示 `3`，第 2 行计算得到的值为 `3,  4`，第三行显示 `25`

## 10.3 将对象用作参数

可像通常那样将对象作为参数进行传递，例如：

```java
public static void printPoint(Point p) {
	System.out.println("(" + p.x + ", " + p.y + ")");
}
```

这个方法接受一个 Point 参数，并在括号中显示其属性。如果调用`printPoint(blank)`，它将显示 `(3, 4)`。

然而，我们并不需要 printPoint 这样的方法，因为调用`System.out.println(blank)` 将得到如下输出：

```java
java.awt.Point[x=3,y=4]
```

Point 对象提供了一个名为 toString 的方法，该方法返回点的字符串表示。以对象为参数调用 println 时，将自动调用 toString 并显示结果。这里显示的是类型名（java.awt.Point）以及属性的名称和值。

再来看一个例子。可将 6.2 节中的方法 distance 重写成将两个 Point对象而不是四个 double 值作为参数：

```java
public static double distance(Point p1, Point p2) {
	int dx = p2.x - p1.x;
	int dy = p2.y - p1.y;
	return Math.sqrt(dx * dx + dy * dy);
}
```

将对象作为参数可让源代码更易理解且不易出错，因为相关的值被关联起来了。

代码如下：

```java
package Chapter10;
import java.awt.Point;
public class Work1 {
    // 输出 (x, y)形式
    public static void printPoint (Point p) {
        System.out.println("(" + p.x + ", " + p.y + ")");
    }
    // 求两点间距离
    public static double distance (Point p1, Point p2) {
        int dx = p1.x - p2.x;
        int dy = p1.y - p2.y;
        return Math.sqrt(dx*dx + dy*dy);
    }
    
    public static void main (String[] args) {
        Point blank, blank2;
        blank = new Point(3, 4);
        blank2 = new Point(4, 5);
        int x = blank.x;
        System.out.println(x);
        System.out.println(blank.x + ", " + blank.y);
        System.out.println(blank.x * blank.x + blank.y * blank.y);
        printPoint(blank);
        System.out.println(blank);
        System.out.println(distance(blank, blank2));
    }
}
```

## 10.4 将对象作为返回类型

java.awt 包还提供了一个名为 Rectangle 的类。要使用这个类的话必须先导入：

```java
import java.awt.Rectangle;
```

`Rectangle` 是 Java 中的一个类，用于表示矩形。它提供了一系列方法来计算矩形的大小、位置和关系等。

Rectangle 对象类似于 Point，但有四个属性：x、y、width 和 height。**x 和 y 代表的是左上角点的横纵坐标**。下面的示例创建了一个 Rectangle 对象，并让变量 box 指向它：

```java
Rectangle box = new Rectangle(0, 0, 100, 200);
```

图 10-2 说明了这条赋值语句的作用。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230404110321821.png" alt="image-20230404110321821" style="zoom:50%;" /> 
						 图 **10-2**：显示一个 **Rectangle** 对象的状态图	

如果运行 System.out.println(box)，那么将得到如下输出：

```java
java.awt.Rectangle[x=0,y=0,width=100,height=200]
```

同样，println 调用了 Rectangle 提供的方法 **toString**，这个方法知道如何显示 Rectangle 对象。

你可以编写返回对象的方法。例如，findCenter 接受一个 Rectangle 参数，并返回一个 Point，其中包含该矩形中心的坐标：

```java
public static Point findCenter(Rectangle box) {
	int x = box.x + box.width / 2;
	int y = box.y + box.height / 2;
	return new Point(x, y);
}
```

这个方法的返回类型为 Point。最后一行创建了一个新的 Point 对象，并返回一个指向该对象的引用。

`Rectangle` 类的常用属性和方法如下：

- `int x`：矩形的左上角 x 坐标
- `int y`：矩形的左上角 y 坐标
- `int width`：矩形的宽度
- `int height`：矩形的高度
- `boolean contains(int x, int y)`：判断点 (x, y) 是否在矩形内部
- `boolean contains(Rectangle r)`：判断矩形 r 是否完全在矩形内部
- `boolean intersects(Rectangle r)`：判断矩形 r 是否和当前矩形有交集
- `Rectangle intersection(Rectangle r)`：返回当前矩形和矩形 r 的交集
- `void setLocation(int x, int y)`：设置矩形的左上角坐标
- `void setSize(int width, int height)`：设置矩形的宽度和高度

示例代码：

```java
package Chapter10;
import java.awt.*;

public class Work2 {

    // 矩形中心坐标
    public static Point findCenter (Rectangle box) {
        int x = box.x + box.width / 2;
        int y = box.y + box.height / 2;
        return new Point(x, y);
    }

    public static void main (String[] args) {
        Rectangle box = new Rectangle(0, 0, 20, 10);
        System.out.println(box);
        System.out.println(findCenter(box));    
    }
}
```

## 10.5 可修改的对象

可通过给对象的属性赋值来修改对象的内容。

例如，要移动矩形而不改变其尺寸，可修改属性 x 和 y：

```java
Rectangle box = new Rectangle(0, 0, 100, 200);
box.x = box.x + 50;
box.y = box.y + 100;
```

结果如图 10-3 所示。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230404150415625.png" alt="image-20230404150415625" style="zoom:50%;" /> 
图 **10-3**：显示最新属性值的状态图

我们可将这些代码封装到一个方法中后再进行泛化，让这个方法能够将矩形移动任何指定的距离：

```java
public static void moveRect(Rectangle box, int dx, int dy) {
	box.x = box.x + dx;
	box.y = box.y + dy;
}
```

变量 dx 和 dy 用于指定将矩形沿水平和垂直方向分别移多远。调用这个方法将修改作为实参传入的 Rectangle 对象。

```java
Rectangle box = new Rectangle(0, 0, 100, 200);
moveRect(box, 50, 100);
System.out.println(box);
```

将对象作为实参传递给方法以便修改十分有用，但也可能导致调试更加困难，因为并非在任何情况下都能清楚地知道哪些方法会修改其实参。

Java 提供了很多操作 Point 和 Rectangle 对象的方法，例如，**translate** 的效果与 moveRect 相同，但调用这个方法时，不是将Rectangle 对象作为实参传递给它，而是用句点表示法：

```java
box.translate(50, 100);
```

这行代码对 box 指向的对象调用方法 translate，因此将直接更新对象 box。

这个示例很好地演示了面向对象（object-oriented）编程：不是编写moveRect 这样修改一个或多个实参的方法，而是用句点表示法对对象调用方法。

## 10.6 制定别名

别忘了，将对象赋给变量时，赋给变量的实际上是指向对象的引用。可让**多个变量指向同一个对象**，如下所示：

```java
Rectangle box1 = new Rectangle(0, 0, 100, 200);
Rectangle box2 = box1;
```

结果如图 10-4 所示。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230404153152324.png" alt="image-20230404153152324" style="zoom:50%;" /> 
图 **10-4**：两个变量指向同一个对象的状态图

请注意，**box1 和 box2 是同一个对象的别名，因此，影响其中一个变量的修改也将影响另一个变量。**下面的示例将这个矩形的左上角向左、向上各移了 50 个单位，并将其高度和宽度都增加了 100 个单位：

```java
System.out.println(box2.width);
box1.grow(50, 50);
System.out.println(box2.width);
```

第 1 行显示 100，这是 box2 指向的 Rectangle 对象的宽度；第 2 行对box1 调用方法 **grow**，这个方法**增大 Rectangle 对象的水平和垂直尺寸**，结果如图 10-5 所示。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230404153216886.png" alt="image-20230404153216886" style="zoom:50%;" /> 
图 **10-5**：说明调用 **grow** 效果的状态图

通过 box1 所做的修改也将影响 box2，因此第 3 行显示的值为 200——增大后的矩形的宽度。

## 10.7 关键字null

创建对象变量时，别忘了你在这种变量中存储的是指向对象的引用。

Java 中的关键字 null 是一个特殊值，意思是“**没有指向任何对象**”。可像下面这样声明并初始化对象变量：

```java
Point blank = null;
```

状态图中用不带箭头的方框表示值 null，如图 10-6 所示。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230404155012106.png" alt="image-20230404155012106" style="zoom: 80%;" /> 

图 **10-6**：包含 **null** 引用的对象变量的状态图

如果试图通过访问属性或调用方法来使用 null 值，那么将引发`NullPointerException` 异常。

```java
Point blank = null;
int x = blank.x; // NullPointerException
blank.translate(50, 50); // NullPointerException
```

另一方面，将 null 引用作为实参或返回值是完全合法的。例如，null 常用来表示特殊情况或指出错误。

## 10.8 垃圾收集

10.6 节说明了多个变量指向同一个对象会带来的后果。如果一个对象没有被任何变量指向，结果将如何呢？

```Java
Point blank = new Point(3, 4);
blank = null;
```

第 1 行创建了一个新的 Point 对象，并让 blank 指向它；第 2 行修改变量 blank，使其不指向任何对象。在状态图中，变量 blank 和这个Point 对象之间的箭头将被删除，如图 10-7 所示。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230404155941891.png" alt="image-20230404155941891" style="zoom:50%;" /> 
图 **10-7**：将变量设置为 **null** 效果的状态图

对于未被任何变量指向的对象，则无法访问其属性，也无法对其调用方法。在程序员看来，这样的对象已不复存在，但它依然驻留在计算机内存中，占据着内存空间。

系统会在程序运行时自动查找并回收无主对象；再将它们占据的空间用于存储新对象。这个过程被称为垃圾收集（garbage collection）。

垃圾收集是自动进行的，你什么都不用做，一般都意识不到垃圾收集过程的存在。但在高性能应用程序中，你可能时不时地会注意到些微的延迟，这是因为 Java 在回收被丢弃的对象所占据的空间。

## 10.9 类图

现在总结一下本章前面介绍的知识。Point 和 Rectangle 对象都有属性和方法；属性是对象的数据，方法是对象的代码；对象有哪些属性和方法由其所属的类定义。

在实践中，查看描述类的简图比研究其源代码更方便。统一建模语言（Unified Modeling Language，UML）定义了一种概述类设计的标准方式。

如图 10-8 所示，类图（class diagram）由两部分组成,上半部分列出了属性，下半部分列出了方法。UML 使用了一种独立于语言的格式，因此在类图中显示的不是 int x，而是 x: int。

![image-20230404160135612](C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230404160135612.png)

图 **10-8**：**Point** 和 **Rectangle** 的 **URM** 类图

状态图描述的是程序运行时的对象和变量，而类图描述的是编译时的源代码。

图 10-8 所示的类图中只列出了本章介绍过的方法，但 Point 和Rectangle 都还包含其他方法。要想更详细地了解这些类的功能，请参阅相关的文档。

## 10.10 Java类库的源代码

前面一直在使用 Java 类库中的类，包括System、String、Scanner、Math、Random 等。你可能还没有意识到这些类也是用 Java 编写的。事实上，可通过查看源代码来了解它们的工作原理。

Java 类库包含数千个文件，其中的很多文件都包含数千行代码。完全阅读并理解这些代码超出了个人的能力范围，因此千万不要感到害怕！

因为 Java 类库很大，所以其源代码存储在一个名为 src.zip 的文件中。请花点时间在你的计算机中找到这个文件。

- 在 Linux 系统中，它很可能位于目录 /usr/lib/jvm/openjdk-8/ 中（可能需要安装 openjdk-8-source 包）。
- 在 OS X 系统中，它很可能位于目录/Library/Java/JavaVirtualMachines/jdk.../Contents/Home/ 中。
- 在 Windows 系统中，它很可能位于目录 C:\Program Files\Java\jdk...\中。

将这个文件打开或解压后，你将看到与各个 Java 包对应的文件夹。例如，如果依次打开文件夹 java 和 awt，你将看到 Point.java 和 Rectangle.java，以及 java.awt 包中的其他类。

请在编辑器中打开 Point.java，并粗略地浏览一下这个文件。它使用了我们还未讨论的语言功能，因此可能很难理解，但通过浏览这个库，你可以感受一下专业的 Java 软件是什么样的。

注意，Point.java 包含详尽的文档。每个方法都有详尽的注释，包括@param、@return 和其他 Javadoc 标签。Javadoc 通过阅读这些注释来生成 HTML 格式的文档。要想知道最终生成的 HTML 文件是什么样的，请阅读 Point 类的文档，而要找到这些文档，可在网上搜索 Java Point。

现在来看看 Rectangle 的方法 grow 和 translate。这些方法的功能比你所知道的要多，但这并不妨碍你在程序中使用它们。

这里对本章的内容作个总结。对象封装了数据并提供了可直接访问和修改这些数据的方法；面向对象编程能够将繁杂的细节隐藏起来，从而让你更轻松地使用和理解他人编写的代码。

## 10.11 方法

### point

在 Java 中，`Point` 是一个表示二维空间中的坐标点的类。它通常用于在图形界面中表示鼠标或组件的位置，或者在绘图中表示图形的坐标。

`Point` 类有两个整型属性：x 和 y，表示坐标点的横坐标和纵坐标。`Point` 类还提供了一些有用的方法，如移动点、设置点的位置、判断两个点是否相等等等。

必须先导入 ：

```java
import java.awt.Point;
```

- `Point(int x, int y)`：用给定的横纵坐标创建一个点对象。
- `getX()` 和 `getY()`：获取点对象的横纵坐标。
- `setLocation(int x, int y)`：设置点对象的横纵坐标。
- `setLocation(Point p)`：设置点对象的坐标为另一个点对象的坐标。
- `distance(double x, double y)` 和 `distance(Point p)`：计算点对象到给定点的距离。

### elem.x

elem 的横坐标

### elem.y

elem 的纵坐标

### Rectangle

`Rectangle` 是 Java 中的一个类，用于表示矩形。它提供了一系列方法来计算矩形的大小、位置和关系等。(10.4)

必须先导入：

```java
import java.awt.Rectangle;
```

`Rectangle` 类的常用属性和方法如下：

- `int x`：矩形的左上角 x 坐标
- `int y`：矩形的左上角 y 坐标
- `int width`：矩形的宽度
- `int height`：矩形的高度
- `boolean contains(int x, int y)`：判断点 (x, y) 是否在矩形内部
- `boolean contains(Rectangle r)`：判断矩形 r 是否完全在矩形内部
- `boolean intersects(Rectangle r)`：判断矩形 r 是否和当前矩形有交集
- `Rectangle intersection(Rectangle r)`：返回当前矩形和矩形 r 的交集
- `void setLocation(int x, int y)`：设置矩形的左上角坐标
- `void setSize(int width, int height)`：设置矩形的宽度和高度

### elem.translate

translate 方法是 Rectangle 类的一个成员方法，可以用于移动绘图区域的原点。

必须先导入：

```java
import java.awt.Rectangle;
```

它的使用方法：

```java
Rectangle box = new Rectangle(x, y, width, height);
box.translate(dx, dy); 
```

其中，x 和 y 分别是要将绘图区域原点移动的水平和垂直距离。调用该方法后，绘图区域的原点将移动到当前位置的(x + dx, y + dy)处。可以使用负数来向相反方向移动原点。

示例如下：

```java
Rectangle box = new Rectangle(10, 10, 50, 100);
box.translate(20, 10); // 向右移动 20，向上移动 10
/* 输出：
java.awt.Rectangle[x=30,y=20,width=50,height=100]
```

### elem.grow

row 方法是 Rectangle 类的一个成员方法，用于扩大或缩小矩形的大小。

必须先导入：

```java
import java.awt.Rectangle;
```

它的使用方法：

```java
Rectangle box = new Rectangle(x, y, width, height);
box.translate(h, v); 
```

其中，h 表示要添加到矩形左边和右边的水平空间量，v 表示要添加到矩形顶部和底部的垂直空间量。如果 h 和 v 都是正数，那么矩形的大小将增加；如果它们都是负数，那么矩形的大小将减小。如果 h 是负数而 v 是正数，那么矩形的左侧将移动向左，而右侧将保持不变；如果 h 是正数而 v 是负数，那么矩形的顶部将向上移动，而底部将保持不变。

示例如下：

```java
Rectangle box = new Rectangle(10, 10, 50, 100);
box.grow(50,50); // h为左右拉伸 50，v为上下拉伸 50
/* 输出：
java.awt.Rectangle[x=-40,y=-40,width=150,height=200]
```

### BigInteger

BigInteger 是 Java 中的一个类，用于处理任意精度的整数，可以处理比 long 类型更大的整数。与 int 和 long 等基本数据类型不同，BigInteger 对象是不可变的，也就是说，一旦创建了一个 BigInteger 对象，就不能修改它的值，只能通过运算得到一个新的 BigInteger 对象。

- `num.add(val)`：将 num 与 val 相加。（val 也是 BigInteger）
- `num.subtract(val)`：将 num 减去 val。（val 也是 BigInteger）
- `num.multiply(val)`：将 num 与 val 相乘。（val 也是 BigInteger）
- `num.divide(val)`：将 num 除以 val。（val 也是 BigInteger）
- `num.mod(val)`：返回 num 除以 val 的余数。（val 也是 BigInteger）
- `num.abs()`：返回 num 的绝对值。
- `num.negate()`：返回 num 的相反数。
- `num.pow(int exponent)`：返回 num 的 exponent 次幂。
- `num.compareTo(val)`：将 num 与 val 进行比较。（val 也是 BigInteger）
- `num.equals(Object x)`：将 num 与指定对象进行比较。
- `num.toString()`：返回 num 的字符串表示形式。

## 10.12 术语表

| 术语       | 含义                                             |
| ---------- | ------------------------------------------------ |
| 属性       | 对象中的命名数据项。                             |
| 句点表示法 | 用句点运算符（.）访问对象的属性或方法。          |
| 面向对象   | 将代码和数据组织成对象，而不是独立的方法。       |
| 垃圾收集   | 找出未被引用的对象并收回其占据的存储空间的过程。 |
| UML        | 统一建模语言，软件工程领域中的一种标准绘图方式。 |
| 类图       | 对类的属性和方法进行描述的插图。                 |

## 10.13 练习

### 第一题

你可能对 `factorial` 方法感到厌烦了，但你还得再编写一个版本。（阶乘）

(1) 新建一个程序，并编写（或重用）方法`factorial` 的迭代（递归）版本。

(2) 以表格的方式显示整数 0~30 及其阶乘。你可能会发现，结果到 15左右就不再正确了。这是为什么呢？

(3) `BigInteger` 是一个 Java 类，可用于表示任意大的整数，它可表示的最大整数只受制于内存量和处理速度。请花点时间阅读这个类的文档。可在网上搜索 Java BigInteger 来找这个文档。

要想使用 `BigInteger`，必须在程序开头导入`java.math.BigInteger`。

创建 `BigInteger` 对象的方式有很多种，但最简单的方式是使用`valueOf`。下面的代码将一个整数转换为 `BigInteger` 对象：

```java
int x = 17;
BigInteger big = BigInteger.valueOf(x);
```

因为 `BigInteger` 不是基本数据类型，所以对其执行数学运算时，不能用常规的数学运算符，而必须用 add 等方法。要想将两个`BigInteger` 相加，可对其中一个调用方法 `add`，并将另一个作为实参：

```java
BigInteger small = BigInteger.valueOf(17);
BigInteger big = BigInteger.valueOf(1700000000);
BigInteger total = small.add(big);
```

请尝试使用其他方法，如 `multiply` 和 `pow`。

(4) 修改方法 `factorial`，在其中用 `BigInteger` 来执行计算，并将结果作为 `BigInteger` 返回。可保留其中的形参，因为其类型还是 `int`。

(5) 修改方法 factorial 后，再次尝试以表格的方式显示 0~30 及其阶乘。计算出的 30 的阶乘正确吗？参数值最多可到多少结果依然是正确的？

(6) BigInteger 对象是可修改的还是不可修改的？你是怎么知道的？

​		答：
​		BigInteger 对象是不可修改的（immutable），也就是一旦创建后就不能再修改其值，任何修		改操作都会创建一个新的 BigInteger 对象。因此，BigInteger 对象的值可以被安全地共享和传		递，而不用担心数据被不小心修改。搜的ChatGPT。

### 第二题

很多加密算法需要计算大整数的幂，下面的方法实现了一种高效的整数幂算法：

```java
public static int pow(int x, int n) {
	if (n == 0) return 1;
		// 递归地计算x的n/2次幂
		int t = pow(x, n / 2);
		// 如果n为偶数，结果就是t的平方
		// 如果n为奇数，结果就是t的平方乘以x
		if (n % 2 == 0) {
			return t * t;
		} else {
			return t * t * x;
	}
}
```

这个方法存在的问题是，仅当结果小到能够用 int 类型表示时，它才管用。请修改这个方法，在其中用 BigInteger 对象来存储结果，但形参可保留为 int 类型。

你应该使用 BigInteger 的方法 add 和 multiply，但不要使用方法BigInteger.pow，不然就太没意思了。

### 第一题代码

```java
package Chapter10;
// 练习1
import java.math.BigInteger;
public class Work4 {

    // (1)计算 n的阶乘(递归)
    public static int factorial (int n) {
        if (n == 0) {
            return 1;
        } else {
            return n * factorial(n - 1);
        }
    }

    // (2)以表格的方式显示 0-30 的阶乘
    public static void factorialTable (int n) {
        int[] table = new int[n + 1]; // 加上 0有 n + 1个数
        for (int i = 0; i < table.length; i++) {
            table[i] = factorial(i); // 保存每个数字的阶乘
            if (i % 4 == 0 && i != 0) { // 表格四列
                System.out.println();
            }
            System.out.printf("%2d! = %-10d", i, table[i]);
            System.out.print("\t"); // 每一次输出后都加个 TAB格，也可以把 %d中间数组调大
        }
    }

    // (3)BigInteger的加减乘除平方
    public static void big (int n) {
        BigInteger big = BigInteger.valueOf(n);
        BigInteger small = BigInteger.valueOf(5);
        BigInteger sum = big.add(small);
        BigInteger sub = big.subtract(small);
        BigInteger mul = big.multiply(small);
        BigInteger div = big.divide(small);
        BigInteger pow = big.pow(2); // 平方不能用 BigInteger

        System.out.println("sum = " + sum);
        System.out.println("sub = " + sub);
        System.out.println("mul = " + mul);
        System.out.println("div = " + div);
        System.out.println("pow = " + pow);
    }

    // (4)使用 BigInteger增强 factorial
    public static BigInteger factorialX (int n) {
        BigInteger big = BigInteger.valueOf(n);
        BigInteger value = BigInteger.valueOf(1);
        if (n == 0) {
            return value;
        } else {
            return big.multiply(factorialX(n - 1));
        }
    }

    // (5)使用修改后的 factorial以表格的方式显示 0~30 及其阶乘。
    public static void factorialXTable (int n) {
        BigInteger[] table = new BigInteger[n + 1];
        for (int i = 0; i < table.length; i++) {
            table[i] = factorialX(i);
            if (i % 3 == 0 && i != 0) {
                System.out.println();
            }
            System.out.printf("%2d! = %-35d", i, table[i]);
        }
    }

    public static void main (String[] args) {
        int n = 30;
//        System.out.println(factorial(n));
//        factorialTable(n);
//        big(n);
        System.out.println(factorialX(n));
        factorialXTable(n);
    }
}
```

### 第二题代码

```java
package Chapter10;
// 练习2
import java.math.BigInteger;
public class Work5 {

    // 整数幂算法(把 x的 n次幂变成 x的 n/2次幂，然后两次相乘。奇数就)
    public static int pow(int x, int n) {
        if (n == 0) return 1;
        // 递归地计算x的n/2次幂
        int t = pow(x, n / 2); // 如果 n是奇数则向下取整
        // 如果n为偶数，结果就是t的平方
        // 如果n为奇数，结果就是t的平方乘以x
        if (n % 2 == 0) {
            return t * t;
        } else {
            return t * t * x;
        }
    }

    // 使用 BigInteger增强的 pow方法：
    public static BigInteger powX (int x, int n) {
        if (n == 0) return BigInteger.valueOf(1);
        BigInteger t = BigInteger.valueOf(x).pow(n / 2);
        if (n % 2 == 0) {
            return t.multiply(t);
        } else {
            return t.multiply(t).multiply(BigInteger.valueOf(x));
        }
    }

    public static void main (String[] args) {
        int x = 200;
        int n = 30;
        System.out.println(powX(x, n));
    }
}
```

# 11 类

每当定义新类时，就创建了一个同名的新类型。因此，在 1.4 节中定义Hello 类时，就创建了一种名为 Hello 的类型。我们没有声明任何类型为 Hello 的变量，也没有用 new 创建 Hello 对象。即便这样做了，创建出的 Hello 对象的用处也不大，但我们确实可以这样做！

我们将在本章中定义表示有用的对象类型的类，还将表明类和对象之间的差别。下面列出了一些最重要的理念。

- 定义类（class）就创建了同名的对象类型。
- 每个对象都属于某种对象类型，即是某个类的实例（instance）。
- 类定义相当于创建对象的模板，指定了对象包含哪些属性以及哪些方法可以操作这些属性。
- 类犹如建筑设计图，可根据同一张设计图建造出很多房子。
- 操作对象的方法是在对象所属的类中定义的。

## 11.1 Time类

为何要定义新类呢？这样做的一个常见目的是将相关的数据封装到对象中，以便能够将它们视为一个整体。这样我们就可以将对象用作参数和返回值，而不传递和返回多个值。这种设计原则被称为数据封装（data encapsulation）。

前面介绍了两个以这种方式封装数据的类型：Point 和 Rectangle。另一个这样的类型是表示时间的 Time，我们将在本章实现它。Time 对象封装的数据为小时、分钟和秒数。因为每个 Time 对象都包含这些数据，所以我们将定义存储它们的属性。

属性也被称为实例变量（instance variable），因为每个实例都包含这些变量，与之相反的是类变量（将在 12.3 节中介绍）。

第一步是判断各个变量应为什么类型。hour 和 minute 显然应为整数，但为了让这个类有趣些，我们将 second 声明为 double 类型。

实例变量是在类定义开头（而不是方法中）声明的。下述代码片段本身就是一个合法的类定义：

```java
public class Time {
	private int hour;
	private int minute;
	private double second;
}
```

Time 类是公有的，这意味着可在其他类中使用。但这些实例变量是私有的，这意味着只能在 Time 类中访问。如果你试图在其他类中读写它们，那么将导致编译错误。`private` 是 Java 中的访问修饰符，用于控制类中的成员变量和方法的访问范围。使用 `private` 修饰的成员变量和方法只能在当前类中被访问，无法在类外部被直接访问。

将实例变量声明为私有的有助于将类隔离开来，避免修改一个类后必须相应地修改其他类；还可让其他程序员在使用你编写的类时，减少需要明白的内容。这种隔离称为信息隐藏（information hiding）。

## 11.2 构造函数

声明实例变量后的下一步是定义构造函数（contructor）——初始化实例变量的特殊方法。构造函数的定义语法与其他方法类似，但：

- 构造函数与类同名；
- 构造函数没有返回类型（因此没有返回值）；
- 不使用关键字 static。

下面是 Time 类的一个构造函数：

```java
public Time() {
	this.hour = 0;
	this.minute = 0;
	this.second = 0.0;
}
```

这个构造函数不接受任何实参，其中的每行代码都将一个实例变量初始化为零（就这里而言，这意味着午夜）。

**this 是一个关键词，指向正在创建的对象。可像使用对象名一样使用this。**例如，可读写 this 的实例变量，将 this 作为实参传递给方法。然而，this 并不是你声明的，不能给它赋值。

编写构造函数时的常见错误是在末尾添加一条 return 语句。与 void方法一样，构造函数不返回值。

要想创建 Time 对象，必须使用运算符 new：

```java
Time time = new Time();
```

调用 new 时，Java 将创建指定的对象，并调用构造函数来初始化其实例变量。构造函数执行完毕后，new 将返回一个指向新对象的引用。在这个示例中，引用被赋给了类型为 Time 的变量 time，结果如图 11-1 所示。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230405142108572.png" alt="image-20230405142108572" style="zoom:50%;" /> 

​					图 **11-1**：**Time** 对象的状态图

初学者有时会犯这样的错误，即在构造函数中调用 new。不必这样做，也不能这样做。在这个示例中，在构造函数中调用 new Time() 将导致无限递归：

```java
public Time() {
	new Time(); // 不对！
	this.hour = 0;
	this.minute = 0;
	this.second = 0.0;
}
```

## 11.3 构造函数重载

与其他方法一样，构造函数也可重载，这意味着可提供形参不同的多个构造函数。Java 知道该调用哪个构造函数，这是根据你提供的实参确定的。

一种常见的做法是，**在提供一个不接受任何参数的构造函数（如前面的构造函数）的同时，提供一个“值构造函数”，**如下：

```java
public Time(int hour, int minute, double second) {
	this.hour = hour;
	this.minute = minute;
	this.second = second;
}
```

这个构造函数所做的只是将形参的值复制到实例变量中。在这个实例中，形参的名称和类型与实例变量相同，因此形参将遮盖（shadow）或者说隐藏实例变量。为将它们区分开来，关键词 this 必不可少。让形参与相应的实例变量同名是一种常见的做法，但并非必须这样。

要调用这个构造函数，必须在运算符 new 后面提供实参。下面的示例创建了一个 Time 对象，这个对象表示的时间为正午前 0.1 秒：

```java
Time time = new Time(11, 59, 59.9);
```

重载构造函数可提供这样的灵活性，即先创建对象再填充属性或在创建对象本身前收集所有的信息。

一旦掌握构造函数的编写技巧，你就会觉得这样的工作很乏味。只需看一眼实例变量列表就能快速编写出构造函数。事实上，有些 IDE 都能替你生成构造函数。

如果要在另一个类调用 Time 类方法的话，需要重写 `toString()` 方法。在Java中，当我们在类中打印对象的实例时，实际上是在调用该对象的toString()方法。如果没有重写该方法，则默认的toString()方法会返回一个字符串，其中包含该对象的类名和散列码。

如果你想打印出自定义类的对象时显示你指定的信息，你需要在该类中重写toString()方法。在这个方法中，你可以将所需的属性以特定的格式组合成一个字符串并返回。例如：

```java
public class Time {
    private int hour;
    private int minute;
    private int second;
	// constructor and other methods omitted for brevity

	@Override
	public String toString() {
    	return String.format("%02d:%02d:%02d", hour, minute, second);
	}
}
```
在上面的例子中，我们重写了toString()方法，使用String.format()方法将时、分、秒组合成一个格式化的字符串，并返回该字符串。

将前面的代码整合起来，得到如下完整的类定义：

```java
public class Time {
	private int hour;
	private int minute;
	private double second;
    
	public Time() {
		this.hour = 0;
		this.minute = 0;
		this.second = 0.0;
	}

	public Time(int hour, int minute, double second) {
		this.hour = hour;
		this.minute = minute;
		this.second = second;
	}
    
    	@Override
	public String toString() {
    	return String.format("%02d:%02d:%02d", hour, minute, second);
	}
}
```

在别的类调用该方法时，应这样编写：

```java
public class Work1 {
    public static void main(String[] args) {
        Time t = new Time();
        Time ti = new Time(10, 23, 41.6);
        System.out.println(t);
        System.out.println(ti);
    }
}
```

## 11.4 获取方法和设置方法

Time 类的实例变量是私有的，可在 Time 类中访问，但如果试图在其他类中访问它们，那么编译器将报错。

例如，下面是一个名为 TimeClient 的新类，之所以这样命名，是因为使用其他类定义的对象的类称为客户端（client）：

```java
public class TimeClient {
	public static void main(String[] args) {
		Time time = new Time(11, 59, 59.9);
		System.out.println(time.hour); // compiler error
	}
}
```

如果你尝试编译这些代码，将出现类似于下面这样的错误消息：`hour has private access in Time`（Time 类中的 hour 是私有的）。解决这种问题的办法有三种。

- 将实例变量 hour 声明为公有的。
- 在 Time 类中提供访问其实例变量的方法。
- 因为本来就要禁止其他类访问 Time 类的实例变量，所以这根本就不是问题。

第一种选择很有吸引力，因为它简单易行，但问题是如果类 A 直接访问类 B 的实例变量，那么类 A 将“依赖”于类 B。换而言之，每当你修改类 B 时，很可能也必须修改类 A。

如果类 A 只使用类 B 的方法来与类 B 交互，那么它们将是彼此“独立的”，这意味着修改类 B 不会影响类 A（只要类 A 使用的方法的特征标没有变化）。

因此，如果我们认为必须让 TimeClient 能够读取 Time 的实例变量，

可在 Time 中提供执行这种任务的方法：

```java
public int getHour() {
	return this.hour;
}
public int getMinute() {
	return this.minute;
}
public int getSecond() {
	return this.second;
}
```

这种方法的正规名称是“访问器”，但更常用的名称是获取方法（getter）。根据约定，获取实例变量 something 的方法将被命名为 getSomething。

如果我们认为还必须让 TimeClient 能够修改 Time 的实例变量，也可在 Time 中提供执行这种任务的方法：

```java
public void setHour(int hour) {
	this.hour = hour;
}
public void setMinute(int minute) {
	this.minute = minute;
}
public void setSecond(int second) {
	this.second = second;
}
```

这些方法的正规名称是“修改器”，但更常用的叫法是设置方法（setter）。设置方法的命名约定与获取方法类似：设置实例变量 something 的方法将被命名为 setSomething。

编写获取方法和设置方法的工作可能很繁琐，但很多 IDE 都能够根据实例变量生成这些方法。

## 11.5 显示对象

如果创建一个 Time 对象，并用 println 显示：

```java
public static void main(String[] args) {
	Time time = new Time(11, 59, 59.9);
	System.out.println(time);
}
```

输出将类似于下面这样：

```
Time@80cc7c0
```

当要求显示对象类型的值时，Java 显示类型名和对象的地址（十六进制表示）。如果需要跟踪各个对象，这种地址在调试中很有用。

要想以对用户更有意义的方式来显示 Time 对象，可编写一个显示小时、分钟和秒的方法。为此，可以 4.6 节中的方法 printTime 为基础，编写下面的方法：

```java
public static void printTime(Time t) {
	System.out.print(t.hour);
	System.out.print(":");
	System.out.println(t.minute);
	System.out.print(":");
	System.out.println(t.second);
}
```

如果用前一节的 time 对象来调用这个方法，输出将为 11:59:59.9。

为让这个方法的代码更简洁，可用 printf：

```java
public static void printTime(Time t) {
	System.out.printf("%02d:%02d:%04.1f\n",
		t.hour, t.minute, t.second);
}
```

需要提醒你的是，整数需要使用格式说明符 %d，浮点数需要使用格式说明符 %f。选项 02 表示总共两位，如果不够就在前面添加零；选项04.1 表示整数部分 4 位、小数部分 1 位，如果不够就在前面添加零。

## 11.6 方法toString

每种对象类型都有一个名为 **toString** 的方法，用于返回对象的字符串表示。用 print 或 println 显示对象时，Java 将调用其方法 toString。

这个方法默认显示对象的类型和地址，但可通过提供方法 toString 来覆盖（override）这种行为。例如，下面是 Time 的方法 toString：

```java
public String toString () {
	return String.format("%02d:%02d:%04.1f\n",
	this.hour, this.minute, this.second);
}
```

这个方法的定义没有包含关键字 static，因为它不是静态方法，而是实例方法（instance method）。为何叫实例方法呢？因为必须通过类（这里是 Time）的实例来调用。实例方法有时也被称为非静态方法，你可能在错误消息中见过这个术语。

这个方法的方法体与前一节的 printTime 类似，但有两个地方不同：

- 在这个方法中，我们使用了 this 来引用当前实例，即对其调用该方法的对象；
- 使用的不是 printf 而是 String.format；String.format 返回一个指定格式的字符串，而不是显示它。

现在可以直接调用 toString 了：

```java
Time time = new Time(11, 59, 59.9);
String s = time.toString();
```

还可通过 println 间接地调用它：

```java
System.out.println(time);
```

在这个示例中，toString 中的 this 与 time 指的是同一个对象。输出为 11:59:59.9 。

## 11.7 方法equals

前面介绍了两种检查两个值是否相等的方式：**运算符 == 和方法 equals**。这两种方式都可用于对象，但它们的含义不同。

- 运算符 == 检查两个对象是否相同（identical），即指的是否是同一个对象。
- 方法 equals 检查两个对象是否相等（equivalent），即它们的值是否相同。

相同的定义是固定不变的，因此运算符 == 所做的事情始终相同；但相等的定义随对象而异，因此对象可定义自己的方法 equals。请看下面的变量：

```java
Time time1 = new Time(9, 30, 0.0);
Time time2 = time1;
Time time3 = new Time(9, 30, 0.0);
```

图 11-2 所示的状态图显示了这些变量及其值。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230406100400238.png" alt="image-20230406100400238" style="zoom:50%;" /> 

图 **11-2**：显示三个 **Time** 变量的状态图

赋值运算符复制引用，因此 time1 和 time2 指向同一个对象。因为它们相同，所以 `time1 == time2` 为 true。

然而，time1 和 time3 指向不同的对象。因为它们不同，所以 `time1 == time3` 为 false。

默认情况下，方法 equals 的行为与 == 相同。就 Time 对象而言，这可能不是我们所希望的。例如，time1 和 time3 表示的时间相同，因此，应将它们视为相等。

我们可提供一个实现这种相等定义的 equals 方法：

```java
public boolean equals(Time that) {
	return this.hour == that.hour
	&& this.minute == that.minute
	&& this.second == that.second;
}
```

equals 是一个实例方法，因此，它使用 this 来引用当前对象，且其定义中没有包含关键词 static。我们可以像下面这样来调用这个 equals 方法：

```java
time1.equals(time3);
```

在这个 equals 方法中，this 指的是对象 time1，而 that 指的是对象time3。因为这两个对象的实例变量相等，所以结果为 true。很多对象采用了类似的相等定义，即如果两个对象的实例变量相等，那么这两个对象就相等。然而，也可用其他的方式定义相等。

## 11.8 时间相加

假设你要去看电影，影片开始放映的时间为 18:50（6:50PM），时长为2 小时 16 分钟，请问影片将在什么时候结束？

我们用 Time 对象来执行这种计算。可采取下面两种方式将 Time 对象“相加”：

- 编写一个将两个 Time 对象作为参数的静态方法；
- 编写一个通过 Time 对象进行调用，并将一个 Time 对象作为参数的实例方法。

为说明差别，我们将演示这两种方式。静态方法的代码类似于下面这样：

```java
public static Time add(Time t1, Time t2) {
	Time sum = new Time();
	sum.hour = t1.hour + t2.hour;
	sum.minute = t1.minute + t2.minute;
	sum.second = t1.second + t2.second;
	return sum;
}
```

下面的代码演示了如何调用这个静态方法：

```java
Time startTime = new Time(18, 50, 0.0);
Time runningTime = new Time(2, 16, 0.0);
Time endTime = Time.add(startTime, runningTime);
```

另一方面，实例方法的代码类似于下面这样：

```java
public Time add(Time t2) {
	Time sum = new Time();
	sum.hour = this.hour + t2.hour;
	sum.minute = this.minute + t2.minute;
	sum.second = this.second + t2.second;
	return sum;
}
```

所做的修改如下：

- 删除了关键词 static。
- 删除了第一个形参。
- 将 t1 替换成了 this。

还可以将 t2 替换为 that。不同于 this，that 并非关键词，而只是一个比 t2 更合适的变量名。

下面的代码演示了如何调用这个实例方法：

```java
Time endTime = startTime.add(runningTime);
```

这就是将时间相加的静态方法和实例方法。静态方法和实例方法的功能相同，要想在它们之间转换，只需要修改几个地方。

然而，还有一个问题，那就是执行加法的代码不正确。就这个示例而言，返回的结果为 20:66，这并非有效的时间。如果 second 超过了 59，那么就必须进位到 minute，而如果 minute 超过了 59，就必须进位到 hour。

下面是一个更佳的 add 版本：

```java
public Time add(Time t2) {
	Time sum = new Time();
	sum.hour = this.hour + t2.hour;
	sum.minute = this.minute + t2.minute;
	sum.second = this.second + t2.second;
	if (sum.second >= 60.0) {
		sum.second -= 60.0;
		sum.minute += 1;
	}
	if (sum.minute >= 60) {
		sum.minute -= 60;
		sum.hour += 1;
	}
	return sum;
}
```

然而，hour 也可能超过 23，但 Time 类没有属性 days，因此无法进位。在 hour 超过 23 时，可用 sum.hour -= 24 来获得正确的结果。

1-8示例代码：

```java
package Chapter11;
// Time类
public class Time {
	// 定义实例变量
    private int hour;
    private int minute;
    private double second;
	// 无参构造方法
    public Time() {
        this.hour = 0;
        this.minute = 0;
        this.second = 0.0;
    }
	// 有参构造方法
    public Time (int hour, int minute, double second) {
        this.hour = hour;
        this.minute = minute;
        this.second = second;
    }
	// 定义 toString
    @Override
    public String toString () {
        return String.format("%02d:%02d:%04.1f", hour, minute, second);
    }
	// 定义访问器，用于获取 Time 类中的实例变量值
    public int getHour () {
        return this.hour;
    }
    public int getMinute () {
        return this.minute;
    }
    public double getSecond () {
        return this.second;
    }
	// 定义修改器，用于设置 Time 类中的实例变量值
    public void setHour(int hour) {
        this.hour = hour;
    }
    public void setMinute(int minute) {
        this.minute = minute;
    }
    public void setSecond(double second) {
        this.second = second;
    }
	// 定义时间加法，用于将两个 Time 对象的时间值相加，并返回它们的和
    public Time add(Time that) {
        Time sum = new Time();
        sum.hour = this.hour + that.hour;
        sum.minute = this.minute + that.minute;
        sum.second = this.second + that.second;
        if (sum.second >= 60) {
            sum.second -= 60;
            sum.minute ++;
        }
        if (sum.minute >= 60) {
            sum.minute -= 60;
            sum.hour ++;
        }
        return sum;
    }

    public static void main (String[] args) {
//        Time t = new Time();
//        int hour = t.getHour();
//        System.out.println(hour);
    }
}

// TimeClient类
public class TimeClient {
// 
    public static void main (String[] args) {
        Time startTime = new Time();
        Time addTime = new Time();
        startTime.setHour(10);
        startTime.setMinute(23);
        startTime.setSecond(42.5);
        addTime.setHour(7);
        addTime.setMinute(36);
        addTime.setSecond(18.5);
        Time endTime = addTime.add(startTime);
        System.out.println(endTime);
    }
}

```

## 11.9 纯方法和非纯方法

前面的静态方法 add 没有修改任何形参，而是创建并返回了一个新的Time 对象。作为一种替代方案，可编写一个类似于下面这样的方法：

```java
public void increment(double seconds) {
	this.second += seconds;
	while (this.second >= 60.0) {
		this.second -= 60.0;
		this.minute += 1;
	}
	while (this.minute >= 60) {
		this.minute -= 60;
		this.hour += 1;
	}
}
```

方法 increment 直接修改当前的 Time 对象，而不是创建并返回一个新的 Time 对象。

像 add 那样的方法被称为纯方法（pure method），因为：

- 它们没有修改形参；
- 它们没有任何“副作用”，如打印；
- 它们的返回值完全取决于形参，而不受任何其他状态的影响。

方法 increment 违反了第一条规则，像它这样的方法有时被称为非纯方法（modifier）。非纯方法通常是 void 方法，但有些也返回一个引用，用于指向它们修改的对象。

因为非纯方法不创建对象，所以效率可能更高，但也更容易出错。如果对象被多个变量指向，可能难以搞清楚非纯方法带来的影响。

要想让类像 String 那样不可修改，可以只提供获取方法，而不提供设置方法，同时只提供纯方法，而不提供非纯方法。不可修改的对象看似用起来更麻烦，但可节省大量的调试时间。

示例代码:

```java
package Chapter11;

public class Time {

    private int hour;
    private int minute;
    private double second;
	
    public Time (int hour, int minute, double second) {
        this.hour = hour;
        this.minute = minute;
        this.second = second;
    }
    
    // 单独增加秒数来增加时间（纯方法）
    public void increment (double seconds) {
        this.second += seconds;
        while (this.second >= 60) {
            this.second -= 60;
            this.minute ++;
        }
        while (this.minute >= 60) {
            this.minute -= 60;
            this.hour ++;
        }
    }

    public static void main (String[] args) {
        Time t = new Time(11, 42, 32);
        System.out.println(t);
        t.increment(33);
        System.out.println(t);
    }
}
```

## 11.10 方法

### private

`private` 是 Java 中的访问修饰符，用于控制类中的成员变量和方法的访问范围。使用 `private` 修饰的成员变量和方法只能在当前类中被访问，无法在类外部被直接访问。(11.1)

```java
public class MyClass {
    private int num;
	private void method() {
    // ...
	}
}
```
上述代码中，`num` 和 `method()` 都是被 `private` 修饰的。因此，它们只能在 `MyClass` 类中被访问，而无法在 `MyClass` 类的外部被直接访问。

### this

`this`是一个关键字，表示当前对象的引用。可以使用`this`来引用当前对象的成员变量、方法和构造函数。(11.2)

在一个对象的方法中，`this`可以用来引用该对象的成员变量，以区分方法中的局部变量和成员变量。例如：

```java
public class Person {
    private String name;
	public void setName(String name) {
    	this.name = name;
	}
}
```
在这个例子中，`this.name`引用了`Person`对象的成员变量`name`，而`name`则是`setName`方法的参数。

另外，`this`还可以用在构造函数中，用于调用同一个类的其他构造函数。例如：

```java
public class Person {
    	private String name;
	public Person() {
    	this("John Doe");
	}

	public Person(String name) {
    	this.name = name;
	}
}
```
在这个例子中，`Person()`构造函数调用了`Person(String name)`构造函数，以便在创建对象时设置`name`属性。使用`this`关键字调用同一个类的其他构造函数时，必须将`this`作为构造函数中的第一条语句。

总之，`this`关键字可以用于引用当前对象的成员变量、方法和构造函数，使得代码更加清晰易懂。

### toString

`toString()` 方法是一个预定义的 Java 方法，可用于将对象转换为字符串。在 Java 中，每个类都隐式继承自 `Object` 类，而 `Object` 类中就有 `toString()` 方法的定义。因此，如果您定义了一个类并且希望该类的实例可以以可读的方式输出，您可以重写 `toString()` 方法来定义输出格式。(11.3, 11.6)

默认情况下，`toString()` 方法将返回一个由类名、`@` 符号和对象的哈希码组成的字符串，例如：

```
Chapter11.Time@6a5fc7f7
```

但是，如果您重写 `toString()` 方法并返回一个自定义字符串，就可以在使用该对象的 `toString()` 方法时输出自定义字符串。例如：

```java
public class Time {    
    private int hour;    
    private int minute;     
    public Time(int hour, int minute) {        
        this.hour = hour;        
        this.minute = minute;    
    }     
    @Override    
    public String toString() {
        return String.format("%02d:%02d", hour, minute);
    }
}
public class Main {
    public static void main(String[] args) {
        Time time = new Time(8, 30);
        System.out.println(time); // Output: 08:30    
    } 
}
```

在上面的示例中，我们重写了 `Time` 类的 `toString()` 方法，并返回了一个包含小时和分钟的格式化字符串。接着，在 `main` 方法中创建一个 `Time` 对象并输出它。由于我们已经重写了 `toString()` 方法，所以输出的将是格式化的时间字符串而不是默认的类名和哈希码。

请注意，`toString()` 方法是非常常用的方法，在编写自定义类时，您应该考虑实现自定义的 `toString()` 方法，以便在需要时以更可读的方式输出类的实例。

### equals

方法 equals 检查两个对象是否相等（equivalent），即它们的值是否相同。(11.7)

而运算符 == 检查两个对象是否相同（identical），即指的是否是同一个对象。

我们可提供一个实现这种相等定义的 equals 方法：

```java
public boolean equals(Time that) {
	return this.hour == that.hour
	&& this.minute == that.minute
	&& this.second == that.second;
}
```

equals 是一个实例方法，因此，它使用 this 来引用当前对象，且其定义中没有包含关键词 static。我们可以像下面这样来调用这个 equals 方法：

```java
time1.equals(time3);
```

在这个 equals 方法中，this 指的是对象 time1，而 that 指的是对象time3。因为这两个对象的实例变量相等，所以结果为 true。很多对象采用了类似的相等定义，即如果两个对象的实例变量相等，那么这两个对象就相等。然而，也可用其他的方式定义相等。

## 11.10 术语表

| 术语     | 含义                                                         |
| -------- | ------------------------------------------------------------ |
| 类       | 在本书前面，我们将类定义为相关方法的集合。现在你应该知道类也是创建对象的模板。 |
| 实例     | 类的一员。每个对象都是某个类的实例。                         |
| 数据封装 | 将多个命名变量放在单个对象中。                               |
| 实例变量 | 对象的属性，即在类中定义的非静态变量。                       |
| 信息隐藏 | 将实例变量声明为私有的，以减少类之间的依赖关系。             |
| 构造函数 | 对新创建的对象的实例变量进行初始化的特殊方法。               |
| 遮盖     | 定义类型和名称与实例变量相同的局部变量或形参。               |
| 客户端   | 使用其他类定义的对象的类。                                   |
| 获取方法 | 返回实例变量的值的方法。                                     |
| 设置方法 | 给实例变量赋值的方法。                                       |
| 覆盖     | 替换方法（如 toString）的默认实现。                          |
| 实例方法 | 可访问 this 和实例变量的非静态方法。                         |
| 相同     | 两个一样的值；就对象变量而言，指的是它们指向同一个对象。     |
| 相等     | 在方法 equals 看来，两个对象是相等的，但不一定相同。         |
| 纯方法   | 结果只取决于形参，而不受其他数据影响的静态方法。             |
| 非纯方法 | 修改对象状态（实例变量）的方法。                             |

## 11.11 练习

### 第一题

本章中的 increment 方法的实现效率不太高，你能重写这个方法，使其不使用任何循环吗？提示：别忘了求模运算符。

### 第二题

在图版游戏 Scrabble 中，每个卡片都包含一个字母和一个分数，其中前者用于在行列上拼出单词，后者用于计算单词的价值。

(1) 请为表示卡片的 Tile 类编写定义。这个类应包含 char 实例变量 letter 和 int 实例变量 value。

(2) 编写一个构造函数，让它包含形参 letter 和 value，并初始化前述实例变量。

(3) 编写一个名为 printTile 的方法，它将一个 Tile 对象作为参数，并以方便阅读的格式显示该对象的实例变量。

(4) 编写一个名为 testTile 的方法，让它创建一个属性 letter 和 value 分别为 Z 和 10 的 Tile 对象，再用 printTile 来显示这个对象的状态。

(5) 为 Tile 类实现方法 toString 和 equals。

(6) 为每个属性创建获取方法和设置方法。

### 第三题

对象类型 Date 包含三个 int 实例变量：year、month 和 day，请为它编写类定义。这个类应提供两个构造函数，其中一个没有任何形参，并将实例变量初始化为默认值；另一个包含形参 year、month 和 day，并用它们来初始化实例变量。

编写一个 main 方法，让它创建一个表示你生日的 Date 对象——birthday。可用前述任何一个构造函数创建这个对象。

### 第四题

有理数是可表示为分数的数字。例如，2/3 就是一个有理数，数字 7 也是有理数，因为可将其视为 7/1。

(1) 定义一个名为 Rational 的类，让它包含两个 int 实例变量，分别用于存储分子和分母。

(2) 编写一个构造函数，让它不接受任何参数，并将分子和分母分别设置为 0 和 1。

(3) 编写一个名为 printRational 的实例方法，并以合理的格式显示 Rational 对象。

(4) 编写一个 main 方法，让它创建一个 Rational 对象、设置该对象的实例变量并显示该对象。

(5) 至此，你编写了一个最基本的程序，请对其进行测试，必要时进行调试。

(6) 为 Rational 类编写方法 toString，并用 println 对其进行测试。

(7) 再编写一个构造函数，让它包含两个形参，并用它们来初始化实例变量。

(8) 编写一个名为 negate 的实例方法，让它对有理数求负。这是一个非纯方法，因此也是 void 方法。在 main 中添加对这个方法进行测试的代码。

(9) 编写一个名为 invert 的实例方法，让它通过将分子和分母互换来计算倒数。这是一个非纯方法。在 main 中添加对这个方法进行测试的代码。

(10) 编写一个名为 toDouble 的实例方法，让它将有理数转换为 double 值（浮点数），并返回结果。这是一个纯方法，不修改对象。与前面一样，请对这个方法进行测试。

(11) 编写一个名为 reduce 的实例方法，让它将有理数化简为最简分数：找出分子和分母的最大公约数，并将分子和分母都除以这个公约数。这是一个纯方法，不修改当前对象的实例变量。

提示：找出最大公约数只需要几行代码。要了解这方面的更详细信息，请在网上搜索 Euclidean algorithm。

这个练习旨在让你编写包含各种方法的类定义：构造函数、静态方法、实例方法、非纯方法和纯方法。



### 第一题代码

原代码+改进部分：

```java
    public void increment (double seconds) {
        this.second += seconds;
        while (this.second >= 60) {
            this.second -= 60;
            this.minute ++;
        }
        while (this.minute >= 60) {
            this.minute -= 60;
            this.hour ++;
        }
    }
    // 上个方法的改进版，不需要循环
    public void incrementX (double seconds) {
        this.second += seconds;
        if (this.second >= 60) {
            int minuteAdd = (int)(this.second / 60);
            this.second = this.second % 60;
            this.minute += minuteAdd;
        }
        if (this.minute >= 60) {
            int hourAdd = this.minute / 60;
            this.minute = this.minute % 60;
            this.hour += hourAdd;
        }
    }
```

### 第二题代码

```java
package Chapter11;

public class Tile {
    // (1)为表示卡片的 Tile 类编写定义
    private char letter;
    private int value;
    // (2)编写一个构造函数，让它包含形参 letter 和 value，并初始化前述实例变量
    public Tile (char letter, int value) {
        this.letter = letter;
        this.value = value;
    }
    // (3)编写一个名为 printTile 的方法
    public void printTile (Tile tile) {
        System.out.println("letter : " + tile.letter);
        System.out.println("value  : " + tile.value);
    }
    // (4)编写一个名为 testTile 的方法
    public Tile testTile () {
        return new Tile('Z', 10);
    }
    // (5) 为 Tile 类实现方法 toString 和 equals。
    public String toString () {
        return String.format("letter : %c\nvalue : %d", letter, value);
    }
    public boolean equals (Tile tile) {
        boolean isEquals = false;
        if (this.letter == tile.letter && this.value == tile.value) {
            isEquals = true;
        }
        return isEquals;
    }
    // (6) 为每个属性创建获取方法和设置方法
    // 获取方法
    public char getLetter () {
        return this.letter;
    }
    public int getValue () {
        return this.value;
    }
    // 设置方法
    public void setLetter (char letter) {
        this.letter = letter;
    }
    public void setValue (int value) {
        this.value = value;
    }

    public void testTilePrint() {
        printTile(testTile());
    }

    public static void main (String[] args) {
        Tile tile = new Tile('Z',10);
        tile.printTile(tile.testTile());
        System.out.println(tile.equals(tile.testTile()));
    }
}
```

### 第三题代码

```java
package Chapter11;

public class Date {

    private int year;
    private int month;
    private int day;
    // 编写构造函数
    public Date() {
        this.year = 0;
        this.month = 0;
        this.day = 0;
    }
    private Date(int year, int month, int day) {
        this.year = year;
        this.month = month;
        this.day = day;
    }
    // 设置输出
    @Override
    public String toString() {
        return "Date{" +
                "year=" + year +
                ", month=" + month +
                ", day=" + day +
                '}';
    }
    // 创建获取和设置方法
    public int getYear() {
        return this.year;
    }
    public int getMonth() {
        return this.month;
    }
    public int getDay() {
        return this.day;
    }
    public void setYear(int year) {
        this.year = year;
    }
    public void setMonth(int month) {
        this.month = month;
    }
    public void setDay(int day) {
        this.day = day;
    }

    public static void main(String[] args) {
        Date date = new Date();
        date.setYear(2000);
        date.setMonth(9);
        date.setDay(22);
        System.out.println(date);

        Date date2 = new Date(2000,9,22);
        System.out.println(date2);
    }
}

```

### 第四题代码

```java
package Chapter11;

public class Rational {
    // (1)
    private int molecule;
    private int denominator;
    // (2)创建构造函数
    public Rational() {
        this.molecule = 0;
        this.denominator = 1;
    }
    // (7)创建带两个形参的构造函数
    public Rational(int molecule, int denominator) {
        this.molecule = molecule;
        this.denominator = denominator;
    }
    // 生成显示和设置方法
    public int getMolecule() {
        return molecule;
    }
    public void setMolecule(int molecule) {
        this.molecule = molecule;
    }
    public int getDenominator() {
        return denominator;
    }
    public void setDenominator(int denominator) {
        this.denominator = denominator;
    }
    // (3)以合理的格式显示 Rational对象
    public void printRational() {
        System.out.printf("%d/%d\n", this.molecule, this.denominator);
    }
    // (6)编写 toString
    @Override
    public String toString() {
        return "Rational{" +
                "molecule=" + molecule +
                ", denominator=" + denominator +
                '}';
    }
    // (8)编写名为 negate 的实例方法，让它对有理数求负，非纯
    public void negate() {
        this.setMolecule(-1 * this.getMolecule());
    }
    // (9)编写名为 invert 的实例方法，让它通过将分子和分母互换来计算倒数，非纯
    public void invert() {
        int value = getMolecule();
        this.setMolecule(this.getDenominator());
        this.setDenominator(value);
    }
    // (10)编写名为 toDouble 的实例方法，让它将有理数转换为 double 值，并返回结果。纯
    public double toDouble() {
        return (double) this.getMolecule() / this.getDenominator();
    }
    // (11)编写一个名为 reduce 的实例方法，让它将有理数化简为最简分数。纯
    public String reduce() {
        int gcd = gcd(this.getMolecule(), this.getDenominator());
        int molecule = this.getMolecule() / gcd;
        int denominator = this.getDenominator() / gcd;
        return molecule + "/" + denominator;
    }
    private int gcd(int a, int b) {
        if (b == 0) {
            return a;
        } else {
            return gcd(b, a % b);
        }
    }

    // (4)用 main方法创建并显示一个 Rational对象
    public static void main(String[] args) {
        Rational value = new Rational();
        value.setMolecule(4);
        value.setDenominator(8);
        value.printRational();
        System.out.println(value);
        value.negate();
        System.out.println(value);
        value.invert();
        System.out.println(value);
        System.out.println(value.toDouble());
        System.out.println(value.reduce());
    }

}
```



# 12 对象数组

## 12.1 Card对象

一副标准的扑克牌有 52 张，每张扑克牌都为 4 种花色（suit）和 13 个点数（rank）之一。四种花色为黑桃、红心、方块和梅花；13 个点数为 A、2、3、4、5、6、7、8、9、10、J、 Q 和 K。

如果要定义一个表示单张扑克牌的类，这个类显然应包含如下实例变量：rank 和 suit，但这些实例变量应为什么类型却不那么明显。一种选择是将它们的类型声明为 String，这样实例变量 suit 将包含"Spade" 这样的字符串，而 rank 将包含 "Queen" 这样的字符串。这种设计存在的一个问题是，比较两张扑克牌的点数或花色将不那么容易。

另一种设计方案是用整数将点数和花色进行编码（encode），这里的“编码”指的并非加密（转换为看不懂的内容），而是在数字序列和要表示的东西之间建立映射。

下面是为花色建立的一种映射：

梅花 → 0

方块 → 1

红心 → 2

黑桃 → 3

这里使用了数学符号 ，旨在明确地指出这些映射并非程序的组成部分。它们是程序设计的一部分，但不会出现在代码中。

花牌与数字的映射关系如下，其他扑克牌对应其点数表示的数字（2~10）：

A → 1

J → 11

Q → 12

K → 13

至此，Card 类的定义类似于下面这样：

```java
public class Card {
	private int rank;
	private int suit;
	public Card(int rank, int suit) {
		this.rank = rank;
		this.suit = suit;
	}
}
```

实例变量被声明为私有的：可以在这个类中访问，但不能在其他类中访问。

构造函数包含两个对应于实例变量的形参。可用运算符 new 创建 Card对象：

```java
Card threeOfClubs = new Card(3, 0);
```

结果为一个引用，指向表示梅花 3 的 Card 对象。

示例代码：

```java
package Chapter12;

public class Card {

    private int suit; // 花色，梅花 0,方块 1，红心 2，黑桃 3
    private int rank; // 点数 1-13 A~K
    private Card(int suit, int rank) {
        this.suit = suit;
        this.rank = rank;
    }
    @Override
    public String toString() {
        return "suit is " + suit + "\n" + "rank is " + rank;
    }
    public void printCard() {
        System.out.println("(" + suit + "," + rank + ")");
    }

    public static void main(String[] args) {
        Card card = new Card(2,11);
        System.out.println(card);
        card.printCard();
    }
}
```

## 12.2 方法toString

创建新类的第一步是声明实例变量和编写构造函数。接下来该干什么呢？一种不错的选择是编写方法 toString，这对调试和渐进开发大有帮助。

要想以易于阅读的方式显示 Card 对象，需要将整数编码映射到字符串。为此，一种比较自然的方式是使用一个 String 数组。我们可以像下面这样创建这个数组：

```java
String[] suits = new String[4];
```

然后给每个元素赋值：

```java
suits[0] = "Clubs";
suits[1] = "Diamonds";
suits[2] = "Hearts";
suits[3] = "Spades";
```

我们也可像 8.3 节那样，在创建数组的同时初始化元素：

```java
String[] suits = {"Clubs", "Diamonds", "Hearts", "Spades"};
```

图 12-1 所示的状态图显示了结果。每个元素都是一个指向 String 的引用。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230417130305254.png" alt="image-20230417130305254" style="zoom:50%;" /> 

图 **12-1**：一个字符串数组的状态图

我们还需要一个对点数进行解码的数组：

```java
String[] ranks = {null, "Ace", "2", "3", "4", "5", "6", "7", "8", "9", "10", "Jack", "Queen", "King"};
```

有效的点数为 1~13，因此根本不会用到索引为 0 的元素。我们将它设置为 null，表明这个元素不会被用到。

通过将实例变量 suit 和 rank 用作索引，可从这些数组中提取有意义的字符串。

```java
String s = ranks[card.rank] + " of " + suits[card.suit];
```

表达式 suits[card.suit] 表示将对象 card 的实例变量 suit 用作索引，以访问数组 suits 中的相应元素。

现在可以将这些代码封装到方法 toString 中了：

```java
public String toString() {
	String[] ranks = {null, "Ace", "2", "3", "4", "5", "6",
				"7", "8", "9", "10", "Jack", "Queen", "King"};
	String[] suits = {"Clubs", "Diamonds", "Hearts", "Spades"};
	String s = ranks[this.rank] + " of " + suits[this.suit];
	return s;
}
```

当我们显示 Card 对象时，println 将自动调用 toString：

```java
Card card = new Card(11, 1);
System.out.println(card);
```

输出为 Jack of Diamonds 。

示例代码：

```java
package Chapter12;

public class Card {

    private int suit; // 花色，梅花 0,方块 1，红心 2，黑桃 3
    private int rank; // 点数 1-13 A~K
    private Card(int suit, int rank) {
        this.suit = suit;
        this.rank = rank;
    }
    @Override
    public String toString() {
        String[] suits = {"Clubs", "Diamonds", "Hearts", "Spades"};
        String[] ranks = {null, "Ace", "2", "3", "4", "5", "6",
                    "7", "8", "9", "10", "Jack", "Queen", "King"};
        return ranks[this.rank] + " of " + suits[this.suit];
    }
    public void printCard() {
        System.out.println("(" + suit + "," + rank + ")");
    }

    public static void main(String[] args) {
        Card card = new Card(2,11);
        System.out.println(card);
//        card.printCard();
    }
}
```

## 12.3 类变量

到目前为止，你已经见过了局部变量和实例变量，其中局部变量是在方法中声明的，而实例变量是在类定义中声明的，通常位于类定义前面。

局部变量是在方法被调用时创建的，方法结束时，它们占据的内存空间将被收回。实例变量是在创建对象时创建的，在对象被作为垃圾收集时，它们占据的内存空间将被收回。

现在该介绍类变量（class variable）了。**与实例变量一样，类变量也是在类定义中声明的，但使用了关键词 static 对其进行标识。它们创建于程序开始运行（或所属类首次被使用）时，直到程序结束才消失。类变量由其所属类的所有实例共享**。

```java
public class Card {
	public static final String[] RANKS = {
		null, "Ace", "2", "3", "4", "5", "6", "7",
		"8", "9", "10", "Jack", "Queen", "King"};
	public static final String[] SUITS = {
		"Clubs", "Diamonds", "Hearts", "Spades"};
		// 这里为实例变量和构造函数
	public String toString() {
		return RANKS[this.rank] + " of " + SUITS[this.suit];
	}
}
```

类变量常用于存储多个地方要用到的常量值。在这种情况下，还应将它们声明为 final。请注意，决定将变量声明为 static 或 final 时，需要考虑两个不同的因素：如果变量由所有实例共享，那么就将其声明为static；如果变量为常量，就应将其声明为 final。

对于 static final 变量来说，一种常用的命名约定是**采用全大写**，这更容易让人知道它们在类中扮演的角色。在方法 toString 中，我们可以像引用局部变量一样引用 SUITS 和 RANKS，但要能够判断出它们是类变量。

将 SUITS 和 RANKS 定义为类变量的另一个优点是，无需在每次调用toString 时创建它们，也不需要在这个方法执行完毕后将它们视为垃圾进行收集。其他方法和类也可能需要它们，因此让它们在任何地方都可用很有帮助。由于这些数组变量是 final 的，且其元素指向的字符串是不可修改的，因此将它们声明为公有的不会有任何危险。

示例代码：

```java
package Chapter12;

public class Work1 {

    public static final String[] RANKS = {
            null, "Ace", "2", "3", "4", "5", "6", "7",
            "8", "9", "10", "Jack", "Queen", "King"};
    public static final String[] SUITS = {
            "Clubs", "Diamonds", "Hearts", "Spades"};
    private int rank;
    private int suit;
    public Work1(int rank, int suit) {
        this.rank = rank;
        this.suit = suit;
    }
    @Override
    public String toString() {
        return RANKS[this.rank] + " of " + SUITS[this.suit];
    }

    public static void main(String[] args) {
        Work1 card = new Work1(13,2);
        System.out.println(card);
    }
}
```

## 12.4 方法compareTo

正如你在 11.7 节中看到的，创建测试两个对象是否相等的方法 equals大有裨益。

```java
public boolean equals(Card that) {
	return this.rank == that.rank && this.suit == that.suit;
}
```

另外，如果有比较两张扑克牌的方法就好了，这样就能知道哪张牌更大。可用比较运算符（<、> 等）比较基本类型值，但这些运算符对对象类型不管用。

正如你在 9.6 节看到的，Java 类 String 提供了方法 compareTo。与方法 equals 一样，我们也可以为自定义类编写方法 compareTo 的定制版本。

有些类型是“完全有序的”，即可以通过比较判断出任何两个值的大小。整数和字符串都是完全有序的。

其他的类型是“无序的”，即无法以有意义的方式来规定哪个元素更大。在 Java 中，boolean 类型是无序的；如果你编写表达式 true < false，编译器将报错。

扑克牌是“部分有序的”，这意味着有些扑克牌能够比较，有些不能。例如，我们知道梅花 3 比梅花 2 大，方块 3 比梅花 3 大，但梅花 3 和方块 2 哪个更大呢？它们一个点数更大，另一个花色更大。

要想让扑克牌是可以比较的，必须指定哪个更重要：点数还是花色。如何选择没有定规，不同的游戏可能作出不同的选择。但刚买的扑克牌是有序的，开头全部是梅花，然后全部是方块，依次类推。因此，我们现在**暂时假设花色更重要**。

根据上述假设，可这样编写方法 compareTo：

```java
public int compareTo(Card that) {
	if (this.suit < that.suit) {
		return -1;
	}
	if (this.suit > that.suit) {
		return 1;
	}
	if (this.rank < that.rank) {
		return -1;
	}
	if (this.rank > that.rank) {
		return 1;
	}
	return 0;
}
```

如果 this 更大，compareTo 将返回 1；如果 that 更大，就返回 -1；如果两者相等，就返回 0。先比较花色，如果花色相同，再比较点数，如果点数也相同，就返回 0。

示例代码：

```java
package Chapter12;

public class Card2 {
    public static final String[] RANKS = {
            null, "Ace", "2", "3", "4", "5", "6", "7",
            "8", "9", "10", "Jack", "Queen", "King"};
    public static final String[] SUITS = {
            "Clubs", "Diamonds", "Hearts", "Spades"};
    private int rank;
    private int suit;
    public Card2(int rank, int suit) {
        this.rank = rank;
        this.suit = suit;
    }
    @Override
    public String toString() {
        return RANKS[this.rank] + " of " + SUITS[this.suit];
    }
    public int compareTo(Card2 card) {
        if (this.suit < card.suit) {
           return -1;
        }
        if (this.suit > card.suit) {
            return 1;
        }
        if (this.rank < card.rank) {
            return -1;
        }
        if (this.rank > card.rank) {
            return 1;
        }
        return 0;
    }

    public static void main(String[] args) {
        Card2 card1 = new Card2(13,1);
        Card2 card2 = new Card2(12,2);
        System.out.println(card1.compareTo(card2));
    }
}
```

## 12.5 Card对象是不可修改的

Card 的实例变量都是私有的，因此在其他类中无法访问。我们可提供获取方法，让其他类能够读取实例变量 rank 和 suit 的值：

```java
public int getRank() {
	return this.rank;
}
public int getSuit() {
	return this.suit;
}
```

是否提供设置方法属于设计方面的决策。如果我们提供了，Card 对象将是可修改的，因此可以将一张牌变成另一张牌。这可能不是我们所需要的功能，而且一般而言，可修改的对象更容易出错。因此，让 Card 对象不可修改可能是更好的选择。为此，只要不提供任何非纯方法（包括设置方法）就可以了。

这很容易，但并不牢靠，因为以后可能有人傻乎乎地添加非纯方法。**为防范这种情况，可将实例变量声明为 final 的：**

```java
public class Card {
	private final int rank;
	private final int suit;
	...
}
```

你依然可以在构造函数中给这些变量赋值，但如果有人编写试图修改这些变量的方法，编译器将报错。

## 12.6 Card数组

可创建 String 对象数组，同样，也可创建 Card 对象数组。下面的语句创建了一个数组，其中包含 52 个 Card 对象：

```java
Card[] cards = new Card[52];
```

图 12-2 是这个数组的状态图。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230417163847410.png" alt="image-20230417163847410" style="zoom: 67%;" /> 

图 **12-2**：一个未填充的 **Card** 数组的状态图

虽然我们称之为“Card 对象数组”，但这个数组包含的是指向 Card 对象的引用，而不是 Card 对象本身。这个数组的元素被初始化为 null，可像通常那样访问：

```java
if (cards[0] == null) {
	System.out.println("No card yet!");
}
```

然而，如果试图访问不存在的 Card 对象的实例变量，那么将引发 `NullPointerException` 异常。

```java
cards[0].rank // NullPointerException
```

用 Card 对象填充这个数组前，上述代码不可运行。编写嵌套 for 循环是填充数组的一种办法：

```java
int index = 0;
for (int suit = 0; suit <= 3; suit++) {
	for (int rank = 1; rank <= 13; rank++) {
		cards[index] = new Card(rank, suit);
		index++;
	}
}
```

外面的循环迭代花色（从 0~3）。对于每种花色，内部的循环迭代点数（从 1~13）。由于外面的循环运行 4 次，里面的循环运行 13 次，因此循环体被执行 52 次。

我们使用了一个独立变量来跟踪下一张牌应存储在数组的什么地方，图12-3 显示了创建开头两张牌后这个数组是什么样的。

<img src="C:\Users\YANGXIAOHAN\AppData\Roaming\Typora\typora-user-images\image-20230417163928351.png" alt="image-20230417163928351" style="zoom: 67%;" /> 

图 **12-3**：一个包含两张牌的 **Card** 数组的状态图

处理数组时，如果有一个显示其内容的方法将很方便。你已经见过很多次数组遍历模式，因此对下面的方法应该不会感到陌生：

```java
public static void printDeck(Card[] cards) {
	for (int i = 0; i < cards.length; i++) {
		System.out.println(cards[i]);
	}
}
```

由于变量 cards 的类型为 `Card[]`，因此其元素的类型为 `Card`，所以 `println` 将调用 Card 类的方法 `toString`。上述方法的效果与调用 `System.out.println(Arrays.toString(cards))` 类似。

示例代码：

```java
package Chapter12;

public class Card3 {

    public static final String[] RANKS = {
            null, "Ace", "2", "3", "4", "5", "6", "7",
            "8", "9", "10", "Jack", "Queen", "King"};
    public static final String[] SUITS = {
            "Clubs", "Diamonds", "Hearts", "Spades"};
    private int rank;
    private int suit;
    public Card3() {
        this.rank = 1;
        this.suit = 0;
    }
    public Card3(int rank, int suit) {
        this.rank = rank;
        this.suit = suit;
    }
    @Override
    public String toString() {
        return RANKS[this.rank] + " of " + SUITS[this.suit];
    }
    // 创建 52张牌的数组
    public static Card3[] cards() {
        Card3[] cards = new Card3[52];
        int index = 0;
        for (int suit = 0; suit <= 3; suit++) {
            for (int rank = 1; rank <=13; rank++) {
                cards[index] = new Card3(rank, suit);
                index++;
            }
        }
        return cards;
    }
    
    public static void main(String[] args) {
        Card3[] deck = cards();
        // 遍历数组
        for (int i = 0; i < deck.length; i++) {
            System.out.println(deck[i]);
        }

    }
}
```

## 12.7 顺序查找

接下来要编写的方法是 search，它接受两个参数——一个 Card 数组和一个 Card 对象，并返回 Card 对象在 Card 数组中的位置。如果Card 对象没有出现在 Card 数组中，则返回-1。下面这个版本的search 方法使用了 8.6 节中的算法——顺序查找（sequential search）：

```java
public static int search(Card[] cards, Card target) {
	for (int i = 0; i < cards.length; i++) {
		if (cards[i].equals(target)) {
			return i;
		}
	}
	return -1;
}
```

这个方法发现指定的 Card 对象后立即返回，这意味着如果中途找到了目标，就不必遍历整个数组。如果未中途退出循环，就说明指定的Card 对象不在数组中。注意，这个算法依赖于方法 equals。

如果数组中的 Card 对象未经排序，那么就无法以比顺序查找更快的速度进行查找，而必须检查每个 Card 对象，因为不这样做就无法确定要找的 Card 对象在不在数组中。然而，如果这些 Card 对象是按顺序排列的，就可使用更好的算法。

如何对数组排序将在下一章中介绍。将数组排序后，查找元素将容易得多。顺序查找的效率极低，数组非常大时尤其如此。

示例代码：

```java
package Chapter12;

import java.util.Objects;

public class Card3 {

    public static final String[] RANKS = {
            null, "Ace", "2", "3", "4", "5", "6", "7",
            "8", "9", "10", "Jack", "Queen", "King"};
    public static final String[] SUITS = {
            "Clubs", "Diamonds", "Hearts", "Spades"};
    private int rank;
    private int suit;
    public Card3() {
        this.rank = 1;
        this.suit = 0;
    }
    public Card3(int rank, int suit) {
        this.rank = rank;
        this.suit = suit;
    }
    @Override
    public String toString() {
        return RANKS[this.rank] + " of " + SUITS[this.suit];
    }
    // 创建 52张牌的数组
    public static Card3[] cards() {
        Card3[] cards = new Card3[52];
        int index = 0;
        for (int suit = 0; suit <= 3; suit++) {
            for (int rank = 1; rank <=13; rank++) {
                cards[index] = new Card3(rank, suit);
                index++;
            }
        }
        return cards;
    }
    // 生成 equals和 hashCode进行对比
    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Card3 card3 = (Card3) o;
        return rank == card3.rank && suit == card3.suit;
    }
    @Override
    public int hashCode() {
        return Objects.hash(rank, suit);
    }
    // 查找指定 Card对象
    public static int search(Card3[] deck, Card3 card) {
        for (int i = 0; i < deck.length; i++) {
            if (deck[i].equals(card)) {
                return i;
            }
        }
        return -1;
    }

    public static void main(String[] args) {
        Card3[] deck = cards();
        Card3 card = new Card3(1, 1);
        // 遍历数组
//        for (int i = 0; i < deck.length; i++) {
//            System.out.println(deck[i]);
//        }
        System.out.println(search(deck, card));
    }
}
```

## 12.8 二分法查找

在字典中查找单词时，你不会从头到尾地逐页查找。由于单词是按字母顺序排列的，因此你很可能用二分法查找（binary search）算法。

(1) 从字典中间附近的某页开始。

(2) 将要查找的单词与该页的某个单词比较。如果找到，则就此结束。

(3) 如果这个单词排在要查找的单词前面，就往后翻并回到第 2 步。

(4) 如果该页的单词排在要查找的单词后面，就往前翻并回到第 2 步。

如果你在某页找到两个相邻的单词，即要查找的单词应排在它们之间，那么你就知道这本字典没有你要找的单词。

对于前面的 Card 对象数组，如果其中的 Card 对象是按顺序排列的，我们就可编写一个速度更快的 search 版本：

```java
public static int binarySearch(Card[] cards, Card target) {
	int low = 0;
	int high = cards.length - 1;
	while (low <= high) {
		int mid = (low + high) / 2; // 第1步
		int comp = cards[mid].compareTo(target);
		if (comp == 0) { // 第2步
			return mid;
		} else if (comp < 0) { // 第3步
			low = mid + 1;
		} else { // 第4步
			high = mid - 1;
		}
	}
	return -1;
}
```

我们首先声明了变量 low 和 high，用于表示要搜索的范围。一开始，我们搜索整个数组，从 0 到 length - 1。

在 while 循环中，我们重复二分法查找的 4 个步骤：

(1) 选择一个位于 low 和 high 之间的索引（mid），并将该索引处的Card 对象同目标进行比较。

(2) 如果找到目标，就返回这个索引。

(3) 如果 mid 处的 Card 对象比目标小，就在范围 mid + 1 到 high 中搜索。

(4) 如果 mid 处的 Card 对象比目标大，就在范围 low 到 mid - 1 中搜索。

如果 low 大于 high，那么就意味着这个范围内没有任何 Card 对象，因此退出循环并返回-1。注意，这个算法依赖于对象的方法 compareTo。

示例代码：

```java
package Chapter12;

import java.util.Objects;

public class Card3 {

    public static final String[] RANKS = {
            null, "Ace", "2", "3", "4", "5", "6", "7",
            "8", "9", "10", "Jack", "Queen", "King"};
    public static final String[] SUITS = {
            "Clubs", "Diamonds", "Hearts", "Spades"};
    private int rank;
    private int suit;
    public Card3() {
        this.rank = 1;
        this.suit = 0;
    }
    public Card3(int rank, int suit) {
        this.rank = rank;
        this.suit = suit;
    }
    @Override
    public String toString() {
        return RANKS[this.rank] + " of " + SUITS[this.suit];
    }
    // 创建 52张牌的数组
    public static Card3[] cards() {
        Card3[] cards = new Card3[52];
        int index = 0;
        for (int suit = 0; suit <= 3; suit++) {
            for (int rank = 1; rank <=13; rank++) {
                cards[index] = new Card3(rank, suit);
                index++;
            }
        }
        return cards;
    }
    // 生成 equals和 hashCode进行对比
    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Card3 card3 = (Card3) o;
        return rank == card3.rank && suit == card3.suit;
    }
    @Override
    public int hashCode() {
        return Objects.hash(rank, suit);
    }
    // 查找指定 Card对象
    public static int search(Card3[] deck, Card3 card) {
        for (int i = 0; i < deck.length; i++) {
            if (deck[i].equals(card)) {
                return i;
            }
        }
        return -1;
    }

    public int compareTo(Card3 card) {
        if (this.suit < card.suit) {
            return -1;
        }
        if (this.suit > card.suit) {
            return 1;
        }
        if (this.rank < card.rank) {
            return -1;
        }
        if (this.rank > card.rank) {
            return 1;
        }
        return 0;
    }
    public static int binarySearch(Card3[] deck, Card3 card) {
        int low = 0;
        int high = deck.length - 1;
        while (low <= high) {
            int mid = (low + high) / 2;
            int comp = deck[mid].compareTo(card);
            if (comp == 0) {
                return mid;
            } else if (comp < 0) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
        return -1;
    }

    public static void main(String[] args) {
        Card3[] deck = cards();
        Card3 card = new Card3(1, 1);
        // 遍历数组
//        for (int i = 0; i < deck.length; i++) {
//            System.out.println(deck[i]);
//        }
//        System.out.println(search(deck, card));
        System.out.println(binarySearch(deck,card));
    }
}
```

## 12.9 跟踪代码

为了搞明白二分法查找的工作原理，在循环开头添加如下打印语句大有帮助：

```java
System.out.println(low + ", " + high);
```

如果像下面这样调用 binarySearch：

```java
Card card = new Card(11, 0);
System.out.println(binarySearch(cards, card));
```

且要查找的 Card 对象位于索引 10 处，则输出如下：

```
0, 51
0, 24
0, 11
6, 11
9, 11
10
```

如果要查找的 Card 对象（如 new Card(15, 1)，即方块 15）不在数组

中，输出将如下：

```
0, 51
26, 51
26, 37
26, 30
26, 27
-1
```

每执行一次循环，low 和 high 之间的距离都将减半。因此，经过 *k* 次迭代后，余下的 Card 对象数为 52/2k。要确定多少次迭代后查找才会结束，可求解方程 52/2*k*=1。结果为 log252，即大约 5.7。因此，可能只需要查看 5 或 6 个 Card 对象，而不需要像顺序查找那样查看全部的 52个 Card 对象。

推而广之，如果数组包含 *n* 个元素，则二分法查找需要作 log2n 次比较，而顺序查找需要作 *n* 次比较。*n* 很大时，二分法查找的速度要快得多。

## 12.10 递归版本

也可以用递归方法实现二分法查找。为此可编写一个将 low 和 high 作为参数的方法，并将第 3 步和第 4 步转换为递归调用。代码类似于下面这样：

```java
public static int binarySearch(Card[] cards, Card target,
	int low, int high) {
	if (high < low) {
		return -1;
	}
	int mid = (low + high) / 2; // 第1步
	int comp = cards[mid].compareTo(target);
	if (comp == 0) { // 第2步
		return mid;
	} else if (comp < 0) { // 第3步
		return binarySearch(cards, target, mid + 1, high);
	} else { // 第4步
		return binarySearch(cards, target, low, mid - 1);
	}
}
```

这里没有用 while 循环，而是用了一条 if 语句来终止递归。如果high 小于 low，它们之间就不可能有 Card 对象，因此指定的 Card 对象肯定不在数组中。

编写递归程序时的两种常见错误是：忘记包含基线条件；编写的递归调用导致基线条件根本不可能满足。这两种错误都会导致无限递归，进而引发 `StackOverflowException` 异常。

示例代码：

```java
package Chapter12;

import java.util.Objects;

public class Card3 {

    public static final String[] RANKS = {
            null, "Ace", "2", "3", "4", "5", "6", "7",
            "8", "9", "10", "Jack", "Queen", "King"};
    public static final String[] SUITS = {
            "Clubs", "Diamonds", "Hearts", "Spades"};
    private int rank;
    private int suit;
    public Card3() {
        this.rank = 1;
        this.suit = 0;
    }
    public Card3(int rank, int suit) {
        this.rank = rank;
        this.suit = suit;
    }
    @Override
    public String toString() {
        return RANKS[this.rank] + " of " + SUITS[this.suit];
    }
    // 创建 52张牌的数组
    public static Card3[] cards() {
        Card3[] cards = new Card3[52];
        int index = 0;
        for (int suit = 0; suit <= 3; suit++) {
            for (int rank = 1; rank <=13; rank++) {
                cards[index] = new Card3(rank, suit);
                index++;
            }
        }
        return cards;
    }
    // 生成 equals和 hashCode进行对比
    @Override
    public boolean equals(Object o) {
        if (this == o) return true;
        if (o == null || getClass() != o.getClass()) return false;
        Card3 card3 = (Card3) o;
        return rank == card3.rank && suit == card3.suit;
    }
    @Override
    public int hashCode() {
        return Objects.hash(rank, suit);
    }
    // 查找指定 Card对象
    public static int search(Card3[] deck, Card3 card) {
        for (int i = 0; i < deck.length; i++) {
            if (deck[i].equals(card)) {
                return i;
            }
        }
        return -1;
    }

    public int compareTo(Card3 card) {
        if (this.suit < card.suit) {
            return -1;
        }
        if (this.suit > card.suit) {
            return 1;
        }
        if (this.rank < card.rank) {
            return -1;
        }
        if (this.rank > card.rank) {
            return 1;
        }
        return 0;
    }
    // 二分法查询
    public static int binarySearch(Card3[] deck, Card3 card) {
        int low = 0;
        int high = deck.length - 1;
        while (low <= high) {
//            System.out.println(low + " , " + high);
            int mid = (low + high) / 2;
            int comp = deck[mid].compareTo(card);
            if (comp == 0) {
                return mid;
            } else if (comp < 0) {
                low = mid + 1;
            } else {
                high = mid - 1;
            }
        }
        return -1;
    }
    // 递归二分法查询
    public static int binaryRecursionSearch(Card3[] deck, Card3 card, int low, int high) {
        if (high < low) {
            return -1;
        }
        int mid = (high + low) / 2;
        int comp = deck[mid].compareTo(card);
        if (comp == 0) {
            return mid;
        } else if (comp < 0) {
            return binaryRecursionSearch(deck, card, mid + 1, high);
        } else {
            return binaryRecursionSearch(deck, card, low, mid - 1);
        }
    }

    public static void main(String[] args) {
        Card3[] deck = cards();
        Card3 card = new Card3(1, 1);
        // 遍历数组
//        for (int i = 0; i < deck.length; i++) {
//            System.out.println(deck[i]);
//        }
//        System.out.println(search(deck, card));
//        System.out.println(binarySearch(deck,card));
        System.out.println(binaryRecursionSearch(deck,card,0,deck.length -1));
    }
}
```

## 12.11 方法

### toString

详看12.2

### compareTo

详见12.4

### final

`final` 是 Java 中的关键字，可以用于修饰类、方法和变量。(12.5)

- 当用 `final` 修饰类时，该类不能被继承，即该类为最终类，不能有子类。
- 当用 `final` 修饰方法时，该方法不能被子类重写，即该方法为最终方法，不能被覆盖。
- 当用 `final` 修饰变量时，该变量为常量，即不能再次赋值。在声明时必须初始化，或在构造方法中初始化。常量名通常使用全大写字母，多个单词间用下划线分隔。

```java
public class Card {
	private final int rank;
	private final int suit;
	...
}
```

## 12.12 术语表

| 术语       | 含义                                                         |
| ---------- | ------------------------------------------------------------ |
| 编码       | 在两组值之间建立映射，以便用其中的一组值来表示另一组值       |
| 类变量     | 类中被声明为 static 的变量；无论根据类创建了多少个对象，其类变量都只有一个副本 |
| 顺序查找   | 查找数组元素的一种算法。它逐个查找，直到找到目标值为止       |
| 二分法查找 | 查找有序数组的一种算法。它从中间元素开始，将该元素同目标进行比较，从而将余下的一半元素排除在外 |

## 12.12 练习

### 第一题

在有些扑克牌游戏中，A 指定的点数比 K 大。请修改方法 compareTo 以支持这种排序方式。









### 第一题代码

```java
package Chapter12;
// 练习1
public class Card4 {

    public static final String[] RANKS = {
            null, "Ace", "2", "3", "4", "5", "6", "7",
            "8", "9", "10", "Jack", "Queen", "King"};
    public static final String[] SUITS = {
            "Clubs", "Diamonds", "Hearts", "Spades"};
    private int suit;
    private int rank;
    // 构造函数
    public Card4() {
        this.suit = 0;
        this.rank = 1;
    }
    public Card4(int rank, int suit) {
        this.suit = suit;
        this.rank = rank;
    }
    // 输出
    @Override
    public String toString() {
        return RANKS[this.rank] + " of " + SUITS[this.suit];
    }
    // 比较
    public int compareTo(Card4 card) {
        if (this.rank == 1) {
            this.rank = 14;
        }
        if (card.rank == 1) {
            card.rank = 14;
        }
        if (this.suit < card.suit) {
            return -1;
        }
        if (this.suit > card.suit) {
            return 1;
        }
        if (this.rank < card.rank) {
            return -1;
        }
        if (this.rank > card.rank) {
            return 1;
        }
        return 0;
    }

    public static void main(String[] args) {
        Card4 card1 = new Card4(2,2);
        Card4 card2 = new Card4(1,2);
        System.out.println(card1.compareTo(card2));
    }
}
```













# 15 异常

## NullPointerException

NullPointerException是Java编程语言中的一个运行时异常。当程序试图在一个空对象上调用方法或访问它的属性时，就会抛出这个异常。在Java中，所有的对象都是由类创建的，如果程序试图在空对象上调用方法或访问属性，就会导致NullPointerException异常。这个异常通常是由程序员的错误导致的，因为程序员没有检查空引用，或者没有正确地初始化变量。

## java.lang.StackOverflowError

Exception in thread "main" java.lang.StackOverflowError

java.lang.StackOverflowError 是Java程序中的一个异常，它表示递归调用过程中的栈空间不足。在Java程序中，每一个方法调用都会在调用栈中占用一定的空间，当递归调用的层数过多或者方法内部死循环，导致栈空间不足时，就会抛出 `java.lang.StackOverflowError` 异常。

要解决 `java.lang.StackOverflowError` 异常，可以采取以下几个方法：

1. 检查代码中的递归调用是否有终止条件，确保递归能够正常结束。
2. 增大JVM的栈空间大小，可以通过 `-Xss` 参数来指定JVM栈的大小。例如：`java -Xss1024k YourClass`。
3. 将递归转换为非递归方式，避免使用递归调用。

## ArrayIndexOutOfBoundsException

Exception in thread "main" java.lang.ArrayIndexOutOfBoundsException

ArrayIndexOutOfBoundsException 是 Java 中的一个运行时异常，表示尝试访问一个超出数组索引范围的元素。通常发生在以下情况：

1. 索引小于 0。
2. 索引大于或等于数组长度。

要解决此异常，需要检查代码中访问数组的索引值是否超出了数组的边界。例如，如果您有一个长度为 n 的数组，则索引的有效范围为 0 到 n-1。如果尝试访问 n 或更高的索引，则会抛出 ArrayIndexOutOfBoundsException 异常。

## Chapter11.Time@6a5fc7f7

这种情况通常是由于没有正确地重写toString()方法导致的。

在Java中，当我们在类中打印对象的实例时，实际上是在调用该对象的toString()方法。如果没有重写该方法，则默认的toString()方法会返回一个字符串，其中包含该对象的类名和散列码。

如果你想打印出自定义类的对象时显示你指定的信息，你需要在该类中重写toString()方法。在这个方法中，你可以将所需的属性以特定的格式组合成一个字符串并返回。例如：

```java
package Chapter11;
public class Time {
    private int hour;
    private int minute;
    private int second;
	// constructor and other methods omitted for brevity

	@Override
	public String toString() {
    	return String.format("%02d:%02d:%02d", hour, minute, second);
	}
}
```
在上面的例子中，我们重写了toString()方法，使用String.format()方法将时、分、秒组合成一个格式化的字符串，并返回该字符串。

这样，当你在其他类中使用该类的对象并调用其toString()方法时，将会按照你指定的格式显示时间信息，而不是默认的类名和散列码。

如果你已经重写了toString()方法，但仍然显示乱码，请确保编码方式一致。例如，如果你在使用IDE编写代码时使用UTF-8编码，但在命令行窗口中执行时使用的是默认的GBK编码，就可能会出现乱码。在这种情况下，你需要在命令行中指定正确的编码方式，或者将IDE的编码方式设置为与命令行相同。

## hour has private access in Time

"hour has private access in Time" 是一个编译错误信息，通常会在使用面向对象编程时出现。在这个错误信息中，“hour”指的是“Time”类中的一个私有成员变量，“private access”表示这个成员变量是私有的，无法从类的外部访问。这个错误信息的意思是在类的外部，试图直接访问“hour”成员变量，但是由于它是私有的，因此无法访问。要解决这个问题，可以通过类的公共接口访问该私有成员变量，或者将它改为公共成员变量。

## ava: 不兼容的类型: 从int转换到char可能会有损失

这个错误是因为你试图将 `int` 类型的值赋值给 `char` 类型的变量，可能导致精度损失。需要注意的是，将大范围的数据类型转换为小范围的数据类型时，可能会丢失数据。

如果你想强制将 `int` 转换为 `char` 类型，可以使用强制类型转换符 `(char)`，例如：

```java
int num = 65; 
char c = (char) num;
```

但需要注意，在进行类型转换时要确保不会丢失关键数据。

## missing return statement

missing return statement是指在一个方法中缺少了return语句，这可能会导致程序无法正常编译或出现逻辑错误。例如，在一个返回值类型为int的方法中，如果没有在所有可能的执行路径上都添加return语句，则编译器会提示missing return statement错误。这是因为编译器无法确定在该方法的所有执行路径上是否会有返回值。在解决这个错误时，需要确保在方法的所有执行路径上都有正确的返回值。

## method printTwice in class Test cannot be applied to given types;

这个错误通常出现在调用一个函数时提供的参数类型与函数定义中参数类型不匹配时。这可能是因为函数参数数量、类型或顺序不正确，导致编译器无法找到匹配的函数。请检查函数的定义和调用，确保它们的参数类型和数量匹配。如果问题仍然存在，请检查是否有其他函数名称或参数错误。

## cannot find symbol symbol: method pow(double,double)

这个错误提示意味着你在代码中调用了一个不存在的方法 `pow`。可能是因为你没有正确导入所需的类或库，或者是因为你错误地拼写了方法名。

通常情况下，Java 中计算幂的方法名是 `Math.pow`，如果你想使用这个方法，你需要在代码中导入 `java.lang.Math` 类，或者使用完整的方法名 `java.lang.Math.pow`。如果你使用了其他类库提供的幂计算方法，则需要导入对应的类或库，并确保方法名正确无误。

## Bad types in assignment: fromdouble to int

这个错误通常是因为将一个 `double` 类型的值直接赋值给一个 `int` 类型的变量，需要进行强制类型转换才能编译通过。例如：

```java
double d = 3.14;
int i = (int) d; // 进行强制类型转换
```

在上面的例子中，`d` 是 `double` 类型，而 `i` 是 `int` 类型。因为 `double` 类型的范围比 `int` 大，所以需要使用强制类型转换将 `d` 转换为 `int` 类型，否则会出现 "Bad types in assignment: from double to int" 的错误提示。

## reached end of file while parsing

"reached end of file while parsing"是Java编译器报出的错误之一，意思是在解析代码时到达了文件末尾，但是代码还没有完成。这通常是由于缺少括号、分号、花括号等基本的语法错误导致的。通常需要检查代码是否完整，括号是否匹配，语法是否正确等。

## NullPointerException

NullPointerException是Java中的一种运行时异常，表示尝试使用一个空引用的对象。当一个对象为null，但在代码中假定该对象为非null时，就会抛出NullPointerException异常。常见的原因包括：

1. 变量未初始化或赋值为null
2. 调用了未初始化或未赋值的对象的方法
3. 对于数组，访问了不存在的元素或者将数组赋值为null
4. 在多线程环境下，出现竞争条件导致对象被意外地置为null

要避免NullPointerException异常，应该在代码中对可能为空的对象进行判空处理，例如使用if语句或三目运算符进行判断。

## StackOverflowException 

`StackOverflowException`是Java虚拟机抛出的一种异常，表示方法调用堆栈发生了溢出。当一个方法调用另一个方法时，Java虚拟机会为被调用方法创建一个新的堆栈帧，并将其推入堆栈顶部。当这个新的堆栈帧又调用了另一个方法，Java虚拟机又会为新方法创建一个新的堆栈帧，依次类推。当堆栈的深度达到一定程度时，Java虚拟机将抛出`StackOverflowException`异常。

这个异常通常是由于程序中出现了无限递归调用的情况，导致方法调用堆栈无限增长，最终导致堆栈溢出。
