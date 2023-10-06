
## GOMAXPROCS含义与用法

https://blog.csdn.net/m0_37554486/article/details/104646467

【GO语言】合理配置GOMAXPROCS提升一倍以上的性能

https://blog.csdn.net/weixin_34191845/article/details/91818888?spm=1001.2101.3001.6661.1&utm_medium=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1.pc_relevant_default&depth_1-utm_source=distribute.pc_relevant_t0.none-task-blog-2%7Edefault%7ECTRLIST%7ERate-1.pc_relevant_default&utm_relevant_index=1

在 Go语言程序运行时（runtime）实现了一个小型的任务调度器。这套调度器的工作原理类似于操作系统调度线程，Go 程序调度器可以高效地将 CPU 资源分配给每一个任务。传统逻辑中，开发者需要维护线程池中线程与 CPU 核心数量的对应关系。同样的，Go 地中也可以通过 runtime.GOMAXPROCS() 函数做到，格式为：

runtime.GOMAXPROCS(逻辑CPU数量)

这里的逻辑CPU数量可以有如下几种数值：

<1：不修改任何数值。
=1：单核心执行。
>1：多核并发执行。

一般情况下，可以使用 runtime.NumCPU() 查询 CPU 数量，并使用 runtime.GOMAXPROCS() 函数进行设置，例如：

runtime.GOMAXPROCS(runtime.NumCPU())
Go 1.5 版本之前，默认使用的是单核心执行。从 Go 1.5 版本开始，默认执行上面语句以便让代码并发执行，最大效率地利用 CPU。

GOMAXPROCS 同时也是一个环境变量，在应用程序启动前设置环境变量也可以起到相同的作用。


[在容器中设置GOMAXPROCS](https://cloud.tencent.com/developer/article/1832721)





## golang 调度

Runtime: Golang中channel实现原理源码分析
https://blog.haohtml.com/archives/20760

深入golang runtime的调度
https://zboya.github.io/post/go_scheduler/



