# deadlock in golang

死锁是线程之间相互等待，其中任何一个都无法向前运行的情形。


## golang 死锁检测工具


Golang 提供了一些内置工具来检测死锁，这些工具包括：

runtime.Stack：可以获取协程的调用栈信息，可以用来查找死锁的原因。


Go 内置的调试工具：GDB、Delve 等工具可以对 Go 程序进行调试，也可以检测到死锁。


go tool pprof：是一个用于性能分析和调试的工具，也可以检测到死锁。


除此之外，还有一些第三方工具，如 Deadlock detection 库，也可以用来检测 Golang 中的死锁。



golang自动检测死锁deadlock的实现   https://xiaorui.cc/archives/5951

死锁检测工具 https://blog.csdn.net/qq_34893654/article/details/129421698


## Go语言中的并发编程总结 


https://www.jianshu.com/p/9a1a28de0900


https://z24z.com/post/2021/concurency-in-go/



## issue 

https://github.com/golang/go/issues/33004










