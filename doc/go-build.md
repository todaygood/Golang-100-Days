## go build 

使用tag来实现编译不同的文件

go-tooling-workshop 中关于go build的讲解可以了解到go bulid的一些用法，这篇文章最后要求实现一个根据go bulid -tag功能来编译不同版本的做法，version参数根据tag传进来的值进行编译。下面是一个实例，main.go

https://www.cnblogs.com/linyihai/p/10859945.html


1. 是否有动态库链接
Go 引用了其他包的话，是将引用的包都编译进去。用 ldd 看几个 Go 编译出来的二进制程序有的没有动态链接库的使用。但是有的又有引用动态链接库，这个是为什么？

回答：Go 默认是开启 CGO_ENABLED 的，即 CGO_ENABLED=1 。但编译出来的二进制程序究竟有无动态链接，取决于你的程序使用了什么包。如果就是一个 hello world，那么编译出来的将是一个纯静态程序。

如果你依赖了网络包或一些系统包，比如用 http 包编写了一个 web server，那么编译出来的二进制程序又会是一个包含动态链接的程序。

原因就在于目前的 Go 标准库中，某些功能具有两份实现，一份是 C 语言实现的，一份是 Go 语言实现的。

在 CGO_ENABLED 开启的情况下， Go 链接器会链接C 语言的版本，于是就有了依赖动态链接库的情况。
如果你将 CGO_ENABLED 置为 0，你再重新编译链接，那么 Go 链接器会使用 Go 版本的实现，这样你将得到一个没有动态链接的纯静态二进制程序。
2. Go 编译优化
Go 语言为了加快编译的速度，在编译时，如果 package 中有未使用的依赖项会直接报错，这保证了 Go 程序的依赖树是精确的。在构建程序时，Go 不会编译多余的代码，这就最大限度地减少了编译时间。

另外，Go 的编译器还做了大量优化。当编译器执行 import 导入包时，它只需要打开一个与导入包相关的 obj 文件（object file），而不是导入依赖的源代码。这种方式具有扩展性，因此不会随着 Go 代码库的增多导致编译时间的指数级上升。

同时，Go 对 obj 文件的结构也做了优化，以便更快速地导入依赖。Go 依赖管理的另一个特性是不能有循环依赖。因为代码之间的循环纠缠最终会使各个模块之间难以解耦，难以独立管理。取消了循环依赖意味着编译器不必一次性编译大量的源代码。
————————————————
版权声明：本文为CSDN博主「wohu007」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/wohu1104/article/details/122806033

```go 
// cat if_assignment.go
package main

import "fmt"

func main() {

        if a := 5; a < 6 {
                fmt.Println("a is less than 6")
        }
}
```
编译出来是一个static的。

```bash
[root@pcentos if]# ls 
go.mod  if_assignment.go
[root@pcentos if]# go build 
[root@pcentos if]# ls
go.mod  if_assignment  if_assignment.go
[root@pcentos if]# ldd ./if_assignment
        not a dynamic executable
```