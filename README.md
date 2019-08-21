Go 语言
====
hello go world!<br>
----
<p>2017-10-15 begin</p>
  
### Go语言数据类型 ###
<pre>
在 Go 编程语言中，数据类型用于声明函数和变量。    
数据类型的出现是为了把数据分成所需**内存大小不同的数据**，编程的时候需要用大数据的时候才需要申请大内存，就可以充分利用内存。  
布尔型, 数字类型, 字符串类型, 派生类型 
</pre>
### Go语言变量###
变量来源于数学，是计算机语言中能储存计算结果或能表示值抽象概念。变量可以通过变量名访问。  
Go 语言变量名由字母、数字、下划线组成，其中**首个字母不能为数字**。  
声明变量的一般形式是使用 var 关键字：  
<pre>
第一种，指定变量类型，声明后若不赋值，使用默认值。
var v_name v_type**
v_name = value**
第二种，根据值自行判定变量类型。
var v_name = value
第三种，省略var, 注意 :=左侧的变量不应该是已经声明过的，
否则会导致编译错误。
v_name := value
// 例如
var a int = 10
var b = 10
c := 10
</pre>
---
### Go语言常量###
常量是一个简单值的标识符，**在程序运行时，不会被修改的量**。  
常量中的数据类型只可以是布尔型、数字型（整数型、浮点型和复数）和字符串型。  
常量的定义格式：
你可以省略类型说明符 [type]，  
因为编译器可以根据变量的值来推断其类型。
<pre>
显式类型定义： const b string = "abc"
隐式类型定义： const b = "abc"
</pre>

#### Go语言运算符####
运算符用于在程序运行时执行数学或逻辑运算。  
Go 语言内置的运算符有： 
>     算术运算符
>     关系运算符
>     逻辑运算符
>     位运算符
>     赋值运算符
>     其他运算符
接下来让我们来详细看看各个运算符的介绍。

算术运算符  
下表列出了所有Go语言的算术运算符。假定 A 值为 10，B 值为 20。

    运算符	描述	实例
    +	相加	A + B 输出结果 30
    -	相减	A - B 输出结果 -10
    *	相乘	A * B 输出结果 200
    /	相除	B / A 输出结果 2
    %	求余	B % A 输出结果 0
    ++	自增	A++ 输出结果 11
    --	自减	A-- 输出结果 9
    

关系运算符
下表列出了所有Go语言的关系运算符。假定 A 值为 10，B 值为 20。

    运算符	      描述	                实例
    ==	检查两个值是否相等，如果相等返回 True 否则返回 False。	(A == B) 为 False
    !=	检查两个值是否不相等，如果不相等返回 True 否则返回 False。	(A != B) 为 True
    >	检查左边值是否大于右边值，如果是返回 True 否则返回 False。	(A > B) 为 False
    <	检查左边值是否小于右边值，如果是返回 True 否则返回 False。	(A < B) 为 True
    >=	检查左边值是否大于等于右边值，如果是返回 True 否则返回 False。	(A >= B) 为 False
    <=	检查左边值是否小于等于右边值，如果是返回 True 否则返回 False。	(A <= B) 为 True

逻辑运算符  
下表列出了所有Go语言的逻辑运算符。假定 A 值为 True，B 值为 False。

    运算符	描述	实例
    &&	逻辑 AND 运算符。 如果两边的操作数都是 True，则条件 True，否则为 False。	(A && B) 为 False
    ||	逻辑 OR 运算符。 如果两边的操作数有一个 True，则条件 True，否则为 False。	(A || B) 为 True
    !	逻辑 NOT 运算符。 如果条件为 True，则逻辑 NOT 条件 False，否则为 True。

其他运算符
下表列出了Go语言的其他运算符。

    运算符	描述	实例
    &	返回变量存储地址	&a; 将给出变量的实际地址。
    *	指针变量。	*a; 是一个指针变量

#### Go语言条件语句####
条件语句需要开发者通过指定一个或多个条件，并通过测试条件是否为 true 来决定是否执行指定语句，并在条件为 false 的情况在执行另外的语句。  
<pre>
if ... else ...       （忽略）  
switch ...             多条件执行  
select ...             select 语句类似于 switch ...   但是select会随机执行一个可运行的case。
                       如果没有case可运行，它将阻塞，直到有case可运行。
</pre>

#### Go语言循环语句####
<pre>
循环类型	        描述
for 循环	        重复执行语句块
循环嵌套	        在 for 循环中嵌套一个或多个 for 循环
</pre>
循环控制语句
<pre>
控制语句	        描述
break 语句	经常用于中断当前 for 循环或跳出 switch 语句
continue 语句	跳过当前循环的剩余语句，然后继续进行下一轮循环。
goto 语句	将控制转移到被标记的语句。
</pre>
案例：无限循环
<pre>
package main
import "fmt"
func main() {
    for true  {
        fmt.Printf("这是无限循环。\n");
    }
}
</pre>
#### Go语言函数####
函数是基本的代码块，用于执行一个任务。  
Go 语言最少有个 main() 函数。  
你可以通过函数来划分不同功能，逻辑上每个函数执行的是指定的任务。  
函数声明告诉了编译器函数的名称，返回类型，和参数。  
Go 语言标准库提供了多种可动用的内置的函数。例如，len() 函数可以接受不同类型参数并返回该类型的长度。如果我们传入的是字符串则返回字符串的长度，如果传入的是数组，则返回数组中包含的元素个数。
<pre>
函数定义
Go 语言函数定义格式如下：
func function_name( [parameter list] ) [return_types] {
   函数体
}
函数定义解析：
func：函数由 func 开始声明
function_name： 函数名称，函数名和参数列表一起构成了函数签名。
parameter list：参数列表，参数就像一个占位符，当函数被调用时，你可以将值传递给参数，这个值被称为实际参数。参数列表指定的是参数类型、顺序、及参数个数。参数是可选的，也就是说函数也可以不包含参数。
return_types：  返回类型，函数返回一列值。return_types 是该列值的数据类型。有些功能不需要返回值，这种情况下 return_types 不是必须的。
函数体：函数定义的代码集合。
</pre>
** 函数调用**  
函数如果使用参数，该变量可称为函数的形参。  
形参就像定义在函数体内的局部变量。  
调用函数，可以通过两种方式来传递参数：  
**值传递:**   值传递是指在调用函数时将实际参数复制一份传递到函数中，这样在函数中如果对参数进行修改，将不会影响到实际参数。  
**引用传递:** 引用传递是指在调用函数时将实际参数的地址传递到函数中，那么在函数中对参数所进行的修改，将影响到实际参数。  
<pre>
package main
import "fmt"
func main() {
   /* 定义局部变量 */
   var a int = 100
   var b int = 200
   var ret int
   /* 调用函数并返回最大值 */
   ret = max(a, b)
   fmt.Printf( "最大值是 : %d\n", ret )
}
/* 函数返回两个数的最大值 */
func max(num1, num2 int) int {
   /* 定义局部变量 */
   var result int
   if (num1 > num2) {
      result = num1
   } else {
      result = num2
   }
   return result 
}
</pre>
**乘法口诀表**
<pre>
package main
import (
	"fmt"
	"strconv"
)
func add(a, b int) int {
	return a + b
}
func multiplicationTable() {
	for i := 1; i <= 9; i++ {
		for j := 1; j <= i; j++ {
			var ret string
			if i*j < 10 && j != 1 {
				ret = " " + strconv.Itoa(i*j)
			} else {
				ret = strconv.Itoa(i * j)
			}
			fmt.Print(j, " * ", i, " = ", ret, "   ")
		}
		fmt.Print("\n")
	}
}
func main() {
	multiplicationTable()
}
</pre>
####GO语言变量作用域####
作用域为已声明标识符所表示的常量、类型、变量、函数或包在源代码中的作用范围。  
GO 语言中变量可以在三个地方声明：  
函数内定义的变量称为**局部变量**  
函数外定义的变量称为**全局变量**  
函数定义中的变量称为**形式参数**   
**局部变量**
<PRE>
...
FUNC MAIN() {
   /* 声明局部变量 */
   VAR A, B INT 
   /* 初始化参数 */
   A = 10
   B = 20
   FMT.PRINTF ("结果： A = %D, B = %D\N", A, B)
}
</PRE>
**全局变量**
在函数体外声明的变量称之为全局变量，全局变量可以在整个包甚至外部包（被导出后）使用。
全局变量可以在任何函数中使用，以下实例演示了如何使用全局变量：
<PRE>
PACKAGE MAIN
IMPORT "FMT"
VAR G INT         /* 声明全局变量 */
FUNC MAIN() {
   VAR A, B INT   /* 声明局部变量 */
   A = 10         /* 初始化参数 */
   B = 20
   G = A + B
   FMT.PRINTF("结果： A = %D, B = %D AND G = %D\N", A, B, G)
}
</PRE>
GO 语言程序中全局变量与局部变量名称可以相同，但是函数内的局部变量会被优先考虑。   
**形式参数**   
形式参数会作为函数的局部变量来使用。
####GO语言数组####
数组是具有相同唯一类型的一组已编号且长度固定的数据项序列，这种类型可以是任意的原始类型例如整形、字符串或者自定义类型。  
相对于去声明NUMBER0, NUMBER1, ..., AND NUMBER99的变量，使用数组形式NUMBERS[0], NUMBERS[1] ..., NUMBERS[99]更加方便且易于扩展。  
数组元素可以通过索引（位置）来读取（或者修改），索引从0开始，第一个元素索引为 0，第二个索引为 1，以此类推  
**声明数组**  
GO 语言数组声明需要指定元素类型及元素个数
<PRE>
VAR VARIABLE_NAME [SIZE] VARIABLE_TYPE
以上为一维数组的定义方式。数组长度必须是整数且大于 0。
例如以下定义了数组 BALANCE 长度为 10 类型为 FLOAT32：
VAR BALANCE [10] FLOAT32
</PRE>
**初始化数组**  
以下演示了数组初始化：  
<PRE>
VAR BALANCE = [5]FLOAT32{1000.0, 2.0, 3.4, 7.0, 50.0}
初始化数组中 {} 中的元素个数不能大于 [] 中的数字。
如果忽略 [] 中的数字不设置数组大小，GO 语言会根据元素的个数来设置数组的大小：
VAR BALANCE = [...]FLOAT32{1000.0, 2.0, 3.4, 7.0, 50.0}
该实例与上面的实例是一样的，虽然没有设置数组的大小。
BALANCE[4] = 50.0
以上实例读取了第五个元素。数组元素可以通过索引（位置）来读取（或者修改），
索引从0开始，第一个元素索引为 0，第二个索引为 1，以此类推。
</PRE>
![](HTTP://WWW.RUNOOB.COM/WP-CONTENT/UPLOADS/2015/06/ARRAY_PRESENTATION.JPG)  

**访问数组元素**  
数组元素可以通过索引（位置）来读取。格式为数组名后加中括号，中括号中为索引的值。例如
<pre>
var salary float32 = balance[9]
</pre>
以上实例读取了数组balance第10个元素的值。  
以下演示了数组完整操作（声明、赋值、访问）的实例：
<pre>
package main
import "fmt"
func main() {
	var n [10]int /* n 是一个长度为 10 的数组 */
	var i int
	/* 为数组 n 初始化元素 */
	for i = 0; i < 10; i++ {
		n[i] = i + 100 /* 设置元素为 i + 100 */
		fmt.Printf("N is [%d] = %d\n", i, n[i])
	}
}
</pre>
**二维数组**  
二维数组是最简单的多维数组，二维数组本质上是由一维数组组成的。二维数组定义方式如下    
二维数组通过指定坐标来访问。如数组中的行索引与列索引，例如：  
int val = a[2][3]    
以上实例访问了二维数组 val 第三行的第四个元素。  
二维数组可以使用循环嵌套来输出元素：
<pre>
package main
import "fmt"
func main() {
   /* 数组 - 5 行 2 列*/
   var a = [5][2]int{ {0,0}, {1,2}, {2,4}, {3,6},{4,8}}
   var i, j int
   /* 输出数组元素 */
   for  i = 0; i < 5; i++ {
      for j = 0; j < 2; j++ {
         fmt.Printf("a[%d][%d] = %d\n", i,j, a[i][j] )
      }
   }
}
</pre>
#### Go 语言指针####
Go 语言中指针是很容易学习的，Go 语言中使用指针可以更简单的执行一些任务。  
接下来让我们来一步步学习 Go 语言指针。  
我们都知道，变量是一种使用方便的占位符，用于引用计算机内存地址。  
Go 语言的取地址符是 &，放到一个变量前使用就会返回相应变量的内存地址。  
以下实例演示了变量在内存中地址：  
<pre>
package main
import "fmt"
func main() {
   var a int = 10   
   fmt.Printf("变量的地址: %x\n", &a  )
}

执行以上代码输出结果为：
变量的地址: 20818a220
</pre>
现在我们已经了解了什么是内存地址和如何去访问它。接下来我们将具体介绍指针。  
**什么是指针**  
一个指针变量指向了一个值的内存地址。  
类似于变量和常量，在使用指针前你需要声明指针。指针声明格式如下：  
**如何使用指针**  
指针使用流程：  
定义指针变量。  
为指针变量赋值。  
访问指针变量中指向地址的值。  
在指针类型前面加上 * 号（前缀）来获取指针所指向的内容。  
<pre>
package main
import "fmt"
func main() {
   var a int= 20   /* 声明实际变量 */
   var ip *int        /* 声明指针变量 */
   ip = &a  /* 指针变量的存储地址 */
   fmt.Printf("a 变量的地址是: %x\n", &a  )
   /* 指针变量的存储地址 */
   fmt.Printf("ip 变量储存的指针地址: %x\n", ip )
   /* 使用指针访问值 */
   fmt.Printf("*ip 变量的值: %d\n", *ip )
}

以上实例执行输出结果为：
a   变量的地址是: 20818a220
ip  变量储存的指针地址: 20818a220
*ip 变量的值: 20
</pre>
**Go 空指针**  
当一个指针被定义后没有分配到任何变量时，它的值为 nil。  
nil 指针也称为空指针。  
nil在概念上和其它语言的null、None、nil、NULL一样，都指代零值或空值。  
一个指针变量通常缩写为 ptr。
查看以下实例：
<pre>
package main
import "fmt"
func main() {
   var  ptr *int
   fmt.Printf("ptr 的值为 : %x\n", ptr  )
}

以上实例输出结果为：
ptr 的值为 : 0

空指针判断：
if(ptr != nil)     /* ptr 不是空指针 */
if(ptr == nil)     /* ptr 是空指针 */
</pre>
**Go 语言指针数组**  
在我们了解指针数组前，先看个实例，定义了长度为 3 的整型数组：  
有一种情况，我们可能需要保存数组，这样我们就需要使用到指针。  
以下声明了整型指针数组：  
<pre>
var ptr [MAX]*int;  
</pre>
ptr 为整型指针数组。因此每个元素都指向了一个值。以下实例的三个整数将存储在指针数组中：
<pre>
package main
import "fmt"
const MAX int = 3
func main() {
   a := []int{10,100,200}
   var i int
   for i = 0; i < MAX; i++ {
      fmt.Printf("a[%d] = %d\n", i, a[i] )
   }
}

以上代码执行输出结果为：
a[0] = 10
a[1] = 100
a[2] = 200
</pre>
#### Go 语言结构体####
Go 语言中数组可以存储同一类型的数据，但在结构体中我们可以为不同项定义不同的数据类型。  
结构体是由一系列具有相同类型或不同类型的数据构成的数据集合。  
结构体表示一项记录，比如保存图书馆的书籍记录，每本书有以下属性：  
**- Title ：标题  
- Author ： 作者  
- Subject：学科  
- ID：     书籍ID**    

**定义结构体**  
结构体定义需要使用 type 和 struct 语句。  
struct 语句定义一个新的数据类型，结构体有中有一个或多个成员。  
type 语句设定了结构体的名称。  
结构体的格式如下：
<pre>
type struct_variable_type struct {
   member definition;
   member definition;
   ...
   member definition;
}
</pre>
一旦定义了结构体类型，它就能用于变量的声明，语法格式如下：
<pre>
variable_name := structure_variable_type {value1, value2...valuen}
或
variable_name := structure_variable_type { key1: value1, key2: value2..., keyn: valuen}
</pre>
实例如下：
<pre>
package main
import "fmt"
type Books struct {
   title   string
   author  string
   subject string
   book_id int
}
func main() {
    // 创建一个新的结构体
    fmt.Println(Books{"Go 语言", "www.runoob.com", "Go 语言教程", 6495407})
    // 也可以使用 key => value 格式
    fmt.Println(Books{title: "Go 语言", author: "www.runoob.com", subject: "Go 语言教程", book_id: 6495407})
    // 忽略的字段为 0 或 空
   fmt.Println(Books{title: "Go 语言", author: "www.runoob.com"})
}

输出结果为：
{Go 语言 www.runoob.com Go 语言教程 6495407}
{Go 语言 www.runoob.com Go 语言教程 6495407}
{Go 语言 www.runoob.com  0}
</pre>
** 访问结构体成员**  
如果要访问结构体成员，需要使用点号 . 操作符，格式为：  
结构体.成员名"   
结构体类型变量使用 struct 关键字定义，实例如下：  
<pre>
package main
import "fmt"
type Books struct {
   title string
   author string
   subject string
   book_id int
}

func main() {
   var Book1 Books        /* 声明 Book1 为 Books 类型 */
   /* book 1 描述 */
   Book1.title = "Go 语言"
   Book1.author = "www.runoob.com"
   Book1.subject = "Go 语言教程"
   Book1.book_id = 6495407

   /* 打印 Book1 信息 */
   fmt.Printf( "Book 1 title : %s\n", Book1.title)
   fmt.Printf( "Book 1 author : %s\n", Book1.author)
   fmt.Printf( "Book 1 subject : %s\n", Book1.subject)
   fmt.Printf( "Book 1 book_id : %d\n", Book1.book_id)
}

以上实例执行运行结果为：
Book 1 title : Go 语言
Book 1 author : www.runoob.com
Book 1 subject : Go 语言教程
Book 1 book_id : 6495407
</pre>
####Go语言切片(Slice)####
Go 语言切片是对数组的抽象。    
Go 数组的长度不可改变，在特定场景中这样的集合就不太适用，  Go中提供了一种灵活，功能强悍的内置类型切片("动态数组"),与数组相比切片的长度是不固定的，可以追加元素，在追加时可能使切片的容量增大。  
定义切片：你可以声明一个未指定大小的数组来定义切片：    
<pre>
var identifier []type
</pre>
切片不需要说明长度。
或使用make()函数来创建切片:  
<pre>
var slice1 []type = make([]type, len)
</pre>
也可以简写为
<pre>
slice1 := make([]type, len)
</pre>
len() 和 cap() 函数  
切片是可索引的，并且可以由 **len() 方法获取长度**。  
切片提供了计算容量的方法 **cap() 可以测量切片最长可以达到多少**  
**切片提供了计算容量的函数 cap() 可以测量切片最长可以达到多少：它等于切片的长度 + 数组除切片之外的长度。如果 s 是一个切片，cap(s) 就是从 s[0] 到数组末尾的数组长度。切片的长度永远不会超过它的容量，所以对于 切片 s 来说该不等式永远成立：0 <= len(s) <= cap(s)**    
优点 因为切片是引用，所以它们不需要使用额外的内存并且比使用数组更有效率，所以在 Go 代码中 切片比数组更常用。  
以下为具体实例：
<pre>
package main
import "fmt"
func main() {
	var numbers = make([]int, 3, 5)  //非空
	//var numbers []int   //空切片
    //numbers := []int{0,1,2,3,4,5,6,7,8}  //数组切片
	printSlice(numbers)
	if numbers == nil { fmt.Printf("切片是空的") }
}
func printSlice(x []int) {
	fmt.Printf("len=%d cap=%d slice=%v\n", len(x), cap(x), x)
}
</pre>
**append() 和 copy() 函数**  
如果想增加切片的容量，我们必须创建一个新的更大的切片并把原分片的内容都拷贝过来。  
下面的代码描述了从拷贝切片的 copy 方法和向切片追加新元素的 append 方法。
<pre>
package main
import "fmt"
func main() {
   var numbers []int
   printSlice(numbers)
   /* 允许追加空切片 */
   numbers = append(numbers, 0)
   printSlice(numbers)
   /* 向切片添加一个元素 */
   numbers = append(numbers, 1)
   printSlice(numbers)
   /* 同时添加多个元素 */
   numbers = append(numbers, 2,3,4)
   printSlice(numbers)
   /* 创建切片 numbers1 是之前切片的两倍容量*/
   numbers1 := make([]int, len(numbers), (cap(numbers))*2)
   /* 拷贝 numbers 的内容到 numbers1 */
   copy(numbers1,numbers)
   printSlice(numbers1)   
}
func printSlice(x []int){
   fmt.Printf("len=%d cap=%d slice=%v\n",len(x),cap(x),x)
}
//------------------------------------------
以上代码执行输出结果为：
len=0 cap=0 slice=[]
len=1 cap=1 slice=[0]
len=2 cap=2 slice=[0 1]
len=5 cap=6 slice=[0 1 2 3 4]
len=5 cap=12 slice=[0 1 2 3 4]
</pre>
#### Go 语言范围(Range) ####  
Go 语言中 range 关键字用于 **for 循环中迭代数组(array)、切片(slice)、通道(channel)或集合(map)的元素**。    
在数组和切片中它返回元素的索引和索引对应的值，在集合中返回 key-value 对的 key 值。    
KV 数据结构  
<pre>
package main
import "fmt"
func main() {
	nums := []int{2, 3, 4}
	sum := 0
	for _, num := range nums {
		sum += num
		fmt.Println("index:", num)
	}
	fmt.Println("sum:", sum)
///K V 结构数组遍历
	kvs := []int{2, 3, 4, 5}
	for k, v := range kvs {
		fmt.Printf("K is: %d -> V is: %d\n", k, v)
	}
}
// K V string
	name1 := []string{"aaaa", "bbbb", "cccc", "dddd", "eeee"}
	for k, v := range name1 {
		fmt.Println("Number", k, v)
	}

这两个都是仅 for 循环内部可见的局部变量。
如果你只关心值，可以这么使用：
for _, value := range map1 {
    ...
}
如果只想获取 key，你可以这么使用：
for key := range map1 {
    fmt.Printf("key is: %d\n", key)
}
//-------输出结构-------
index: 2
index: 3
index: 4
sum: 9
K is: 0 -> V is: 2
K is: 1 -> V is: 3
K is: 2 -> V is: 4
K is: 3 -> V is: 5
Number 0 aaaa
Number 1 bbbb
Number 2 cccc
Number 3 dddd
Number 4 eeee
</pre>
#### Go 语言Map(集合)####
map 是一种特殊的数据结构：一种元素对（pair）的无序集合，pair 的一个元素是 key，对应的另一个元素是 value，所以这个结构也称为关联数组或字典。这是一种快速寻找值的理想结构：给定 key，对应的 value 可以迅速定位。  
map 这种数据结构在其他编程语言中也称为字典（Python）、hash 和 HashTable 等。  
**概念**  
map 是引用类型，可以使用如下声明：  
`注意 不要使用 new，永远用 make 来构造 map`  
<pre>
var map1 map[keytype]valuetype
var map1 map[string]int

map 的初始化：var map1 = make(map[keytype]valuetype)
或者简写为：     map1 := make(map[keytype]valuetype)
-----------------------------
（[keytype] 和 valuetype 之间允许有空格，但是 gofmt 移除了空格）
</pre>
在声明的时候不需要知道 map 的长度，map 是可以动态增长的。  
未初始化的 map 的值是 nil。  
key 可以是任意可以用 == 或者 != 操作符比较的类型，比如 string、int、float。  
所以数组、切片和结构体不能作为 key   
(译者注：含有数组切片的结构体不能作为 key，只包含内建类型的 struct 是可以作为 key 的），但是指针和接口类型可以。如果要用结构体作为 key 可以提供 Key() 和 Hash() 方法，这样可以通过结构体的域计算出唯一的数字或者字符串的 key。  
map 传递给函数的代价很小：在 32 位机器上占 4 个字节，64 位机器上占 8 个字节，  
无论实际上存储了多少数据。**通过 key 在 map 中寻找值是很快的，比线性查找快得多**，但是仍然比从数组和切片的**索引中直接读取要慢 100 倍**；所以如果你很在乎性能的话还是建议用切片来解决问题。  
**map 容量**  
和数组不同，map 可以根据新增的 key-value 对动态的伸缩，因此它不存在固定长度或者最大限制。但是你也可以选择标明 map 的初始容量 capacity，  
就像这样：make(map[keytype]valuetype, **cap**)。  
例如：
<pre>
map2 := make(map[string]float32, 100)
</pre>

<pre>
package main
import "fmt"

func main() {
	var value int
	var isPresent bool

	map1 := make(map[string]int)
	map1["New Delhi"] = 55
	map1["Beijing"] = 20
	map1["Washington"] = 25
	value, isPresent = map1["Beijing"]
	if isPresent {
		fmt.Printf("The value of \"Beijing\" in map1 is: %d\n", value)
	} else {
		fmt.Printf("map1 does not contain Beijing")
	}
    //如果你只是想判断某个 key 是否存在而不关心它对应的值到底是多少，你可以这么做：    或者和 if 混合使用：
	if _, ok := map1["Beijing"]; ok {
		fmt.Println("Hello world")
	} else {
		fmt.Printf("map1 111111111111111111111111111")
	}
	value, isPresent = map1["Paris"]
	fmt.Printf("Is \"Paris\" in map1 ?: %t\n", isPresent)
	fmt.Printf("Value is: %d\n", value)

	// delete an item:从 map1 中删除 key1：如果 key1 不存在，该操作不会产生错误。
	delete(map1, "Washington")
	value, isPresent = map1["Washington"]
	if isPresent {
		fmt.Printf("The value of \"Washington\" in map1 is: %d\n", value)
	} else {
		fmt.Println("map1 does not contain Washington")
	}
}
======================================
go run mapifok.go
The value of "Beijing" in map1 is: 20
Hello world
Is "Paris" in map1 ?: false
Value is: 0
map1 does not contain Washington
</pre>
#### Go 包 package ####
像 fmt、os 等这样具有常用功能的内置包在 Go 语言中有 150 个以上，它们被称为标准库
**regexp 包**
我们将在字符串中对正则表达式进行匹配。  
如果是简单模式，使用 Match 方法便可：   
```
ok, _ := regexp.Match(pat, []byte(searchIn))
```
简单引用  
```
package main
import (
    "fmt"
    "regexp"
)
// 判断在 b 中能否找到正则表达式 pattern 所匹配的子串 
// pattern：要查找的正则表达式 
// b：要在其中进行查找的 []byte 
// matched：返回是否找到匹配项 
// err：返回查找过程中遇到的任何错误 
// 此函数通过调用 Regexp 的方法实现
// func Match(pattern string, b []byte) (matched bool, err error) 
func main() {
  fmt.Println(regexp.Match("[a-zA-Z]+", []byte("Hello World!"))) 
}
```
高级应用详见：[REGEXP复杂应用](https://github.com/gouki777/golang/blob/master/regexp)

**锁和 sync 包**
在一些复杂的程序中，通常通过不同线程执行不同应用来实现程序的并发。当不同线程要使用同一个变量时，经常会出现一个问题：无法预知变量被不同线程修改的顺序！(这通常被称为资源竞争，指不同线程对同一变量使用的竞争) 显然这无法让人容忍，那我们该如何解决这个问题呢？  
经典的做法是一次只能让一个线程对共享变量进行操作。当变量被一个线程改变时 (临界区)，我们为它上锁，直到这个线程执行完成并解锁后，其他线程才能访问它。  
特别是我们之前章节学习的 map 类型是不存在锁的机制来实现这种效果 (出于对性能的考虑)，所以 `map 类型是非线程安全的。当并行访问一个共享的 map 类型的数据，map 数据将会出错。`  
在 Go 语言中这种锁的机制是通过 sync 包中 Mutex 来实现的。sync 来源于 "synchronized" 一词，这意味着线程将有序的对同一变量进行访问  
sync.Mutex 是一个互斥锁，它的作用是守护在临界区入口来确保同一时间只能有一个线程进入临界区  
