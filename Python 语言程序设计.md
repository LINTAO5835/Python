# python语言程序设计



## 1、进度计划表

[python语言程序设计](https://www.icourse163.org/shortUrl/parse/EjQzt)



## 2、概述





## 3、数据类型、运算符和表达式

### 3.1 标识符、常量和变量

#### 3.1.1标识符

标识符在程序中用来标识各种程序成分，命名程序中一些实体。包括三方面：

1、字母（a~z、A~Z）；2、数字（0~9）；3下划线：”_“



合法的标识符：x,	a1,	lin_tao,	num_1,	radius

不合法的标识符：first-name,	5sum

```python
#单独的下划线（_）用于表示上一次运算的的结果
>>>2*3
6
>>>_*10
60
```

（1）、见名思意：通过变量名就知道变量值的含义。

（2）、开头和结尾都是用下划线的情况应避免：_lintao_

（3）、不能和关键字重名，否则会出现语法错误。

```python
#Python中的33个关键字
>>>import keyword
>>>print(keyword.kwlist)
	['False', 'None', 'True', 'and', 'as', 'assert', 'async', 'await', 'break', 'class', 'continue', 'def', 'del', 'elif', 'else', 'except', 'finally', 'for', 'from', 'global', 'if', 'import', 'in', 'is', 'lambda', 'nonlocal', 'not', 'or', 'pass', 'raise', 'return', 'try', 'while', 'with', 'yield']
```

判断标识符是否为关键字可以用keyword.iskeyword(word)

```python
>>>keyword.iskeyword('int')
False
>>>keyword.iskeyword("and")
True
```



#### 3.1.2常量

在程序运行过程中，**其值不能改变的量**称为常量

（1）整型常量：-123、20

（2）实型常量：3.14、0.15、-2.0

（3）字符串常量：‘Python’、"Hello World !"

（4）布尔型常量：Ture、False

（5）复数型常量：3+2j



#### 3.1.3变量

变量是指在程序中执行过程中，**其值可以被改变**，既可以进行赋值运算的量

变量名必须是合法的标识符，不能是python的关键字

每个变量的单个基本要素：变量名  变量值  变量地址

```python
>>>x = 5  #创建了一个变量x，其值为5
```

***<u>与变量相关的内置函数</u>***

（1）type()函数		**用于返回变量的类型**

一般形式：type(变量名)

```python
>>>x = 5 #创建了整型变量x
>>>print(x)
5
>>>type(x)
<class 'int'>
>>>x = "Hello World !"#创建了字符串型变量X
>>>type(x)
<class 'str'>
>>>x = (1,2,3)#创建了元组类型变量x
>>>type(x)
<class 'tuple'>
```

（2）id()函数		**用于返回变量的地址**

一般形式：id(变量名)

```python
>>>str = "Hello World !"
>>>id(str)
2110376855408
```

（3）isinstance()函数		**用来判断一个对象是否为已知的类型**

一般形式：isinstance(对象，类型名)

```python
>>>a = 5
>>>isinstance(a,int)
True
>>>isinstance(a,str)
False
>>>isinstance(a,(int,float,str))
True
```



### 3.2基本数据类型

数据是程序设计要处理的对象和结果，是程序设计中所要涉及和描述的主要内容

数据类型：具有相同性质的数据对象集合

python中的基本数据类型有：**整型，实型，字符型，布尔型，复数类型**



#### 3.2.1 整型

整型数据即整数，不带小数点，可以有正号也可以有负号。

在python3.x中，整型数据在计算机内的表示没有长度限制，其值可以任意大。

```python
>>>a=1234567890123456789
>>>b=a*a
>>>b
1524157875323883675019051998750190521

```

python中整型常量可由二进制、八进制、十进制、十六进制表示。

**二进制整数**：以0b或0B为前缀，由0~1组成。

**八进制整数**：以0o或0O为前缀，其后由0~7的数字组成。

**十进制整数**：由0~9组成。

**十六进制整数**：以0x或0X开头，其后由0~9的数字和a~f字母和A~F字母组成。

在python是根据前缀来区分进制数的，在书写中要注意前缀。

```python
>>>0b1001  #二进制数
9
>>>0o456	#八进制数
302
>>>0x7a		#十六进制数
122
```



#### 3.2.2实型

实数又称为浮点数，一般有两种表示形式：

1、**十进制小数形式**：由数字和小数点组成（必须有小数）

例如：1.5、.25、0.2等，

浮点型数据允许小数点后没有任何数字，表示小数部分为0

例如：25.	表示25.0

2、**指数形式**：用科学计数法表示的浮点数，用字母e(E)表示以10为底的指数，e之前的为数字部分，之后的为指数部分。

**注意：e(E)前面必须要有数字，后面必须是整数**

例如：123.4e3 表示123.4 * 10^3

例如：e-5,1.2E-3.5,1e		都是错误的表示形式。



#### 3.2.3字符型

字符型数据可以使用一对单引号、双引号或者三引号。

```python
>>>"Let's go"
"Let's go"
>>>s = "'python'program"
>>>s
"'python'program"
```

转义字符：“\”开头的字符序列“

| 字符形式 | 含义                               |
| :------: | :--------------------------------- |
|    \n    | 回车换行，将当前位置移到下一行开头 |
|    \t    | 横向跳到下一制表符位置（Tab）      |
|    \b    | 退格，将当前位置退回到前一列       |
|    \r    | 回车，将当前位置移到当前行开头     |
|    \f    | 走纸换页，将当前位置移到下页开头   |
|    \\    | 反斜线符”\“                        |
|    \'    | 单引号符                           |
|    \"    | 双引号符                           |
|   \ddd   | 1~3位8进制数所代表的字符           |
|   \xhh   | 1~2位16进制数所代表的字符          |

```python
>>>a = 1
>>>b = 2
>>>c ="\101"
print("\t%d\n%d%s\n%d%d\t%s" % (a,b,c,a,b,c))
	1
2A
12	A
```



#### 3.2.4布尔类型

python的布尔类型有两个值：Ture和False,分别表示逻辑真和逻辑假。

```python
>>>type(True)
<class 'bool'>
>>>True == 1
True
>>>False == 0
True
```

布尔类型还可以与其他数据类型进行逻辑运算，

Python规定：**0、空字符串、None为False,其他数值和非空字符串为True。**

```python
>>>0 and False
0
>>>None or True
True
```



#### 3.2.5 复数类型

复数由两部分组成：实部和虚部

形式：实部+虚部j		j大小写都可以

复数类型可以进行加减乘除运算

可以用 .real 求出复数的实部，用 .imag 求出复数的虚部

```python
>>>x = 3+5j
>>>x.real
3.0
>>>x.imag
5.0
>>>y = 6-10j
>>>x + y
(9-5j)
```



### 3.3算术运算符和赋值运算符

#### 3.3.1算术运算符

| 运算符 |          说明          |
| :----: | :--------------------: |
|   +    | 加法运算符或正值运算符 |
|   -    | 减法运算符或负值运算符 |
|   *    |       乘法运算符       |
|   /    |       除法运算符       |
|   //   |      取整除运算符      |
|   **   |       求幂运算符       |
|   %    |       取模运算符       |

***运算符**有多重含义，具体含义取决于操作数的类型

数值型数据：表示乘法操作

序列类型：表示对内容进行重复

```python
>>>3*5
15
>>>'ab'*5
'ababababab'
```

**/运算符**

除法运算的两个操作数为整数，得到的结果为浮点数

除法运算的友谊个操作数为浮点数，得到的结果还为浮点数

```python
>>>1/2
0.5
>>>3/5
0.6
```

**//运算符**

参与运算的两个操作数都是整型，则结果为整型

参与运算的两个操作数有一个是浮点型，则结果为浮点型

```python
>>>3//5
0
>>>3.0//4
0.0
>>>12//5
2
>>>12//5.0
2.0
>>>-10//2
-5
>>>10//-2
-5
>>>10//-3.0		#向下取整
-4.0
```

**%运算符**

对整数和浮点数进行取模运算

```python
>>>5%3
2
>>>-5%3
1
>>>5%-3
-1
>>>10.5%2.1
2.0999999999999996
```

**求幂运算符**

```python
>>>2**3
8
>>>3**3
27
>>>4*3**3	#乘方运算符优先级大于乘法运算符
108

```



#### 3.3.2赋值运算符

赋值运算符用 ’ = ‘ 表示

作用将一个数据赋值给变量：变量  =  表达式

```python
>>>y = 2
>>>x = y + 2
>>>x
4
```

通过链式赋值将同一个值赋给多个变量

```python
>>>x = y = 5
>>>x
5
>>>y
5
```

多变量并行赋值

```python
>>>x,y,z = 2,5,8
>>>x
2
>>>y
5
>>>z
8

```

两个变量交换数值

```python
x,y = y,x
```

复合的赋值运算符

```python
+=、-=、*=、/=、//=、**=、%=、>>=、<<=、&=、|=、^=
```



### 3.4关系运算符和逻辑运算符

#### 3.4.1关系运算符

用于对两个操作数进行比较

关系运算符：>、>=、<、<=、==、!=

结合方向：至左向右

优先级别：>、>=、<、<=                ==、!=

关系表达式：

<表达式>关系运算符<表达式>

```python
>>>x,y,z = 2,5,8
>>>x>y
False
```

实数的比较---会出现误差

```python
>>>x = 123456
>>>y = -1111111
>>>z = 1.2345678
>>>a = x + y + z
>>>b = x +(y + z)
>>>a
-987653.7654322
>>>b
-987653.7654321999
>>>a == b
False
```

可通过绝对误差（或相对误差）的形式给出：

```python
>>>import math  #导入math库
>>>math.fabs(a-b)<0.00000001
True
```

关系运算符的连用

```python
<<<x = 5
<<<0 <= x <= 10
True
<<<0 <= x <= 2
False
```

注意符号的区分

" = "、" == "

```python
>>>a,b = 0,1
>>>if a==b:
    print("a equal to b")
>>>else:
    print("a not equal to b")    
a not equal to b

```



#### 3.4.2逻辑运算符

**and** **: 逻辑与**    当两边的运算量都为真时，整个逻辑表达式的值才是真，否则真个逻辑表达式的值就是假

**or : 逻辑或**   只要有一个运算量为真时，整个逻辑表达式的值就是真，否则真个逻辑表达式的值就是假

**not : 逻辑非** 当其右边的式子是真时，整个逻辑表达式的值就是假，否则真个逻辑表达式的值就是真



逻辑运算真值表

|  a   |  b   | not a | not b | a and b | a or b |
| :--: | :--: | :---: | :---: | :-----: | :----: |
|  真  |  真  |  假   |  假   |   真    |   真   |
|  真  |  假  |  假   |  真   |   假    |   真   |
|  假  |  真  |  真   |  假   |   假    |   真   |
|  假  |  假  |  真   |  真   |   假    |   假   |

优先级：逻辑非 > 逻辑与 > 逻辑或

**a and b**

如果a为真，继续计算b,表达式的结果为b的值
如果a为假，无需计算b,表达式的结果为a的值

```python
>>>True and 0
0
>>>False and 1
False
>>>True and 1 and 0
0
```

**a or b**

如果a为真，无需计算b,表达式的结果为a的值
如果a为假，继续计算b,表达式的结果为b的值

```python
>>>1 or 0
1
>>>False or 1
1
>>>False or 1 or 0
1
```

判断字符变量ch是否是数字字符？

```python
>>>ch ='3'
>>>ch >= '0' and ch <= '9'
True
```

判断字符变量ch是否是英文字母？

```python
>>>ch = 'b'
>>>(ch >= 'a' and ch <= 'z' ) or (ch >= 'A' and ch <= 'Z' )
True

```

判断整型变量x是否在0到100之间

```python
>>>x = 10
>>>x >= 0 and x <= 100
True
>>>0 <= x <=100
True
```



### 3.5成员运算符和同一性质运算符

#### 3.5.1成员运算符：

**in、not in**

判断一个元素是否在某一个序列中，或者判断一个字符是否属于这个字符串等，运算结果仍是True或False

```python
>>>'a' in 'abcd'
True
>>>'ac' in 'abcd'
False
>>>3 not in [1,2,3,4]
False
```



#### 3.5.2同一性质运算符

同一性质运算符用于**测试两个变量是否指向同一个对象**，其运算结果是**逻辑值。**

| 运算符 |  含义  |
| :----: | :----: |
|   is   |  相同  |
| is not | 不相同 |

优先级：相同

结合性：左结合

**is**    用来检查用来运算的两个变量是否引用同一对象，如果相同返回True，不相同则返回False。

**is not **  则相反

```python
>>>x = y = 3
>>>z = 4
>>>x is y
True
>>>x is z
False
>>>x is not z
True

########

>>>id(x)
1273016484144
>>>id(y)
1273016484144
>>>id(z)
1273016484176
```

**is 与 == 的区别**

**==**  用来比较判断两个对象的值是否相等

**is**    比较判断的是对象间的唯一身份标识，也就是id是否相同





## 4、顺序结构程序设计

### 4.1算法及结构化程序设计

**算法是解决问题的一系列操作步骤的集合**，是设计思路的描述，是指令的有限序列。

**数据结构 + 算法 = 程序**

1、有穷性：有限步骤之内正常结束，不能形成无穷循环。

2、确定性：算法中的每一个步骤必须有确定的含义，无二义性。

3、可行性：原则上都能精确执行，操作可通过已实现基本运算执行有限次而完成。

4、有输入：有多个或0个输入。

5、有输出：至少有一个或多个输出

**算法的评价标准**

1、正确性

程序不含语法错误，对于几组输入数据能够满足规格说明要求的结果，对于精心选择的典型、苛刻而带有刁难性的几组输入数据能够得出满足规格说明要求的结果，对于一切合法的输入数据都能够产生满足规格说明要求的结果。

2、可读性

3、鲁棒性（健壮性）

4、高效率与低存储量需求





描述方法：自然语言，数学语言，某种计算机语言描述

规范的方法：**流程图，N-S结构流程图，伪代码**



结构化程序设计思想采用模块分解与功能抽象和自顶向下、分而治之的方法，解决人脑思维能力的局限性和所处理问题的复杂性之间的矛盾，从而便于开发和维护，减少程序的出错概率和提高软件开发效率。

**原则：自顶向下、模块化**



### 4.2程序基本结构

从程序流程控制的角度来看，程序结构可以分为三种基本结构：**顺序结构，选择结构，循环结构**。

**任何结构化程序均可以有“顺序”、”选择“和”循环''这三种基本结构通过有限次的组合与嵌套来描述**



**顺序结构**：由一系列顺序执行的操作组成，是一种线性结构

**选择结构**：是根据一定的条件选择下一步要执行的操作

**循环结构**：根据一定的条件重复执行一个操作集合



### 4.3标准输入输出

一般一个程序分为三步进行：输入原始数据、进行计算处理和运算结果。



#### 4.3.1标准输入 input （）

​	一般格式：

​					input（[提示字符串]）



在python3.x中，input（）函数接受任意输入，将所有输入默认为字符串处理。

```python
>>>x = input("Please enter your input:")
Please enter your input:5
>>>print(type(x))
<class 'str'>

>>>x = input("Please enter your input:")
Please enter your input:(1,2,3)
>>>print(type(x))
<class 'str'>

```

如果要输入数值类型数据，可以使用类型准换函数将字符串转换为数值。

```python
>>>x = int(input("Please enter your input:"))
Please enter your input:5
>>>print(type(x))
<class 'int'>

```

input()函数可以给多个变量赋值

```python
>>>x,y = eval(input())
1,2
>>>print(x,y)
1 2

```

eval()函数

一般形式：

​			eval([字符串])

功能：将字符串str当成有效的表达式来求值并返回计算结果。

```python
>>>x=5
>>>eval('3*x')
15
>>>eval('print(x)')
5

```



#### 4.3.2标准输出 print（）函数

一般形式：

print（[输出1，输出2，·······，输出n] [sep=分隔符，end=结束符]）

print函数从左求出至右各输出项的值，并将各输出项依次显示在屏幕的同一行

```python
>>>x,y = 1,2
>>>print(x,y)
1 2
>>>print(x,y,sep=':',end='%')
1:2%
>>>print(x,y,sep='*',end='#')
1*2#
>>>print(x,y,sep='*',end=' #')
1*2 #

```

使用表达式输出

```python
>>>str = 'hello'
>>>str
'hello'

>>>x = 2 * 3
>>>x
6
```



### 4.4格式化输出

print（）函数可以按照指定的输出格式在屏幕上输出相应的数据信息。‘

基本做法：将输出项格式化，然后使用表达式的形式或print()函数输出。

1、字符串格式化%

一般形式：

格式控制字符串%（输出1，输出2，·········输出项n）

**常规字符**：包括可显示的字符和用转义字符表示的字符。

**格式控制符**：决定所对应的输出项的格式，以%开头的一个或多个字符。



```python
>>>print("sum=%o"%123)
sum=173
```



**常用格式说明符**



| 1    | d或i | 十进制格式           |
| ---- | ---- | -------------------- |
| 2    | o    | 八进制格式           |
| 3    | x或X | 十六进制格式         |
| 4    | c    | 一个字符格式         |
| 5    | s    | 字符串格式           |
| 6    | f    | 实数格式             |
| 7    | e或E | 指数格式             |
| 8    | g或G | e或f中较短的一种格式 |



**附加格式说明符**

一般形式： %[附加格式说明符]格式符



| 附加格式说明符 |                         格式说明                         |
| :------------: | :------------------------------------------------------: |
|       m        |        域宽，十进制整数，用以描述输出数据所占宽度        |
|       n        | 附加域宽，十进制整数，用于指定实型数据小数部分的输出位数 |
|       -        |             输出数据左对齐，默认时 为右对齐              |
|       +        |       输出正数时，以+号开头;输出负数时，以-号开头        |
|       #        |       作为o,x的前缀时，输出结果前面加上前导符0，0x       |

```python
>>>print("sum=%o"%123)
>>>sum=173
>>>print("s = %#x" % 123)
s = 0x7b
>>>print("s = %#o" % 123)
s = 0o173
s = 8.123
>>>print("%6.2f" % s)
  8.12
>>>print("%06.2f" % s)
008.12
>>>print("%-04x%2d" % (10,100))
a   100
```



**字符串的format方法**

一般形式：

格式字符串.format()(输出1，输出2，·······，输出n)



其中格式字符串使用大括号括起来，一般形式为：

{[序号或键]：格式说明符}

1、使用“{序号}” 形式的格式说明符		注意序号是从0开始的

```python
>>>"{} {}".format("hello","world")
'hello world'
>>>"{1} {0}".format("hello","world")
'world hello'
>>>"{1} {0} {1}".format("hello","world")
'world hello world'
```

2、使用“{序号：格式说明符}”形式的格式说明符

```python
>>>"{0:.3f} {1}".format(3.1414926,100)
'3.141 100'
```

3、使用“{序号/键：格式说明符}”形式的格式说明符

```python
>>>"{0},pi={x}".format("圆周率",x=3.1414926)
'圆周率,pi=3.1414926'
```





## 5、选择结构程序设计

#### 5.1分支结构1

if语句

1、单分支if语句

​	形式：**if 表达式：**

​						**语句**（注意要向右缩进）

执行过程：如果表达式值非0，执行该语句，然后执行if的下一条语句；否则直接执行if的下一条语句。

```python
a,b = eval(input("请输入两个数（a,b）："))
		#请输入两个数（a,b）：2,3
max = a
if b>max:
    max = b	#注意缩进
print("max = %d" % max)
max = 3

```

```python
#输入三个整数，把这三个数从小到大输出
x,y,z = eval(input("Please input the (x,y,z):"))
if x > y:
    x,y=y,z
if x > z:
    x,z=z,x
if y > z:
    y,z=z,y
print("Small to big:%d %d %d\n" % (x,y,z))
```

2、双分支 if/else

形式：**if  表达式：**

​					**语句1**

​			**else：**

​					**语句2**

执行过程：如果表达式值非0，执行语句1，否则执行语句2；无论执行了哪一路分支之后，都执行if的下一条语句。

```python
a,b = eval(input("请输入两个数（a,b）："))
		#请输入两个数（a,b）：2,3
if a>=b:
    max = a
else:
    max = b
print("max = %d" % max)
```

```python
#判断给定的某一年是否是闰年
year = int(input("请输入年份："))

if year%4==0 and year%100!=0 or year%400==0:
    print("%d年是闰年。" % year)
    
else:
    print("%d年是平年。" % year)
```

1）随机数产生

python的random库提供了产生随机数的方法

random库属于python的标准库，使用之前需要导入库

​	**import random**

randint(a,b)

功能：返回一个a <= N <= b的随机整数N

```python
#猜数字游戏
import random
data = random.randint(1,5)
guess = int (input("请输入你要猜的数字（限1-5）："))
if guess == data:
    print("猜对了~_~,正确数字为：%d !" %data)
else:
    print("猜错了0_0,正确数字为：%d !" %data)

```



#### 5.2分支结构2

3、多分支if/elif

形式：

**if  表达式1：**

​	**语句块1**

**elif 表达式2：**

​	**语句块2**

**·······**

**else：**

**语句块n**



```python
x = eval(input("Input x:"))
if x<1:
    y=x
elif x<10:
    y=2*x+1
else:
    y=5*x-17
print("y=%f" %y)
```

简单总结：

1.if和else后的语句可以只有一条，也可以有多条语句，如果有多条语句，这些语句一定要缩进对齐。

2.else不是语句，不能单独使用，必须与if配对使用。

**if语句的嵌套**

```python
distance = float(input("请输入公里数："))
if distance < 0:
    print("抱歉，出错了！")
else:
    if distance<3:
        fee = 7
    elif distance<8:
        fee = 7 + (int)(distance-2)*1.7
    else:
        fee = 7 + 5*1.7+(int)(distance-7)*2.0

print("您的出租车费用为： %8.2f元" % fee)
```

python根据对齐关系来确定if之间的逻辑关系

**注意：**

（1）嵌套只能在一个分支内嵌套，不能出现交叉。嵌套的形式有多种，嵌套的层次也可以任意多。

（2）多层if嵌套结构中，要特别注意if和else的配对问题。else语句不能单独使用，必须与if配对使用。





## 6、循环结构程序设计

### 6.1循环控制语句

**while语句**

while语句为当型循环结构

一般形式：**while 表达式：**

​								**语句**

执行过程：当表达式的值为真(非0)时，重复执行语句，直到表达式的值为假，跳出循环。

特点：先判断表达式，后执行语句。

```python
sum = 0
i = 1
while i<=200:
    sum +=i
    i =i+1
print("sum = %d" %sum)
```

while语句中使用else子句

一般形式：

​				**while 表达式：**

​							**循环体**

​				**else：**

​							**语句**

```python
count = int(input())
while count<5:
    print(count,"is less than 5")
    count = count + 1
else:
    print(count,"is not less than 5")
```



**for语句**

一般形式：

​				**for 目标变量 in序列对象：**

​						**循环体**

执行过程：

for语句是通过遍历任意序列的元素来建立循环的，针对序列的每一个元素执行一次循环。

列表、字符串、元组、都是序列，可以利用它们来建立循环。



for语句中使用else子句

**for 目标变量 in序列对象：**

​		**循环体**

**else：**

​		**语句**

表示当循环体所有执行完了就执行else语句后的语句



range对象在for循环中的应用

range（）一般形式：

​						**range（[start,]end[,step]）**

```python
for i in range(5):
    print(i)
    
###************###
''' 
0
1
2
3
4
'''
###************###

for i in range(2,4):
    print(i)

###************###
''' 
2
3
'''
###************###    

for i in range(2,20,2):
    print(i)
   

###************###
''' 
2
4
6
8
10
12
14
16
18
'''
###************###
```

```python
sum = 0
for i in range(1,201):
    sum += i
print("sum = %d" % sum)

# sum = 20100
```



### 6.2循环嵌套

```python
for i in range(1,6):
    for i in range(1,6):
        print("*",end = "  ")
    print("\n")
    
    
'''
*  *  *  *  *  

*  *  *  *  *  

*  *  *  *  *  

*  *  *  *  *  

*  *  *  *  *  
'''
```

**金字塔**

```python
n = 10
for j in range(1,n+1):
    for i in range(1,n-j+1):
        print(" ",end = " ")
    for i in range(1,2*j):
        print("*",end = " ")
    print()
```

**九九乘法表**

```python
for j in range(1,10,1):
    for i in range(1,j+1,1):
       print("%d*%d=%-2d " %(i,j,i*j),end = "")
    print()
```



### 6.3累加累乘问题

```python
s = 0
count = 1
n = int(input())
while count<=n:
    s += count
    count +=1
print(s)
```

求圆周率

```python
s = 0
x = 1
t = 1
f = 1
while abs(x)>=10**-6:
    s = s+x
    t = t+2
    f = -f
    x = f/t

print(4*s)

```





## 7、序列

### 7.1组合数据类型

组合数据类型：将多个相同类型或不同类型的数据组合起来



序列类型：元组，列表，字符串

集合类型：集合

映射类型：字典



### 7.2列表的基本操作

**1、列表是包含0个或多个对象引用的有序序列**

**2、列表的长度和内容都是可变的**

**3、列表没有长度限制，元素类型可以不同**

**4、所有元素放在一对方括号中[]，相邻元素之间用逗号分隔开**



#### 7.2.1创建列表

使用赋值运算符” **=** “创建列表

```python
a_list =['physics','chemistry','2017','2.5']
#创建了一个列表，包含了四个元素
print(a_list)
#['physics', 'chemistry', '2017', '2.5']


b_list = ['wade',3.0,81,['bosh','haslem']]
#创建了一个列表，嵌套了一个列表，包含了四个元素
print(b_list)
#['wade', 3.0, 81, ['bosh', 'haslem']]

c_list = [1,2,(3.0,'hello world !')]
#创建了一个列表，嵌套了一个元组，包含了三个元素
print(c_list)
#[1, 2, (3.0, 'hello world !')]

d_list = []
e_list = list()
#创建了一个空列表
```



#### 7.2.2列表元素的读取

使用列表索引的方法读取元素：列表名[索引]

```python
a_list = ['physics','chemistry','2017','2.5']
a_list[1]
#'chemistry'
a_list[-1]
#'2.5'
a_list[5]
'''Traceback (most recent call last):
  File "<pyshell#9>", line 1, in <module>
    a_list[5]
IndexError: list index out of range
'''
```



#### 7.2.3列表切片

●取出列表中某一范围内的元素的得到一个新列表

●列表序号对

​					**列表名[开始索引：借宿索引：步长]**



开始索引:表示提取部分的以第一个元素的编号，默认为第一个，索引位置默认为0。

结束索引:表示是最后一个元素对象,不包含在切片范围内,默认是最后一个元素。

步长:步长为非零整数，默认为1。当步长为负数时,表示从右到左提取元素。



```python
a_list = ['physics','chemistry','2017','2.5']

a_list[1:3:1]
['chemistry', '2017']

a_list[-4:-1:1]
['physics', 'chemistry', '2017']
```



#### 7.2.4添加元素

使用 **” + “** 运算符将一个新列表添加在原列表的尾部

```python
a_list = [1,2,3,4,5]
a_list = a_list + [6,7]
a_list

#[1, 2, 3, 4, 5, 6, 7]
```

使用append（）方法向列表尾部添加一个新的元素

```python
a_list = [1, 2, 3, 4, 5, 6, 7]
a_list.append('python')
a_list

#[1, 2, 3, 4, 5, 6, 7, 'python']
```

使用extend（）方法将一个列表添加到原列表的尾部

```python
a_list = [1, 2, 3, 4, 5, 6, 7, 'python']
a_list.extend([8,9])
a_list

#[1, 2, 3, 4, 5, 6, 7, 'python', 8, 9]
```

使用insert（）方法将一个元素插入到列表的指定位置

```python
a_list.insert(1,1.5)#将元素1.5插入到1的位置
a_list

#[1, 1.5, 2, 3, 4, 5, 6, 7, 'python', 8, 9]
```



#### 7.2.5检索元素

index（）方法可以获取指定元素首次出现的下标

​				index(value,[start,end])

```python
a_list.index(5)
#5
a_list.index(8,6)
#9
```

count（）方法统计列表中指定元素出现的次数

```python
a_list.count(6)
#1
a_list.count(25)
#0
```

in 或 not in 运算符检索某个元素是否在该列表中

```python
1 in a_list
#True

2.5 in a_list
#False
```



#### 7.2.6删除元素

使用del命令删除列表中指定位置的元素

```python
a_list = [1, 3.5, 2, 3, 4, 5, 6, 7, 'python', 8, 9]
del a_list[3]
a_list
#[1, 3.5, 2, 4, 5, 6, 7, 'python', 8, 9]
```

使用del命令删除整个列表

```python
b_list = [1,2,3]
del b_list
b_list		#删除后再次访问显示报错


'''Traceback (most recent call last):
  File "<pyshell#41>", line 1, in <module>
    b_list
NameError: name 'b_list' is not defined. Did you mean: 'a_list'?
'''

```

remove（）方法删除首次出现的指定的元素

```python
c_list = [1,1,2,2,2]
c_list.remove(1)
c_list
#[ 1, 2, 2, 2]

c_list.remove(1)
c_list
#[2, 2, 2]

c_list.remove(1)

''' 
Traceback (most recent call last):
  File "<pyshell#50>", line 1, in <module>
    c_list.remove(1)
ValueError: list.remove(x): x not in list
'''


```

pop（）方法删除并返回指定位置上的元素

```python
a_list = [1, 3.5, 2, 4, 5, 6, 7, 'python', 8, 9]
a_list.pop() #默认删除最后一个元素
#9
a_list.pop(3)
#4
```



### 7.3列表的常用函数

#### 7.3.1列表常用函数-cmp()

**cmp()函数**

**格式：cmp(列表1，列表2)**

**功能：比较两个列表**

cmp指定一个定制的比较函数，这个函数接收两个参数，如果第一个参数小于第二个参数，返回一个负数；如果第一个参数等于第二个参数，返回零；如果第一个参数大于第二个参数，返回一个正数。默认值为None。

```python
cmp([1,2,3,6],[1,2,3,5])
#1

cmp([1,2,3],[1,2,3])
#0

cmp([123,'Bsaic'],[123,'Python'])
#-1
```

在python3.x中去掉了cmp()函数，可以直接用运算符进行比较

**>、<、==**

**功能：比较两个列表**

**返回值：True或False**

```python
[123,'Bsaic']>[123,'Python']
#False

[123,'Bsaic']<[123,'Python']
#True

[1,2,3]==[1,2,3]
#True
```



#### 7.3.2列表常用函数-len()

**len()函数**

**格式：len(列表)**

**功能：返回列表中的元素个数**

```python
a_list = ['physics','chemistry',2022,25,[0.5,1]]
len(a_list)
#5

len([1,2.0,'hello'])
#3

```



#### 7.3.3列表常用函数-max()和min()

**max()函数和min()函数**

**格式：max(列表)或min(列表)**

**功能：返回列表中最大或最小的元素**

```python
a_list = ['123','xyz','zara','abc']
max(a_list)
#'zara'

min(a_list)
#'123'

```



#### 7.3.4列表常用函数-sum()

**sum()**

**格式：sum(列表)**

**功能：对数值型列表的元素进行求和运算，对非数值型列表进行运算会出错**

```python
a_list=[23,59,-1,2.5,39]
sum(a_list)
#122.5

b_list = [123,'xyz','zara','abc']
sum(b_list)	#报错

'''
Traceback (most recent call last):
  File "<pyshell#4>", line 1, in <module>
    sum(b_list)
TypeError: unsupported operand type(s) for +: 'int' and 'str'

'''
```



#### 7.3.4列表常用函数-sorted()

**sorted()**

**格式：sorted(列表)**

**功能：对列表进行排序，默认是按照升序排序，但是要注意的是函数调用并不会改变原列表的排序，只是函数调用的返回结果是升序或降序**

```python
a_list=[80,20,30,34,56,4,56,23,45,66]
sorted(a_list)
#[4, 20, 23, 30, 34, 45, 56, 56, 66, 80]

a_list		#再次输出时，我们可以知道原列表顺序并未改变
#[80, 20, 30, 34, 56, 4, 56, 23, 45, 66]
```

**用sorted()函数对列表进行降序排序**

**格式：sorted(列表，reverse=True)**

```python
a_list=[80,20,30,34,56,4,56,23,45,66]
sorted(a_list,reverse=True) 
#[80, 66, 56, 56, 45, 34, 30, 23, 20, 4]

sorted(a_list,reverse=False)	#若reverse=False则为升序排序
#[4, 20, 23, 30, 34, 45, 56, 56, 66, 80]
```



#### 7.3.5列表常用函数-sort()

**sort()**

**格式：列表名.sort()**

**功能：对列表进行排序，默认是按照升序排序，但是要注意的是函数调用会覆盖原列表，也就是会改变原列表的排序**

```python
a_list=[80,20,30,34,56,4,56,23,45,66]
a_list.sort()
a_list
#[4, 20, 23, 30, 34, 45, 56, 56, 66, 80]

```

**用sort()函数对列表进行降序排序**

**格式：列表名.sorted(reverse=True)**

```python
a_list=[80,20,30,34,56,4,56,23,45,66]
a_list.sort(reverse=True)	#降序
a_list
#[80, 66, 56, 56, 45, 34, 30, 23, 20, 4]

a_list.sort(reverse=False)	#升序
a_list
#[4, 20, 23, 30, 34, 45, 56, 56, 66, 80]
```



#### 7.3.6列表常用函数-reverse()

**格式：列表名.reverse()**

**功能：对列表中的元素进行翻转存放**

```python
a_list=[80,20,30,34,56,4,56,23,45,66]
a_list.reverse()	#逆序存放
a_list
#[66, 45, 23, 56, 4, 56, 34, 30, 20, 80]
```



### **7.4列表的应用**

**例：编写程序实现将列表中元素逆置**

​		逆置是指将列表中的元素按照与原来的位置顺序相反的顺序重新存放。

例如：

​		原列表：1，2，3，4，5

​		逆置后列表：5，4，3，2，1



**问题分析：**

1、从键盘读入数据，(以逗号分隔开)存放到一个变量中

2、使用字符串的分割函数和列表的append方法，将读入的数据存放到列表中

3、遍历列表的一半元素，首尾依次交换

4、输出你之后的数据

```python
b_list = input("请输入数据：")
a_list = []
for i in b_list.split(','):
    a_list.append(i)
print("逆置前的数据为：",a_list)
n = len(a_list)
for i in range(n//2):
    a_list[i],a_list[n-i-1] = a_list[n-i-1],a_list[i]
print("逆置后的数据为：",a_list)

#请输入数据：1,3,5,7,9
#逆置前的数据为： ['1', '3', '5', '7', '9']
#逆置后的数据为： ['9', '7', '5', '3', '1']

```



### 7.5元组

#### 7.5.1创建元组

使用赋值运算符  **” = “**  创建元组

```python
a_tuple=('physics','chemistry',2022,25)
b_tuple=('physics','chemistry',2022,25,(3.0,'hello,world')) 	#元组中内嵌了一个元组
c_tuple=('physics','chemistry',2022,25,[0.5,1]) 	#元组中内嵌了一个列表
d_tuple=() 	#创建了一个空元组
e_tuple=tuple() 	#用tuple（）函数创建了一个空元组
```

创建只包含一个元素的元组

```python
x =(1)	#x为数字类型1
x
#1

y = (1,)	#创建只包含一个元素的元组
y
#(1,) 从输出结果可以看出，python在输出只包含一个元素的元组时会默认加一个逗号，以免误解为数学计算意义的括号
```



#### 7.5.2元组元素的读取

使用序列索引的方法读取元素

​	元组名[索引]

```python
a_tuple=('physics','chemistry',2022,25)
a_tuple[1]
#'chemistry'

a_tuple[-1]
#25

a_tuple[5]	#报错，a_tuple元组只包含4个元素，提示越界错误
''' 
Traceback (most recent call last):
  File "<pyshell#12>", line 1, in <module>
    a_tuple[5]
IndexError: tuple index out of range

'''

```



#### 7.5.3元组切片

一般形式：

​				元组名[开始索引:结束索引:步长]

```python
a_tuple=('physics','chemistry',2022,25)
a_tuple[1:3]
#('chemistry', 2022)

a_tuple[::3]
#('physics', 25)
```



#### 7.5.4检索元素

index()方法可以获取指定元素首次出现的下标

​		index(value,[start,[,end]])

```python
a_tuple=('physics','chemistry',2022,25)
a_tuple.index(2022)
#2

a_tuple.index('physics',-3)
'''
Traceback (most recent call last):
  File "<pyshell#16>", line 1, in <module>
    a_tuple.index('physics',-3)
ValueError: tuple.index(x): x not in tuple
'''
```

count()方法统计列表中指定元素出现的次数

```python
a_tuple=('physics','chemistry',2022,25)
a_tuple.count(2022)
#1
a_tuple.count(1)
#0
```

in或not in 运算符检索某个元素是否在该列表中

```python
a_tuple=('physics','chemistry',2022,25)
'chemistry' in a_tuple
#True

2 in a_tuple
#False

```



#### 7.5.5删除元组

元组的元素不能删除，但可以使用del语句删除元组

使用del命令删除元组

```python
a_tuple=('physics','chemistry',2022,25)
del a_tuple
a_tuple
'''
Traceback (most recent call last):
  File "<pyshell#23>", line 1, in <module>
    a_tuple
NameError: name 'a_tuple' is not defined. Did you mean: 'b_tuple'?
'''
```



#### 7.5.6列表和元组的区别

（1）列表是可变序列，而元组是不可变序列

（2）元组的处理速度和访问速度比列表快

（3）元组在字典中可以作为关键字使用，而列表不能作为关键字使用，因为列表不是不可改变的



#### 7.5.7列表和元组的转换

通过list()函数 、tuple() 实现相互转换

```python
a_list=['physics','chemistry',2022,25]
tuple(a_list)
#('physics', 'chemistry', 2022, 25)

type(a_list)# a_list类型并没有改变，tuple只是得到了元组类型的中间结果，若要保存中间结果则需要定义一个变量，用于接收tuple调用返回的值
#<class 'list'>

b_tuple=('physics','chemistry',2022,25,(3.0,'hello,world'))
list(b_tuple)
#['physics', 'chemistry', 2022, 25, (3.0, 'hello,world')]

type(b_list)
#<class 'str'>

```

tuple()函数

冻结列表，是元素之不可改变

list()函数

融化元组，使其元素值可变，达到修改目的



### 7.6字符串基本操作

Python中的字符串用一对单引号（‘）或双引号（”）括起来



三重引号表示，可以保留所有字符串的格式信息

```python
>>>'''python hello world ! "lin tao"
      hhhhh '''

#'python hello world ! "lin tao"\nhhhhh ' 出现了换行字符
```



#### 7.6.1创建字符串

使用赋值运算符 “  =  ”或str（）函数

```python
str = 'Hello'
str
#'Hello'

str1 = 'program "python"'
str1
#'program "python"'

str2 = str()
str2
#''
```



#### 7.6.2读取字符串的元素

读取字符：字符名[索引]

```python
str = 'Hello'
str[1]
#'e'

str[-1]
#'o'

str[9]	#报错 不能越界
'''
Traceback (most recent call last):
  File "<pyshell#12>", line 1, in <module>
    str[9]
IndexError: string index out of range
'''
```



#### 7.6.3字符串切片

切片：字符串名[开始索引：结束索引：步长]

```python
str = 'Hello'
str[0:5:2]
#'Hlo'

str[:]	#输出str字符串全部内容
#'Hello'

str[-1:-10]
#''

str[-1:-10:-1]
#'olleH'
```



#### 7.6.4字符串连接

使用运算符 “  +  ”  ，将两个字符串对象连接起来

```python
'hello '+'world'
#'hello world'

'python ' + str(3)	#要将3转换成字符型
#'python 3'
```



#### 7.6.5字符串重复运算

使用运算符 “  *  ”

```python
'hello '*3
#'hello hello hello'

3*'hello'
#'hello hello hello'
```



#### 7.6.6字符串的比较

单字符 字符串的比较，基于ASCII码值概念进行的

使用关系运算符进行比较

```python
"a" == "a"
#True

'a' == 'A'
#False
```

多字符 字符串的比较

```python
'abc' == 'abd'
#False

'abc' > 'abd'
#False

'abc' < 'abd'
#True

'' < '0'	#空字符串比任何字符串都要小
#True
```



#### 7.6.7成员运算

使用运算符 in 或 not in ：字符串1 [not] in 字符串2

```python
'ab' in 'aabb'
#True

'abc' in 'aabbcc'
#False

'a' not in 'abc'
#False

```



### 7.7字符串基本函数

字串查找

使用find方法：str.find(substr,[start,[,end]])

```python
s1 = 'beijng jiangxi ganzhou ruijin jiujiang jiangxi'
s1.find('jiangxi')
#7

s1.find('jiangxi',10)
#39

s1.find('jiangxi',10,20)	#不存在 返回-1
#-1

```

字符串替换

使用replace（）方法：sr.replace(old,new,(max))  #old:进行更换的旧字符串  new:替换old子字符串的新字符串 max:可选项 表示替换的最大的次数

```python
s2 = 'this is string example.this is string example.'
s2.replace('is','was')
#'thwas was string example.thwas was string example.'

s2
#'this is string example.this is string example.'

s2.replace('is','was',2)
#'thwas was string example.this is string example.'

```

字符串分离

使用split()方法：str.split([sep])  #sep是指分隔符，默认以空格作为分隔符

```python
s1 = 'beijng jiangxi ganzhou ruijin jiujiang jiangxi'
s1.split()
#['beijng', 'jiangxi', 'ganzhou', 'ruijin', 'jiujiang', 'jiangxi']

s1.split('a')
#['beijng ji', 'ngxi g', 'nzhou ruijin jiuji', 'ng ji', 'ngxi']
```

字符串连接

使用join（）方法：sep.join（sequence）#sep:分隔符，可以为空    sequence：要连接的元素序列

```python
s1 = ['beijng','jiangxi','ganzhou','ruijin','jiujiang','jiangxi']
sep = '->'
str = sep.join(s1)
str
#'beijng->jiangxi->ganzhou->ruijin->jiujiang->jiangxi'

sep=''
str = sep.join(s1)
str
#'beijngjiangxiganzhouruijinjiujiangjiangxi'
```

字符串常用方法

![image-20220807215820100](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220807215820100.png)



### 7.8字符串应用

例：从键盘输入一行字符，分别统计出其中英文字母、空格、数字和其他字符的个数

```python
a_list = list(input('请输入一行字符：'))
letter = []
space = []
number = []
other = []
for i in range(len(a_list)):
    if ord(a_list[i]) in range(65, 90) or ord(a_list[i]) in range(97,122):
        letter.append(a_list[i])
    elif a_list[i] == ' ':
        space.append(' ')
    elif ord(a_list[i]) in range(48, 58):
        number.append(a_list[i])
    else:
        other.append(a_list[i])

print('英文字母个数：%s' % len(letter))
print('空格个数：%s' % len(space))
print('数字个数：%s' % len(number))
print('其他字符个数：%s'% len(other))          


'''
请输入一行字符：lintao  1112223  $%^^ jkshkj
英文字母个数：12
空格个数：5
数字个数：7
其他字符个数：4
'''

```





## 8、字典和集合

### 8.1字典

**映射类型**

映射：key-value的键值对，通过key可以找到其他映射的value

字典是python语言中唯一的映射类型，映射类型中的元素是无序的



**字典**

形式：**{<键1>:<值1>，<键2>:<值2>，........，<键n>:<值n>}**

字典的键：不可变类型，例如整数、实数、复数、字符串、元组等。

键不能重复，而值可以重复。一个键只能对应一个值，但多个键可以对应相同的值。

```python
{1:"lintao",2:"jiangxi",3:"nan",4:"student"}
#{1: 'lintao', 2: 'jiangxi', 3: 'nan', 4: 'student'}

{(1,2,3):'A',55:'B'}
#{(1, 2, 3): 'A', 55: 'B'}
```



创建字典

1、使用 “  =  ” 将一个字典赋给一个变量

```python
a_dict = {1:"lintao",2:"jiangxi",3:"nan",4:"student"}
a_dict
#{1: 'lintao', 2: 'jiangxi', 3: 'nan', 4: 'student'}#顺序和一开始创建的不一定相同，因为各个元素并没有顺序之分

b_dict = {}	#创建一个空的字典
b_dict
#{}
```

2、使用内建函数 **dict()** 来建立字典

```python
c_dict = dict(zip(['one','two','three'],[1,2,3]))
c_dict
#{'one': 1, 'two': 2, 'three': 3}

d_dict = dict(one=1,two=2,three=3)
d_dict
#{'one': 1, 'two': 2, 'three': 3}

e_dict = dict([('one',1),('two',2),('three',3)])           e_dict
#{'one': 1, 'two': 2, 'three': 3}

f_dict = dict((('one',1),('two',2),('three',3)))
f_dict
#{'one': 1, 'two': 2, 'three': 3}

g_dict = dict()
g_dict
#{}
```

3、使用内建函数fromkeys()

​		**dict.fromkeys(seq[,value])**  

​		**{}.fromkeys(seq[,value])** 

sep:字典键值列表，value:可选参数，默认为：None

```python
g_dict = dict.fromkeys((1,2,3),'lintao')
g_dict
#{1: 'lintao', 2: 'lintao', 3: 'lintao'}

g_dict = {}.fromkeys((1,2,3),'lintao')
g_dict              
#{1: 'lintao', 2: 'lintao', 3: 'lintao'}

g_dict = dict.fromkeys(())             
g_dict              
#{}
```



字典元素的读取

1、使用下标的方法

```python
a_dict = {1:"lintao",2:"jiangxi",3:"nan",4:"student"}
a_dict[1]              
#'lintao'

a_dict[2]
#'jiangxi'

a_dict[nan]	#nan不是键，报错 
'''
Traceback (most recent call last):
  File "<pyshell#28>", line 1, in <module>
    a_dict[nan]
NameError: name 'nan' is not defined
'''

```

2、使用get方法获取执行键对应的值

dict.get(key,default=None)

key:字典中要查找的键 default: 指定的键值不存在时返回的值

```python
a_dict = {1:"lintao",2:"jiangxi",3:"nan",4:"student"}
a_dict.get(1)
'lintao'

a_dict.get(5,'address')              
'address'

a_dict.get(5)
              

```



字典元素的添加与修改

1、使用" 字典名[键名]=键值 " 形式

```python
a_dict = {1:"lintao",2:"jiangxi",3:"nan",4:"student"}
a_dict[3]='man' #修改
a_dict            
#{1: 'lintao', 2: 'jiangxi', 3: 'man', 4: 'student'}

a_dict[5]=18 	#添加             
a_dict              
{1: 'lintao', 2: 'jiangxi', 3: 'man', 4: 'student', 5: 18}

```

2、使用update（）方法

将另一个字典的键值对一次性全部添加到当前字典上，如果另一个键存在与当前字典，则对当前字典进行更新，若不存在则添加新的键值对

```python
a_dict = {1: 'lintao', 2: 'jiangxi', 3: 'man', 4: 'student', 5: 18}
b_dict = {2:'ruijin',6:100}
a_dict.update  
a_dict              
#{1: 'lintao', 2: 'ruijin', 3: 'man', 4: 'student', 5: 18, 6: 100}
# 2更新  6添加

```



字典元素的删除

使用del命令删除字典中指定键对应的元素

```python
a_dict = {1: 'lintao', 2: 'ruijin', 3: 'man', 4: 'student', 5: 18, 6: 100}
del a_dict[6]             
a_dict
              
#{1: 'lintao', 2: 'ruijin', 3: 'man', 4: 'student', 5: 18}

del a_dict[18] #不存在18的键的元素 报错

'''            
Traceback (most recent call last):
  File "<pyshell#48>", line 1, in <module>
    del a_dict[18]
KeyError: 18
'''
```

使用pop（）方法删除并返回指定键的元素

```python
a_dict = {1: 'lintao', 2: 'jiangxi', 3: 'man', 4: 'student', 5: 18}
a_dict.pop(5)             
#18

a_dict
#{1: 'lintao', 2: 'ruijin', 3: 'man', 4: 'student'}
```

使用popitem()方法，随机元素

```python
a_dict = {1: 'lintao', 2: 'ruijin', 3: 'man', 4: 'student'}
a_dict.popitem()           
#(4, 'student')

a_dict             
#{1: 'lintao', 2: 'ruijin', 3: 'man'}

```

使用clear（）方法删除素有元素,字典为空

```python
a_dict = {1: 'lintao', 2: 'ruijin', 3: 'man'}
a_dict.clear()
              
a_dict	#再次访问时为空字典
              
#{}
```

使用del命令删除整个字典，字典就不存在了

```python
a_dict = {1: 'lintao', 2: 'ruijin', 3: 'man', 4: 'student'}
              
del a_dict
              
a_dict
'''
Traceback (most recent call last):
  File "<pyshell#57>", line 1, in <module>
    a_dict
NameError: name 'a_dict' is not defined. Did you mean: 'b_dict'?
'''              
```

字典元素的遍历

遍历字典的关键字

一般形式：dict.keys()

```python
a_dict = {1: 'lintao', 2: 'ruijin', 3: 'man', 4: 'student'}           a_dict.keys()
              
#dict_keys([1, 2, 3, 4])


```



遍历字典的值

一般形式：dict.values()

```python
a_dict = {1: 'lintao', 2: 'ruijin', 3: 'man', 4: 'student'}
a_dict.values()
              
#dict_values(['lintao', 'ruijin', 'man', 'student'])
```



遍历字典的元素

一般形式：dict.items()

```python
a_dict = {1: 'lintao', 2: 'ruijin', 3: 'man', 4: 'student'}
a_dict.items()
              
#dict_items([(1, 'lintao'), (2, 'ruijin'), (3, 'man'), (4, 'student')])


```

字典的常用方法

![image-20220807215626511](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220807215626511.png)

 

字典的应用

例：输入一串字符，统计其中单词出现的次数，单词之间用空格分隔开

```python
string = input("input string:")
string_list = string.split()
word_dict = {}
for word in string_list:
    if word in word_dict:
        word_dict[word] += 1
    else:
        word_dict[word] = 1

print(word_dict)


'''
input string:lintao lintao lintao hello world world verygood! verygood!
{'lintao': 3, 'hello': 1, 'world': 2, 'veryood!': 2}
'''

```



### 8.2集合

 集合：0个或多个对应引用的无序排列的、不重复的数据集合体。可进行交、并、差等运算



创建集合

 使用 **“=”** 将一个集合赋给一个变量

```python
a_set={0,1,2,3,4,5,6,7,8,9}
a_set
#{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}

b_set={1,3,3,5}
b_set
#{1, 3, 5}
```

 使用集合对象的set()方法创建集合

```python
b_set=set(['physics', 'chemistry',2017, 2.5])
b_set
#{2017, 2.5, 'physics', 'chemistry'}

c_set=set(('Python', 'C','HTML','Java','Perl '))
c_set
#{'Java', 'Python', 'C', 'Perl ', 'HTML'}

d_set=set('Python')
d_set
#{'P', 'n', 'h', 'o', 't', 'y'}
```

注意：集合中不允许有相同元素

```python
 g_set={0,0,0,0,1,1,1,3,4,5,5,5}
 g_set	#自动删除相同元素
#{0, 1, 3, 4, 5}

```

使用frozenset()方法创建一个冻结的集合

该集合不能添加或删除集合里的任意元素

```python
e_set=frozenset('a')
e_set
#frozenset({'a'})

a_dict={e_set:1,'b':2}
a_dict
#{frozenset({'a'}): 1, 'b': 2}

f_set=set('a')
b_dict={f_set:1,'b':2}
'''
Traceback (most recent call last):
  File "<pyshell#19>", line 1, in <module>
    b_dict={f_set:1,'b':2}
TypeError: unhashable type: 'set' 
'''
```

**区分frozenset()方法与set()方法创建集合的区别：**

set()方法创建的集合可以添加或删除元素，而frozenset()方法则不行

frozenset()方法可以作为字典的key,也可以作为其他集合的元素，而set不可以



访问集合

 使用in或者循环遍历访问集合元素

```python
b_set=set(['physics', 'chemistry',2017, 2.5])
b_set
#{2017, 2.5, 'physics', 'chemistry'}

2.5 in b_set
#True

3 in b_set
#False

for i in b_set:print(i,end=' ')
#2017 2.5 physics chemistry 

```

删除集合

 使用del命令

```python
a_set={0,1,2,3,4,5,6,7,8,9}
a_set
#{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}

del a_set
a_set
'''
Traceback (most recent call last):
 File "<pyshell#66>", line 1, in <module>
 a_set
NameError: name 'a_set' is not defined
'''
```

增加元素

使用add()方法：s.add(x)

```python
b_set={'chemistry', 2017, 2.5, 'physics'}
b_set.add('math')
b_set
#{'chemistry', 2017, 2.5, 'math', 'physics'}
```

使用update()方法：s.update(s1,s2,…,sn)

```python
s={'Phthon','C','C++'}
s.update({1,2,3},{'Wade','Nash'},{0,1,2})
s
{0, 1, 2, 3, 'Phthon', 'Wade', 'C++', 'Nash', 'C'}
```

删除集合中的元素

使用remove()方法：s.remove(x)

```python
s={0, 1, 2, 3, 'Phthon', 'Wade', 'C++', 'Nash', 'C'}
>>> s.remove(0)
>>> s
#{1, 2, 3, 'Phthon', 'Wade', 'C++', 'Nash', 'C'}

>>> s.remove('Hello')	#删除不存在的元素报错
'''
Traceback (most recent call last):
 File "<pyshell#45>", line 1, in <module>
 s.remove('Hello')
KeyError: 'Hello'
'''
```

 使用discard ()方法：s. discard(x)

```python
s={0, 1, 2, 3, 'Phthon', 'Wade', 'C++', 'Nash', 'C'}
>>> s.discard('C')
>>> s
#{1, 2, 3, 'Phthon', 'Wade', 'C++', 'Nash'}

>>> s.discard('abc')	#删除不存在的元素不会报错
#{1, 2, 3, 'Phthon', 'Wade', 'C++', 'Nash'}
```

使用pop()方法删除任意一个元素

```python
s={0, 1, 2, 3, 'Phthon', 'Wade', 'C++', 'Nash', 'C'}
>>> s.pop()
#1

>>> s
#{2, 3, 'Phthon', 'Wade', 'C++', 'Nash'}
```

 使用clear()方法删除集合中所有元素

```python
s={0, 1, 2, 3, 'Phthon', 'Wade', 'C++', 'Nash', 'C'}
>>> s.clear()
>>> s
#set()
```

集合常用运算

 交集：**s1 & s2 & … & sn**

```python
>>> {0,1,2,3,4,5,7,8,9}&{0,2,4,6,8}
#{8, 0, 2, 4}

>>> {0,1,2,3,4,5,7,8,9}&{0,2,4,6,8}&{1,3,5,7,9}
#set()
```

并集：**s1 | s2 | … | sn**

```python
>>> {0,1,2,3,4,5,7,8,9}|{0,2,4,6,8}
#{0, 1, 2, 3, 4, 5, 6, 7, 8, 9}

>>> {0,1,2,3,4,5}|{0,2,4,6,8}
#{0, 1, 2, 3, 4, 5, 6, 8}
```

 差集：**s1 - s2 - … - sn**

```python
>>> {0,1,2,3,4,5,6,7,8,9}-{0,2,4,6,8}
#{1, 3, 5, 9, 7}

>>> {0,1,2,3,4,5,6,7,8,9}-{0,2,4,6,8}-{2,3,4}
#{1, 5, 9, 7}
```

 对称差集：**s1 ^ s2 ^ … ^ sn**

```python
>>> {0,1,2,3,4,5,6,7,8,9}^{0,2,4,6,8}
#{1, 3, 5, 7, 9}

>>> {0,1,2,3,4,5,6,7,8,9}^{0,2,4,6,8}^{1,3,5,7,9}
#set()
```





## 9、函数

### 9.1函数概述及其应用

**Python程序基本结构**

![image-20220808164319746](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220808164319746.png)

**使用函数的好处：**

① 程序结构清晰，可读性好。

② 减少重复编码的工作量。

③ 可多人共同编制一个大程序，缩短程序设计周期，提高程序设计和调试的效率。



**函数举例：**

```python
def print_info():
	print(‘---------------------------------------’)
	print(‘ 人生苦短，我用Python ’)
	print(‘---------------------------------------’)
print_info()

################
---------------------------------------
 人生苦短，我用Python 
---------------------------------------


```



#### 9.1.1函数的分类：

**1、从用户的使用角度**



1······库函数（标准函数）：由系统提供

在使用库函数前应先导入该函数原型所在的模块

​	使用库函数应注意：

​		1、函数功能

​		2、函数参数的数目和顺序，及各参数意义和类型

​		3、函数返回值意义和类型



2·······用户自定义函数



**2、从参数传递的角度**

**有参函数：**函数定义时带有参数的函数。函数定义时的参数（形式参数），函数实际调用时的参数（实际参数）。

```python
def average(x,y,z):#三个参数
	aver=(x+y+z)/3;
	return(aver)
a,b,c=eval(input("please input a、 b、c:"))
ave=average(a,b,c) 
print("average=%f"%ave)

'''
please input a、 b、c:1,2,3
average=2.000000
'''
```

**无参函数**

```python
def printstar():
	print("*************")
def print_message():
	print("How are you!")
def main():
	printstar()
	print_message()
	printstar()
main()


*************
How are you!
*************
```



#### 9.1.2函数的定义

一般形式：

​		**def 函数名（[形式参数表]）:**

​			 **函数体**

 			**[return 表达式]** 



**函数定义时要注意**

 采用def 关键字定义函数，不需要指定返回值的类型；

 函数的参数不限，不需要指定参数类型；

 参数括号后面的冒号 “ : ” 必不可少；

 函数体相对于def关键字必须保持一定的空格缩进；

 return语句是可选的；

 允许定义函数体为空的函数。



#### 9.1.3函数的调用

一般形式：

 **函数名（[实际参数表]**



程序调用一个函数需要执行以下过程：

 调用程序在调用处暂停执行

 在调用时将实参传递给形参

 执行函数体语句

 函数调用结束给出返回值，程序回到



### 9.2函数参数传递

函数间数据传递方式：

​	** 函数调用**

​	** 返回值**



函数参数分类：

​	** 实际参数（实参）**函数被调用时，在被调用处给出对应的参数

​	** 形式参数（形参）**函数定义的首部，函数名后括号中的变量



#### 9.2.1值传递方式

 **值传递方式：函数调用时，为形参分配存储单元，并将实参的值复制到形参。**

**特点：**形参和实参各占不同的内存单元，函数中对形参值的改变不会改变实参的值

```python
def swap(a,b):
    a,b=b,a
    print("a=",a,"b=",b)
 
x,y=eval(input("input x,y:"))
swap(x,y)
print("x=",x,"y=",y)

'''
input x,y:2,3
a= 3 b= 2
x= 2 y= 3
'''

```



#### 9.2.2地址传递方式

 **地址传递方式：在函数调用时，将实参数据的存储地址作为参数传递给形参**

**特点：**形参和实参占用同样内存单元，函数中对形参值得改变也会改变实参的值

```python
def swap(a_list):
    a_list[0],a_list[1]=a_list[1],a_list[0]
    print("a_list[0]=",a_list[0],"a_list[1]=",a_list[1])

x_list=[3,5]
swap(x_list)
print("x_list[0]=",x_list[0],"x_list[1]=",x_list[1])



'''
a_list[0]= 5 a_list[1]= 3
x_list[0]= 5 x_list[1]= 3
'''
```



#### 9.2.3默认参数

 **在函数定义时，直接在函数形参后面使用赋值运算符  “ = ” 为其设置默认值**

```python
def func(x, n = 2):
    f = 1
    for i in range(n):
        f*=x
    return f
 
print(func(5)) 
print(func(5,3))

'''
25
125
'''
```

**注意：**

（1）所有位置参数必须出现位于参数列表的最后面。

```python
def func(a,b=1,c=2):
	return print(a+b+c)
func(3)
#报错 定义了三个形参，使用func(3)时，实参3不确定传给哪个形参
```

（2）默认参数的值只在定义时被设置计算一次，如果函数修改了对象，默认值就被修改了。

```python
def func(x, a_list = []):
    a_list.append(x)
    return a_list

print(func(1))
print(func(2))
print(func(3))

'''
[1]
[1, 2]
[1, 2, 3]
'''

```



#### 9.2.4位置参数和关键字参数

python将实参定义为两种类型：位置参数和关键字参数

**位置参数**

 **在函数调用时，实参默认采用按照位置顺序传递给形参的方式**

**特点：**形参和实参各占不同的内存单元，函数中对形参值的改变不会改变实参的值

```python
def func(a,b):
    c=a**b
    return c
print(func(2,3))
print(func(3,2))



'''
8
9
'''
```

**关键字参数**

 **指定参数：键 = 值**

```python
def func(a,b):
    c=a**b
    return c
print(func(a=2,b=3))
print(func(b=3,a=2))

'''
8
8
'''

```



#### 9.2.4可变长参数

 变长参数可以是元组或者字典类型

 变量名前加星号 *** **或 ****** ，以区分一般参数

 变量名前加星号*****——元组

 变量名前加星号******——字典



**可变长参数——元组**

```python
def func(*para_t): 
    print("可变长参数数量为:") 
    print(len(para_t)) 
    print("参数依次为:") 
    for x in range(len(para_t)): 
        print(para_t[x]); 

func('a') 
func(1,2,3,4);

'''
可变长参数数量为:
1
参数依次为:
a
可变长参数数量为:
4
参数依次为:
1
2
3
4
'''
```

**可变长参数——字典**

 **实参形式：键 = 值**

```python
def func(**para_t):
    print(para_t)
 
func(a=1,b=2,c=3)

'''
{'a': 1, 'b': 2, 'c': 3}
'''
```

**默认参数、位置参数、可变长参数应用举例**

```python
def func(x,*para,y = 1): #默认参数要放到最后
	print(x)
	print(para)#以元组的形式进行输出
	print(y)

func(1,2,3,4,5,6,7,8,9,10,y=100)


'''
1
(2, 3, 4, 5, 6, 7, 8, 9, 10)
100
'''
```



### 9.3函数的递归调用

**递归调用：**在函数的执行过程中又直接或间接调用该函数本身

 直接递归调用：

 	在函数中直接调用函数本身

 间接递归调用：

 	在函数中调用其它函数，其它函数又调用原函数



![image-20220809092855523](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809092855523.png)

例：用递归的方法求n的阶乘。

```python
def fac(n):
	if n==0:
		f=1
	else:
		f=fac(n-1)*n
	return f
	
n=int(input("please input n: "))
f=fac(n)
print("%d!=%d"%(n,f))

'''
please input n: 3
3!= 6
'''

```

![image-20220809094126765](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809094126765.png)



**递归算法的特点**

递推归纳

将问题转化为比原问题小的同类规模，归纳出一般递推公式. 故所处理的对象要有规律地递增或递减

递归终止

当规模小到一定的程度应该结束递归调用，逐层返回常用条件语句来控制何时结束递归



**递归的执行过程**

执行过程（两个阶段）

– 第一阶段：递推归纳，逐层调用，调用函数自身

– 第二阶段：回归逐层返回，返回到调用该层的位置

递归调用是多重嵌套调用的一种特殊情况

调用的深度：调用的层数



**设计递归算法的方法**

前提：

1、原问题可以层层分解为类似的子问题，且子问题比原问题规模更小

2、规模最小的问题具有直接解

方法：

1、寻找分解方法：将原问题转化为子问题求解，例：n!=n*(n-1)!

2、设计递归出口：根据规模最小的子问题确定递归终止条件，例：求解n! ，当n＝0时，n!＝1；



**递归函数练习题**

![image-20220809094633212](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809094633212.png)







### 9.4变量作用域

**变量的作用域：**可以合法访问变量的范围，由变量的位置来确定。

变量定义有两种位置：  

​		在所有函数之外

​		在块内

按作用域划分：将变量分为局部变量和全局变量



#### 9.4.1局部变量

**定义：**在函数内部定义的变量或复合语句内定义的变量

 **作用域：**限于定义它的函数或语句块中



**任意一个函数都不能访问其它函数中定义的局部变量**

1.主函数中定义的变量也属于局部变量。

2.不同的函数中定义的变量，其作用范围都限定在各自的函数中。

3.形参也是局部变量



**局部变量的作用域范围**

![image-20220809095053564](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809095053564.png)



**局部变量的使用**

```python
def f1(x):
	print("x=",x)
	x=20
	print("changed local x=",x)
x=30
f1(30)
print("main x=",x)


'''
x= 30
changed local x= 20
main x= 30
'''
```



#### 9.4.2全局变量

定义：在所有函数外定义的变量

![image-20220809095440756](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809095440756.png)



例：

```python
def f():
    global x
    x=30
    y=40
    print('NO2:',x,y)

x=10
y=20
print('NO1:',x,y)
f()
print("NO3:",x,y)

'''
NO1: 10 20
NO2: 30 40
NO3: 30 20
'''

```

在同一个程序文件中，如果全局和局部变量同名，在局部变量的作用范围内，全局变量不起作用。



**函数嵌套定义中的全局变量**

```python
def f():
    global x
    x="ABC"
    def g():
        global x
        x+="def"
        return x
    return g()
 
str=f()
print(str)


'''
ABCdef
'''
```



**使用全局变量的主要目的：**

** 为函数间的数据传递提供了直接传递通道**

** 使函数能返回多个值**

** 减少函数的参数传递**

** 破坏了函数的封装性能**



### 9.5模块

 **模块：**将一些常用的功能单独放置到一个文件中，方便其他文件来调用。

 从用户的角度看，模块也分为**标准库模块**和**用户自定义模块**。



#### 9.5.1标准库模块

**标准库模块是Python自带的函数模块。** 

 文本处理

 文件处理

 操作系统功能

 网络通信

 网络协议

**Python还提供了大量的第三方模块**

 科学计算

 Web开发

 数据库接口

 图形系统



#### 9.5.2用户自定义模块

用户建立一个模块就是建立扩展名为.py的Python程 序。

**def printer(x):**

​	**print(x)**

将以上程序代码保存成.py程序，例如module.py



**导入模块**

**导入模块：给出一个访问模块提供的函数、对象和类的方法。**



**（1）直接导入模块**

 		**import** **模块**

例：求列表中值为偶数的元素和

```python
#evensum.py
def func_sum(a_list):
    s=0
    for i in range(0,len(a_list)):
        if a_list[i]%2==0:
            s=s+a_list[i]
    return s
```

```python
import evensum
a_list=[3,54,65,76,45,34,100,-2]
s=evensum.func_sum(a_list)
print("sum=",s)


#sum= 262
```

**（2）导入模块中的函数**

​		 **from** **模块名** **import** **函数名**

```python
from evensum import func_sum
a_list=[3,54,65,76,45,34,100,-2]
s=func_sum(a_list)
print("sum=",s)

#sum= 262
```

**（3）导入模块中的所有函数**

​		**from 模块名 import***

```python
from evensum import *
a_list=[3,54,65,76,45,34,100,-2]
s=func_sum(a_list)
print("sum=",s)

#sum= 262
```



#### 9.5.3Python程序结构

Python程序通常由一个**主程序**及**多个模块**组成。

**主程序：** 程序的主控流程，是执行程序的启动文件，属于顶层文件

**多个模块：** 是函数库，相当于子程序；模块是用户自定义函数的集合体；调用模块中定义的函数来调用应用程序的功能，还可以调用标准库模块；模块还可以调用其他模块或标准库模块定义的函数

![image-20220809102459326](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809102459326.png)



**例如：**

![image-20220809102609120](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809102609120.png)





## 10、文件

### 10.1文件概述

文件：存储在外部存储介质上的数据集合。

**主文件名〖.扩展名〗**

例如：程序文件中保存着程序，数据文件中保存着数据。



**文件的分类**

1、根据文件依附的介质，可分为**普通文件**和**设备文件**。

2、根据文件的组织方式，可分为**顺序读写文件**（按照文件所存储的数据的顺序从头到尾进行访问。）和**随机读写文件**（存储的数据通常是有结构的，每条数据记录长度相等，因此可以通过计算直接访问文件中的特定记录。）。

3、根据文件的存储形式，可分为**ASCII码文件**（文本文件）和**二进制文件**。

4、按照操作系统对磁盘文件的读写方式，文件系统可分为**缓冲文件系统**和**非缓冲文件系统**。

**缓冲区：**为了提高程序访问文件的速度而开辟的一块内存，大小

通常为512字节。



**Python语言的文件处理函数：**

• 带缓冲区的标准I/O函数

• 不带缓冲的系统I/O函数



**标准I/O函数的执行过程**

![image-20220809201147172](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809201147172.png)



**总结：**

**第一，文件是存储在外部存储介质上的数据集合,可使用文件名来访问文件,程序将文件当作数据流来处理。**


**第二，文件按依附的介质可分为普通文件和设备文件,按组织方式可分为顺序读写文件和随机读写文件,按存储形式可分为ASCII码文件和二进制文件。**

**第三，程序在使用文件时,可使用标准I/0文件处理函数或系统I/0文件处理函数,它们的区别是是否使用缓冲区,大部分Python程序使用带缓冲区的标准I/0文件处理函数。**





### 10.2文件的打开和关闭

**文件的操作流程**

![image-20220809203606858](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809203606858.png)

**文件的打开函数**

文件对象=open(文件名[,打开方式，缓冲区])



**函数功能**:按指定的文件使用方式打开指定的文件。

​		若文件打开成功，为该文件分配一个文件缓冲区;

​		若文件打开失败，返回NULL。



例如：

**fp=open**(“e: \ \program\ \input.txt”,”r”)

或			**fp=open**(“input.txt"，”r”)

或			str=“input. txt”

​				**fp=open**(str,”r”)



**文件的分类**

**第一种“r”只读方式:**为文件打开文件。若文件不存在，返回NULL。

**第二种“w”只写方式:**为写文件打开文件。若文件不存在，则建立一个新文件;若文件已存在，则清空文件。

**第三种“a”追加方式:**为写文件打开文件。若文件已存在，则保持原来文件的内容，将新的数据增加到原来数据的后面;若文件不存在，则建立一个新文件。
![image-20220809204433867](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809204433867.png)



缓冲区设置

![image-20220809204543029](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809204543029.png)

**X = open( 'c:\txt\somefile.txt,r' ,buffering=1024)**



文件对象属性

![image-20220809204634023](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809204634023.png)

引用方法：

**文件对象名.属性名**

例：

![image-20220809204739817](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809204739817.png)



**文件的关闭函数**

文件关闭函数:**文件对象.close()**

函数功能:关闭文件对象指定的文件，释放该文件的缓冲区。

​				若文件关闭成功，则返回0;否则，则返回非0值。

例如:如果之前有语句

​		fp=open(“input.txt" ，”r”)

​		关闭文件时就可以使用语句: fp.close()



### 10.3文本文件的读写

#### 10.3.1文本文件的读取

**（1）read()方法**

​						 **文件对象.read()**

```python
fp = open("d:\\file1.txt", "r")
string1=fp.read()
print("Read Line: %s" % (string1))

#Read Line: There were bears everywhere!
#They were going to ruijin

```

![image-20220809210513305](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809210513305.png)

**（2）read()方法**

​						 **文件对象.read([size])**

```python
fp = open("d:\\file1.txt", "r")
string2=fp.read(10)
print("Read Line: %s" % (string2))

#Read Line: There were
```



**（3）readline()方法**

​							**文件对象.readline()**

```python
fp = open("d:\\file1.txt", "r")
string3=fp.readline()
print("Read Line: %s" % (string3))

#Read Line: There were bears everywhere!
```



**（4）readlines()方法**

​							**文件对象.readlines()**



```python
fp = open("d:\\file1.txt", "r")
string4=fp.readlines()
print("Read Line: %s" % (string4))

#Read Line: ['There were bears everywhere!\n', 'They were going to ruijin']


```



#### 10.3.2文本文件的写入

**（1）write()方法**

 					**文件对象. write (字符串)**

```python
fp=open("d:\\file1.txt", "w")
fp.write("Python")
#6

fp.write("Python programming")
#18

fp.close()
```

![image-20220809212216142](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809212216142.png)



**（2）writelines ()方法**

 								**文件对象. writelines (字符串元素的列表)**

```python
fp=open("d:\\file1.txt", "w")
fp.writelines(["Python","Python programming"] )
fp.close()
```



#### 10.3.3文本文件读写应用举例

例：从键盘输入若干个字符串，逐个将它们写入文件d:\\file1.txt的尾部，直到输入*时结束，然后从该文件中逐一读出字符串，并在屏幕上显示出来。

```python
a_list=[ ]
while True:
	s=input("输入若干字符：")
	if s=="*":
		break
	a_list.append(s+'\n')

fp=open("d:\\file1.txt","a")
fp.writelines(a_list)
fp.close()
fp=open("d:\\file1.txt","r")
str=fp.read()
fp.close()
print("输出文本文件内容:")
print(str)


'''
输入若干字符：linao*
输入若干字符：*
输出文本文件内容:
PythonPython programminglinao*
'''
```



### 10.4二进制文件的读写



1.通过struct模块的pack()方法把数字和bool值转换成字符串，然后用write()方法写入二进制文件中

2.用pickle模块的dump()方法直接把对象转换为字符串并存入文件中。



#### 10.4.1二进制文件写入——pack方法

**（1）pack()方法**

​			 **pack(格式串，数据对象表)**

格式字符

![image-20220809220016770](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220809220016770.png)

**二进制文件写入——pack方法**

```python
import struct
x=100
y=struct.pack('i',x)
y
#b'd\x00\x00\x00'

len(y)
#4

fp=open("e:\\file2.txt","wb")
fp.write(y)
#4

fp.close()



```

例1：将一个整数、一个浮点数和一个布尔型对象存入一个二进制文件中。

```python
import struct
i=12345
f=2017.2017
b=False
string=struct.pack('if?',i,f,b) 

fp=open("e:\\string1.txt","wb")
fp.write(string)
fp.close()
```

**pack()方法写入文件的内容  ---->  read(方法读出相应的字符串  ---->  unpack()方法还原数据**



#### 10.4.2二进制文件写入——dump方法

**（2）dump() 方法**

​						 **dump(数据，文件对象)**

```python
import pickle
x=100
fp=open("e:\\file3.txt","wb")
pickle.dump(x,fp) 
fp.close()

```

例2：使用dump方法将一个整数、一个浮点数和一个布尔型对

象存入一个二进制文件中。

```python
import pickle
i=12345
f=2017.2017
b=False
fp=open("e:\\string2.txt","wb")
pickle.dump(i,fp)
pickle.dump(f,fp)
pickle.dump(b,fp)
fp.close()
```

**dump()方法写入文件的内容  ---->  pickle模块的load()方法还原数据**



#### 10.4.3二进制文件读取——unpack方法

**（1）unpack ()方法**

​							 **unpack(格式串，字符串表)**

```python
import struct
fp=open("e:\\file2.txt","rb") 
y=fp.read()
x=struct.unpack('i',y)
x
#(100,)
```

例3：读取例1中写入的“string1.txt”文件内容

```python
import struct
fp=open("e:\\string1.txt","rb")
string=fp.read()
a_tuple=struct.unpack('if?',string)
print("a_tuple=",a_tuple)
i=a_tuple[0]
f=a_tuple[1]
b=a_tuple[2]
print("i=%d,f=%f"%(i,f))
print("b=",b)
fp.close()
```



#### 10.4.4二进制文件读取——load方法

**（2）load ()方法**

 				**load(文件对象)**

```
 import pickle
>>> fp=open("e:\\file3.txt","rb") 
>>> x=pickle.load(fp) 
>>> fp.close()
>>> x 
100
```



#### 10.4.5二进制文件写入——unpack方法

例4：读取例2写入的“string2.txt”文件内容。

```python
import pickle
fp=open("e:\\string2.txt","rb")
while True:
	n=pickle.load(fp)
	if(fp):
		print(n)
	else:
		break
fp.close()
```





## 11、Python标准库

### 11.1random库及其使用

#### 11.1.1Random库

随机数:在某次产生过程中是按照实验过程中表现的分布概率随机产生的，其结果是不可预测、不可见的计算机的伪随机数是由随机种子根据一定的计算方法计算出来的数值

import random



**Random库----random的基本方法**

![image-20220810201623932](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220810201623932.png)

**Random库----针对序列结构的方法**

![image-20220810201713199](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220810201713199.png)

**Random库----真值分布**

![image-20220810201806241](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220810201806241.png)



#### 11.1.2Random库常用方法----random ()

**(1) random()**
功能:返回- -个介于左闭右开[0.0, 1.0)区间的浮点数

```python
>>> import random
>>> random.random()
#0.8050901378898727

```

**注意:该语句每次运行的结果不同，但都介于0~1之间。**



#### 11.1.3Random库常用方法----seed ()

**(2) seed(a)**

功能:初始化伪随机数生成器，给随机数对象一个种子值， 用于产生随机序列。

例1:随机数应用举例

```python
from numpy import *
num=0
while(num < 5):
	random.seed(5)
	print(random.random())
	num += 1
```

**seed()函数使用时要注意:**

1、如果使用相同的seed()值，则每次生成的随即数都相同。

2、如果不设置函数的参数，则使用当前系统时间作为种子，此时每次生成的随机数因时间差异而不同。

3、设置的seed()值仅一次有效。



#### 11.1.4Random库常用方法-----randint ()

**(3) randint(a,b)**

功能:返回- -个a<= N < = b的随机整数N

```python
import random
random.randint(3,10)
#4
random.randint(3,10)
#7
```



#### 11.1.5Random库常用方法----randrange ()

**(4) randrange([start,]stop[,step])**

功能:从指定范围start~stop内,按指定步长step递增的集合中，获取一个随机整数

```python
>>> import random
>>> random.randrange(1,10,2)
>>> 3
>>> random.randrange(1,10,2)
>>> 9
```



#### 11.1.6Random库常用方法----choice ()

**(5) choice(seq)**

功能:从非空序列seq中随机选取一个元素

```python
import random
random.choice([1,2,3, 5, 9])
#5
random.choice('A String')
#A
```



#### 11.1.7Random库常用方法----shuffle ()

**(6) shuffle(x[, random])**

功能:随机打乱序列x内元素的排列顺序，返回随机排序后的序列使用shuffle()方法实现模拟洗牌程序。

```python
import random
list= [20, 16, 10, 5]
random.shuffle(list)
print( "随机排序列表: ",list)
random.shuffle(list)
print( "随机排序列表: ",list)

'''
随机排序列表:  [5, 16, 20, 10]
随机排序列表:  [10, 5, 20, 16]

'''
```



#### 11.1.8Random库常用方法----sample ()

**(7) sample(population, k)**

功能:从population样本或集合中随机抽取K个不重复的元素形成新的序列

```python
>>> random.sample([10, 20, 30, 40, 50]，k=4)
[30, 40, 50, 20]
>>> random.sample([10, 20, 30, 40, 50]，k=4)
[20, 50, 10, 40]
>>> random.sample([10, 20, 30, 40, 50], k=4)
[20, 40, 30, 50]
```

**注意：**sample()方法不会改变原有的序列，但shuffle()方法会直接改变原有序列。



#### 11.1.9Random库常用方法----unifrom ()

**(8) uniform(a,b)**

功能:返回-个介于a和b之间的浮点数

```python
>>> import random
>>> random.uniform(10,20)
#13.516894180425453
```



#### 11.1.10Random库应用举例

例3:用户从键盘输入两个整数,第一一个数是要猜的数n (n<10) ，第二个数作为随机种子，随机生成一个1~10的整数，如果该数不等于n,则再次生成随机数，如此循环，直至猜中数n,输出"N times to got it",其中N为猜测的次数。

```python
from random import*
n=int(input("请输入n的值 (1~10) : "))
m=int(input("请输入m的值: "))
count=1
seed(m)
b=randint(1,10)
while True
	if (b==n): 
		break
	count=count+1
	b=randint(1,10)
print("{} times to got it".format(count))

'''
请输入n的值 (1~10) : 5
请输入m的值: 6
4 times to got it
'''
```



### 11.2time库及其使用

**time库**

python中表示时间方法：

 时间戳，即从1975年1月1日00:00:00到现在的秒数

 格式化后的时间字符串

 时间struct_time 元组



**时间struct_time元组中元素主要有：**

**tm_year**：年

**tm_mon**：月

**tm_mday**：日

**tm_hour**：时

**tm_min**：分

**tm_sec**：秒

**tm_wday**：星期几，范围是0~6，0表示周日

**tm_yday**：一年中的第几天，范围是1 ~366

**tm_isdst**：是否是夏令时



#### 11.2.1时间获取

![image-20220810205713752](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220810205713752.png)





**时间获取——time()**

**（1）time() 函数**

功能：获取当前时间戳，返回值为浮点数，表示从1970年1月1日0点0分开始，到当前时间，一共经历了多少秒

```python
>>> import time
>>> time.time()

#1533554029.3566148
```

**时间获取——ctime()**

**（2）ctime()** **函数**

**功能：**获取当前时间，以字符串形式返回

```python
>>> import time
>>> time.ctime()
#'Wed Aug 10 23:41:34 2022'

>>> time.ctime(1533554029.3566148)
#'Mon Aug 6 19:13:49 2018
```

'

**时间获取——gmtime()**

**（3）gmtime() 函数**

**功能：**返回指定时间戳对应的*utc时间的struct_time对象格式

```python
>>> import time
>>> time.gmtime()

'''
time.struct_time(tm_year=2018, tm_mon=10, tm_mday=6, tm_hour=11, tm_min=18, tm_sec=21, tm_wday=5, tm_yday=279, tm_isdst=0
'''

```

**时间获取——localtime()**

**（4）localtime () 函数**

**功能：**返回以指定时间戳对应的本地时间的 struct_time对象格式

```python
>>> import time
>>> time.localtime(1533554029.3566148)

'''
time.struct_time(tm_year=2018, tm_mon=8, tm_mday=6, tm_hour=19, tm_min=13, tm_sec=49, tm_wday=0, tm_yday=218, tm_isdst=0)
'''

```

**时间获取——mktime()**

**（5）mktime (t) 函数**

**功能：**返回用秒数来表示时间的浮点数

```python
>>> import time
>>> t=(2018,8,36,17,25,35,1,48,58)
>>> time.mktime(t)

#1536139535.0
```



#### 11.2.2时间格式化

![image-20220810210647185](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220810210647185.png)



**时间格式化——strftime()**

**（1）time.strftime(tpl, ts)**

**功能：**将struct_time对象实例转换成字符串

**时间日期格式化控制符**

![image-20220810210802283](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220810210802283.png)



**时间格式化——strftime()**

```python
>>> import time
>>> time.strftime("%b %d %Y %H:%M:%S", time.gmtime())
#'Aug 10 2022 15:44:18'

>>> time.strftime("%B %d %Y %p %h:%M:%S", time.gmtime())
#'August 10 2022 PM Aug:44:42'
```

**时间格式化——strptime()**

**(2）strptime(str, tpl) **

**功能：**将时间字符串转换为struct_time时间对象

```python
>>> time.strptime("30 Nov 17", "%d %b %y")
'''
time.struct_time(tm_year=2017, tm_mon=11, tm_mday=30, tm_hour=0, tm_min=0, tm_sec=0, tm_wday=3, tm_yday=334, tm_isdst=-1)

'''

>>> time.strptime("Oct 06 2018 12:30:38", "%b %d %Y %H:%M:%S")
'''
time.struct_time(tm_year=2018, tm_mon=10, tm_mday=6, tm_hour=12, tm_min=30, tm_sec=38, tm_wday=5, tm_yday=279, tm_isdst=-1)
'''

```

**时间格式化——asctime()**

**（3）asctime([t])**

**功能：**将一个tuple或struct_time形式的时间（转换为时间字符串

```python
>>> t=time.localtime()
>>> time.asctime(t)

#'Wed Aug 10 23:46:04 2022'
```



#### 11.2.3程序计时

![image-20220810211416003](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220810211416003.png)



**程序计时——sleep()**

**（1）sleep(s)**

**功能：**暂停给定秒数后执行程序 

```python
>>> import time
>>> time.sleep( 5 ) 
```



**程序计时——perf_counter()**

**（2）perf_counter()**

**功能：**返回CPU计时器的精准时间（系统的运行时间），单位为秒

```python
>>> import time
>>> time.perf_counter()

#3132924.1484889
```



#### 11.2.4time库应用举例

例1：获取当前时间，然后再格式化当前时间输出，暂停两秒再获取当前时间，最后再格式化当前时间输出。

```python
import time
t=time.time()
print("now time is:{}".format(t))
m=time.localtime(t)
print("now time is:{}".format(m))
time.sleep(2)
t=time.time()
n=time.localtime(t)
print("now time is:{}".format(n))

'''
now time is:1660146495.6778948
now time is:time.struct_time(tm_year=2022, tm_mon=8, tm_mday=10, tm_hour=23, tm_min=48, tm_sec=15, tm_wday=2, tm_yday=222, tm_isdst=0)
now time is:time.struct_time(tm_year=2022, tm_mon=8, tm_mday=10, tm_hour=23, tm_min=48, tm_sec=17, tm_wday=2, tm_yday=222, tm_isdst=0)
'''
```



### 11.3turtle库及其使用

![image-20220810211907097](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220810211907097.png)



**turtle库**

![image-20220810211928224](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220810211928224.png)

**设置画布——screensize**

**（1）screensize(canvwidth, canvheight, bg)**

 **canvwidth** 表示设置的画布宽度（单位像素）

 **canvheight** 表示设置的画布高度（单位像素）

 bg表示设置的画布背景颜色

默认宽度300，高度400，背景颜色白色

```python
>>> import turtle
>>> turtle.screensize(800,600, "blue") 
>>> turtle.screensize() 
```

**设置画布——setup**

**（2）setup(width, height, startx, starty)**

**width** 表示画布宽度

**height** 表示画布高度

**startx** 表示画布左侧与屏幕左侧的像素距离

**starty** 表示画布顶部与屏幕顶部的像素距离

```python
>>>turtle.setup(width=0.6,height=0.6)
>>>turtle.setup(width=800,height=800, startx=100, starty=100) 
```



**画笔及绘制函数**

**控制小海龟绘图有很多函数，这些函数可以划分为4种：**

 画笔运动函数

 画笔控制函数

 全局控制函数

 其他函数



**画笔运动函数**

![image-20220810232710659](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220810232710659.png)

**画笔运动函数——setheading()**

**（1）setheading (angle)**

**功能：**按照angle角度逆时针改变海龟的行进方向

```python
>>> turtle.setheading(30)
```



**画笔运动函数——circle()**

**（1）circle（radius, extent, steps）**

 **radius ** 表示半径

 **extent** 表示绘制弧形的角度

 **steps** 表示阶数



```python
>>> turtle.circle(50) 

>>> turtle.circle(50,180) 

>>> turtle.circle(50,steps=4) 
```

**画笔控制函数**

![image-20220810233044590](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220810233044590.png)



**画笔控制函数——pencolor()**

**pencolor()** **：返回当前画笔颜色**

**pencolor(color)：参数color为颜色字符串或者RGB值**



```python
>>> turtle.pencolor()

'black'

>>> turtle.pencolor("grey")

>>> turtle.pencolor((255,0,0))
```



**全局控制函数**

![image-20220810233119505](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220810233119505.png)

**全局控制函数——write()**

**write(s,font)：给画布写文本信息**

**font基本形式为：**

**font=("font-ame",font_size,"font_type")**



```python
>>>turtle.write("hello") 

>>>turtle.write("hello",font = ("Times", 24, "bold"))
```

**画笔其他函数**

![image-20220810233158562](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220810233158562.png)



**画笔其他函数——mode()**

**mode(mode)**

**功能：设置乌龟运动的模式并执行重置**

**参数mode表示要设置的模式，有三种选项**

**”standard”**

**”logo”**

**”world”**

```python
>>> turtle.mode("logo")
```

绘制五角星

```python
import turtle
 
turtle.pensize(5)
turtle.pencolor("yellow")
turtle.fillcolor("red")
 
turtle.begin_fill()

for i in range(5):
	turtle.forward(200)
	turtle.right(144)
turtle.end_fill()

turtle.penup()
turtle.goto(-150,-120)
turtle.color("violet")
turtle.write("五角星", font=('Arial', 40, 'normal'))
```

![image-20220811000609811](C:\Users\林涛\AppData\Roaming\Typora\typora-user-images\image-20220811000609811.png)

------

