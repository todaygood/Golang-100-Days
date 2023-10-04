# golang中的关键字


## 定义变量

const,var
golang中var a int 这种, 或者 a:= 3 这种；

在go中，函数的声明可以放在调用函数的后面. 这跟C不一样。

## DataType
struct,map
interface

Types:
	bool byte complex64 complex128 error float32 float64
	int int8 int16 int32 int64 rune string
	uint uint8 uint16 uint32 uint64 uintptr

Constants:
	true false iota

Zero value:
	nil

### Functions:
	append cap close complex copy delete imag len
	make new panic print println real recover



### condition
if , else , 

select


# package management

import, package


## Function

make,cap,

len()数组， python和golang中的用法是一样的。

main函数的参数，必须使用os.Argus[] 数组来获取；

https://www.kancloud.cn/liupengjie/go/570013

init和main函数都不能有任何参数，任何返回值。

init函数用于包(package)的初始化，该函数是go语言的一个重要特性。


### 执行顺序

https://www.jianshu.com/p/8a8a1b5b775f


### Parameters

... 用于不定参数 https://blog.csdn.net/jeffrey11223/article/details/79166724
ref three_points.go
 

## range 用法

golang中的range用法：

for i,item = range 数组{
}

python 中的range用法：
sum = 0
for i in range(100):
	sum += i

## delete 用法

删除一个字典中key的元素
delete (map,key)


## print 

精确控制格式使用fmt.Printf，否则使用fmt.Print或者fmt.Println， 这两函数参数中加逗号打印出来就会有空格, 不识别"%v"这种格式字符串。


## 指针

跟C的指针用法类似。
golang的指针不使用符号 "->", 只有"&","*"两个符号可以用。

ref: http://www.runoob.com/go/go-pointers.html

## 接口

/* 定义接口 */
type interface_name interface {
   method_name1 [return_type]
   method_name2 [return_type]
   method_name3 [return_type]
   ...
   method_namen [return_type]
}

/* 定义结构体 */
type struct_name struct {
   /* variables */
}

/* 实现接口方法 */
func (struct_name_variable struct_name) method_name1() [return_type] {
   /* 方法实现 */
}
...
func (struct_name_variable struct_name) method_namen() [return_type] {
   /* 方法实现*/
}

接口的方法和普通func的区别：
func 和 函数名 之间有一个括号, 声明struct , 如：( struct变量)


## sizeof 

使用unsafe.Sizeof()来获得clang中的sizeof 效果。 

 m := Man{Name:"John", Age:20}

fmt.Println("man size:", unsafe.Sizeof(m))


## json.Marshal()

把struct变成json字符串,使用json.Marshal

## struct tag 

知识点： 

1. 反射 , reflection 

2. json , Mashal , Unmashal

Tag 规则
Tag 本身是一个字符串，但字符串中却是，以空格分隔的 key:value 对 。
key: 必须是非空字符串，字符串不能包含控制字符、空格、引号、冒号。
value: 以双引号标记的字符串
注意：冒号前后不能有空格

————————————————
原文作者：水墨先生
转自链接：https://learnku.com/articles/61564
 

Go语言之旅：Struct Tag的介绍及用法
https://cloud.tencent.com/developer/article/1496468


## append 

len()
cap()
make()
append()


## 打印变量类型的方法


1.使用reflect的TypeOf方法
模块是："reflect"

fmt.Println(reflect.TypeOf(var)) 
切片类型的输出



2.使用Printf中的占位符%T
占位符     说明                           举例                   输出
%T      相应值的类型的Go语法表示       Printf("%T", people)   main.Human
————————————————
版权声明：本文为CSDN博主「火山彬」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/m0_37965811/article/details/117618890


## 语言的跨平台性，平台即OS,如Windows, Linux

1. 计算机程序与机器的硬件平台绑定，如：汇编语言，每个硬件平台有自己的汇编语言，如intel x86、ARM 

2. 程序与OS绑定， 如C/C++, 编译器在Windows 和Linux不一样，

3. 程序与编译器、解释器绑定， 如Java,Python，Golang, 这个时候就可以称之为"跨平台语言" , Java是“一次编译，到处运行” 

4. 跨平台语言里面也有差异， 

   1) java语言跨平台的原理： 只要在需要运行java应用程序的操作系统上，先安装一个JAVA虚拟机（JVM Java Virtual Machine）即可。由JVM来负责Java程序在该系统中 的运行。
      Java语言是跨平台的，但JVM不是跨平台的，应为针对不同的操作系统，JAVA提供了不同的JVM，而各个操作系统的可执行文件是不同的。
	  JVM是运行所有Java程序的抽象计算机，是Java语言的运行环境，它是 Java 最具吸引力的特性之一，JVM读取并处理编译过的与平台无关的字节码(class)文件。

   2）Go语言是一种编译型语言，没有虚拟机。虚拟机主要是指解释型语言的执行环境，而Go语言的执行方式是先编译成机器码后直接执行，因此不需要虚拟机。此外，Go语言的运行时系统（runtime）可以看作是一种类似于虚拟机的东西，它提供了垃圾收集、调度器等功能，但它并不是一个完整的虚拟机。 golang的标准库屏蔽了os的底层细节。

	  关于go runtime，可参见： https://developer.aliyun.com/article/396978 ， https://blog.csdn.net/futurewu/article/details/104692651

	  尽管 Go 编译器产生的是本地可执行代码，这些代码仍旧运行在 Go 的 runtime（这部分的代码可以在 runtime 包中找到）当中。这个 runtime 类似 Java 和 .NET 语言所用到的虚拟机，它负责管理包括内存分配、垃圾回收（第 10.8 节）、栈处理、goroutine、channel、切片（slice）、map 和反射（reflection）等等。
      runtime 主要由 C 语言编写（Go 1.5 开始自举），并且是每个 Go 包的最顶级包。你可以在目录 $GOROOT/src/runtime 中找到相关内容。



https://www.modb.pro/db/153365


## iota 

golang里面 奇怪的 自增 常量。 


## channel 

关闭管道（Close）

close 函数标志着不会再往某个管道发送值。 在调用close之后，并且在之前发送的值都被接收后，接收操作会返回一个零值，不会阻塞。
一个多返回值的接收操作会额外返回一个布尔值用来指示返回的值是否发送操作传递的。

ch := make(chan string)
go func() {
    ch <- "Hello!"
    close(ch)
}()
fmt.Println(<-ch)    // 输出字符串"Hello!"
fmt.Println(<-ch)    // 输出零值 - 空字符串""，不会阻塞
fmt.Println(<-ch)    // 再次打印输出空字符串""
v, ok := <-ch        // 变量v的值为空字符串""，变量ok的值为false


## waitGroup不是引用类型

golang中分为值类型和引用类型
值类型分别有：int系列、float系列、bool、string、数组和结构体

引用类型有：指针、slice切片、管道channel、接口interface、map、函数等

值类型的特点是：变量直接存储值，内存通常在栈中分配

引用类型的特点是：变量存储的是一个地址，这个地址对应的空间里才是真正存储的值，内存通常在堆中分配


## 在Go中返回一个局部变量的地址是安全的

和C不一样，Go是支持垃圾回收的，所以一个函数返回其内声明的局部变量的地址是绝对安全的。比如：
func newInt() *int {
	a := 3
	return &a
}

Go指针的一些限制
为了安全起见，Go指针在使用上相对于C指针有很多限制。 通过施加这些限制，Go指针保留了C指针的好处，同时也避免了C指针的危险性。

上述Go指针的限制是可以被打破的
unsafe标准库包中提供的非类型安全指针（unsafe.Pointer）机制可以被用来打破上述Go指针的安全限制。 unsafe.Pointer类型类似于C语言中的void*。 但是，通常地，非类型安全指针机制不推荐在Go日常编程中使用。


## WaitGroup

WaitGroup 对象内部有一个计数器，最初从0开始，它有三个方法：Add(), Done(), Wait() 用来控制计数器的数量。Add(n) 把计数器设置为n ，Done() 每次把计数器-1 ，wait() 会阻塞代码的运行，直到计数器地值减为0。


## type 

https://cloud.tencent.com/developer/article/1074455

