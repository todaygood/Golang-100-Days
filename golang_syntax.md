## make,new

make 返回类型是引用类型，new 返回类型是指针类型。

make 仅用于初始化 slice，map 和 chan，new 可用于初始化任意类型。
make 返回值是”引用类型“，new 返回值是指针类型。

func new(Type) *Type


## ...any 


概念
any是golang新引入的预定义标识符，是空接口的别名，可以用于代替interface{}。

应用场景
在泛型场景下，可将any用于类型限定（type constraint），以表示任意类型。

https://juejin.cn/post/7064220225302396941


### ... 是可变参数

https://programming.guide/go/three-dots-ellipsis.html

func Sum(nums ...int) int {
        res := 0
        for _, n := range nums {
                res += n
        }
        return res
}

## panic 

Go语言追求简洁优雅，所以，Go语言不支持传统的 try…catch…finally 这种异常，因为Go语言的设计者们认为，将异常与控制结构混在一起会很容易使得代码变得混乱。因为开发者很容易滥用异常，甚至一个小小的错误都抛出一个异常。在Go语言中，使用多值返回来返回错误。不要用异常代替错误，更不要用来控制流程。在极个别的情况下，也就是说，遇到真正的异常的情况下（比如除数为 0了）。才使用Go中引入的Exception处理：defer, panic, recover。

这几个异常的使用场景可以这么简单描述：Go中可以抛出一个panic的异常，然后在defer中通过recover捕获这个异常，然后正常处理。

https://zhuanlan.zhihu.com/p/373653492


## type 


类型别名
通过 type 进行定义，如下

    type 整型 int32
    var  zhengxing 整型 = 1 
    fat.Print(zhengxing) // 打印会输出 1


int 整型
 float32,float64 浮点型 32位浮点型数，64位浮点型数
 uint8,uint16,uint32,uint64 无符号整型 (8:0-255,16:0-65535,32:0-4294967295,64:0-18446744073709551615)
 int8,int16,int32,int64 有符号整型 (-128 到 127，-32768 到 32767,-2147483648 到 2147483647,-9223372036854775808 到 9223372036854775807)

byte 类似uint8
rune 类似int32
uint 32位或者64位
int 与uint一样大小
uintptr 无符号整型，用于存放一个指针

布尔型
布尔型的值只可以是常量 true 或者 false。例子：var b bool = true。 注意：不能为其他类型

字符串类型
字符串就是一串固定长度的字符连接起来的字符序列。 Go 的字符串是由单个字节连接起来的。 Go 语言的字符串的字节使用 UTF-8 编码标识 Unicode 文本。


派生类型

指针类型（Pointer）
数组类型
结构化类型 （struct)
Channel 类型 (chan)
函数类型 (func)
切片类型 (slice)
接口类型 （interface）
Map 类型 (map)


注意
类型零值不是空值，而是某个变量被声明后的默认值，
一般情况下，值类型的默认值为0，
一般情况下，布尔默认值为false
一般情况下，字符串类型默认值为空字符串

https://github.com/aliliin/Learn-golang/blob/master/DocRecord/Go%E6%95%B0%E6%8D%AE%E7%B1%BB%E5%9E%8B.md

## interface



## flag

https://learnku.com/articles/83560


