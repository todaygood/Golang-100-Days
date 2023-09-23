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

