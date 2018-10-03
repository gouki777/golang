Go 语言
====
hello go world!<br>
----
<p>2017-10-15 begin</p>
###Go语言数据类型###
在 Go 编程语言中，数据类型用于声明函数和变量。  
数据类型的出现是为了把数据分成所需**内存大小不同的数据**，编程的时候需要用大数据的时候才需要申请大内存，就可以充分利用内存。  

布尔型, 数字类型, 字符串类型, 派生类型 
###Go语言变量###
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
###Go语言常量###
常量是一个简单值的标识符，**在程序运行时，不会被修改的量**。  
常量中的数据类型只可以是布尔型、数字型（整数型、浮点型和复数）和字符串型。  
常量的定义格式：
你可以省略类型说明符 [type]，  
因为编译器可以根据变量的值来推断其类型。
<pre>
显式类型定义： const b string = "abc"
隐式类型定义： const b = "abc"
</pre>

####Go语言运算符####
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

####Go语言条件语句####
条件语句需要开发者通过指定一个或多个条件，并通过测试条件是否为 true 来决定是否执行指定语句，并在条件为 false 的情况在执行另外的语句。  
<pre>
if ... else ...       （忽略）  
switch ...             多条件执行  
select ...             select 语句类似于 switch ...   但是select会随机执行一个可运行的case。
                       如果没有case可运行，它将阻塞，直到有case可运行。
</pre>

####Go语言循环语句####
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
####Go语言函数####
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
**函数调用**
函数如果使用参数，该变量可称为函数的形参。  
形参就像定义在函数体内的局部变量。  
调用函数，可以通过两种方式来传递参数：  
**值传递:** 值传递是指在调用函数时将实际参数复制一份传递到函数中，这样在函数中如果对参数进行修改，将不会影响到实际参数。  
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