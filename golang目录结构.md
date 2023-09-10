# Golang目录结构


使用一个IDE， 比如LiteIDE 

1. Go可执行程序可以分解成一个个包，其中必须存在main包，main包里必须包含main函数，程序执行本质上就是运行main包里的main函数，main函数结束程序就结束，就这样。

2. 使用go module导入本地包

https://zhuanlan.zhihu.com/p/109828249



参见oop这个代码。 


### 使用go module 来做包管理。

使用go module ， 不要使用gopath了， 参见[go mod使用 | 全网最详细](https://zhuanlan.zhihu.com/p/482014524)

使用go path问题：

代码开发必须在go path src目录下，不然，就有问题。
依赖手动管理
依赖包没有版本可言
从这个看， go path不算包管理工具

https://maelvls.dev/go111module-everywhere/

## 我要提出问题


## kb 

1. go install, go build

2. go module 

3. go workspace 

4. go package , import , main package

## go workspace

目前go都是通过mod进行包管理，包主要分两类:

- 一类是公网上的，直接引入用go mod管理即可。
- 一类是本地包，比如你自己写的包或者下载到本地的包，对于这类包，在go 1.18前，都是通过给go.mod中添加replace来修改引用包的实际路径。这种包引用对于git提交就非常麻烦，每次提交前需要把replace去掉才行。

于是go work被发明了出来。

作者：lambdang
链接：https://juejin.cn/post/7145855715565895710

 

## go build, go install

golang的编译使用命令 go build , go install; 除非仅写一个main函数，否则还是准备好目录结构；

GOPATH=工程根目录；其下应创建src，pkg，bin目录，

- bin目录中用于生成可执行文件，
- pkg目录中用于生成.a文件；

golang中的import name，实际是到GOPATH中去寻找name.a, 使用时是该name.a的源码中声明的package名字； 

注意点：

    1.系统编译时 go install abc_name时，系统会到GOPATH的src目录中寻找abc_name目录，然后编译其下的go文件；

    2.同一个目录中所有的go文件的package声明必须相同，所以main方法要单独放一个文件，否则在eclipse和liteide中都会报错；
    编译报错如下：（假设test目录中有个main.go 和mymath.go,其中main.go声明package为main，mymath.go声明packag 为test);

        $ go install test

        can't load package: package test: found packages main (main.go) and test (mymath.go) in /home/wanjm/go/src/test

        报错说 不能加载package test（这是命令行的参数），因为发现了两个package，分别时main.go 和 mymath.go;

    3.对于main方法，只能在bin目录下运行 go build path_tomain.go; 可以用-o参数指出输出文件名；

    4.可以添加参数 go build -gcflags "-N -l" ****,可以更好的便于gdb；详细参见 http://golang.org/doc/gdb

    5.gdb全局变量主一点。 如有全局变量 a；则应写为 p 'main.a'；注意但引号不可少；


```PowerShell
PS G:\go_repo> ls .\bin\


    目录: G:\go_repo\bin


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----          2023/8/6     10:16       24160768 gopls.exe
-a----         2023/6/24     13:34       23996416 gopls.exe~


PS G:\go_repo> go install .\src\TestIf\if_assignment.go
PS G:\go_repo> ls .\bin\


    目录: G:\go_repo\bin


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----          2023/8/6     10:16       24160768 gopls.exe
-a----         2023/6/24     13:34       23996416 gopls.exe~
-a----         2023/9/10     10:15        1894400 if_assignment.exe


PS G:\go_repo> ls .\src\TestIf\


    目录: G:\go_repo\src\TestIf


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----          2023/9/9     23:17             23 go.mod
-a----          2021/1/3      6:53            102 if_assignment.go
-a----          2023/9/9     23:17        1894400 TestIf.exe
```

实际上，go install 命令只比 go build 命令多做了一件事，即：安装编译后的结果文件到指定目录。


## go module

https://article.itxueyuan.com/Oe3oB3


配置 GO111MODULE
GO111MODULE环境变量主要是用来开启或关闭模块支持的。

它有三个可选值：off、on、auto，默认值是 auto。

GO111MODULE=off  无模块支持，go 会从 GOPATH 和 vendor 文件夹寻找包。
GO111MODULE=on    模块支持，go 会忽略 GOPATH 和 vendor 文件夹，只根据 go.mod 下载依赖。
GO111MODULE=auto 在 $GOPATH/src 外面且根目录有 go.mod 文件时，开启模块支持。
在使用模块的时候，GOPATH 是无意义的，不过它还是会把下载的依赖储存在 $GOPATH/src/mod 中，也会把 go install 的结果放在 $GOPATH/bin 中。

依赖本地包：
https://zhuanlan.zhihu.com/p/105556877



## Package 包使用

package 是最基本的分发单位和工程管理中依赖关系的体现

每个 Go 语言源代码文件开头都拥有一个 package 声明，表示源码文件所属代码包

要生成 Go 语言可以执行程序，必须要有 main 的 package 包，且必须在该包下有 main() 函数

package main

同一个路径下只能存在一个package ，一个package 包可以拆成多个源文件组成

建议引入的 package 包的名称和当前属于的文件名相同

## import 的用法及原理

import的语法是： import Module/Package , 注意module目录下面有go.mod , Package目录下面没有go.mod 

import 语句可以导入源代码文件所依赖的 package 包
不得 导入源代码文件中没有用到的 package ，否则 Go 语言编译器会报编译错误
如果一个 main 导入其他包，包将按照顺序导入
如果导入的包中依赖其他包（A 依赖 B）, 会首先导入 B 包，然后初始化 B 包中的常量和变量，最好如果 B 包中有 init, 会自动执行 init() 初始化函数
所有包导入完成后才对 main 中的常量和变量进行初始化，然后执行 main 中的 init() 函数 (如过存在)，最后执行 main 函数
如果一个包被导入多次则该包之后导入一次。
import 语法：
第一种用法

    import "package1"
    import "package2"
    import "package3"

第二种用法 （多个包推荐此用法）

    import (
        "package1"
        "package2"
        "package3"
    )


import 特殊用法

import 可以取别名，将导入的包命名为另一个容易记忆的别名 （别名写在 引入包的名称前面）

点（.）操作的含义是：点（.）标示的包导入后，调用该包中函数时可以省略前缀包名
下划线 （_）操作的含义是：导入该包，但不导入整个包，而是执行该包中的 init 函数，因此无法通过包名来调用包中的其他函数。使用下划线操作往往是为了注册包里的引擎，让外部可以方便的使用

————————————————
原文作者：Aliliin
转自链接：https://learnku.com/articles/24447
 


## go get 

```bash
[root@pcentos build-k8s]#  go install  github.com/go-delve/delve/cmd/dlv@v1.8.0
[root@pcentos build-k8s]# cd /root/gopath/
[root@pcentos gopath]# ls
bin  pkg  src
[root@pcentos gopath]# find . -name dlv
./pkg/mod/github.com/go-delve/delve@v1.8.0/cmd/dlv
./bin/dlv
```

go get的用法： go get 指定url@版本号

```bash
[root@pcentos src]# /usr/local/go/bin/go get github.com/go-delve/delve/cmd/dlv@v1.8.0
go: downloading github.com/go-delve/delve v1.8.0
go: downloading github.com/sirupsen/logrus v1.6.0
go: downloading github.com/spf13/cobra v1.1.3
go: downloading github.com/mattn/go-isatty v0.0.3
go: downloading github.com/konsorten/go-windows-terminal-sequences v1.0.3
go: downloading golang.org/x/sys v0.0.0-20211019181941-9d821ace8654
go: downloading gopkg.in/yaml.v2 v2.4.0
go: downloading github.com/cosiner/argv v0.1.0
go: downloading github.com/derekparker/trie v0.0.0-20200317170641-1fdf38b7b0e9
go: downloading github.com/mattn/go-colorable v0.0.9
go: downloading github.com/peterh/liner v1.2.1
go: downloading github.com/google/go-dap v0.6.0
go: downloading github.com/inconshreveable/mousetrap v1.0.0
go: downloading github.com/spf13/pflag v1.0.5
go: downloading github.com/cpuguy83/go-md2man/v2 v2.0.0
go: downloading go.starlark.net v0.0.0-20200821142938-949cc6f4b097
go: downloading github.com/mattn/go-runewidth v0.0.3
go: downloading github.com/hashicorp/golang-lru v0.5.4
go: downloading golang.org/x/arch v0.0.0-20190927153633-4e8777c89be4
go: downloading github.com/russross/blackfriday/v2 v2.0.1
go: downloading github.com/cilium/ebpf v0.7.0
go: downloading github.com/shurcooL/sanitized_anchor_name v1.0.0
[root@pcentos src]# ls

```

go get 会下载到$GOPATH/pkg下面去 

```bash
[root@pcentos delve@v1.8.0]# pwd
/root/gopath/pkg/mod/github.com/go-delve/delve@v1.8.0
[root@pcentos delve@v1.8.0]# ls
assets        cmd              Documentation  go.mod  ISSUE_TEMPLATE.md  Makefile  README.md  service
CHANGELOG.md  CONTRIBUTING.md  _fixtures      go.sum  LICENSE            pkg       _scripts   vendor
```


## GOXXX环境变量

https://www.jianshu.com/p/c43ebab25484



环境变量

GOPATH: 定义了go project 所在的位置
GOROOT: 定义了go的安装位置。 

环境变量：
$GOROOT:
表示Go的安装目录。也就是上面我们解压出来的文件夹里面的go文件夹。
$GOPATH:
表示我们的工作空间。用来存放我们的工程目录的地方。
GOPATH目录：
一般来说GOPATH下面会有三个文件夹：bin、pkg、src，没有的话自己创建。每个文件夹都有其的作用。

bin：编译后可的执行文件的存放路径
pkg：编译包时，生成的.a文件的存放路径
src：源码路径，一般我们的工程就创建在src下面。
注意：如果要用Go Mod(Go1.11及以上支持)进行包管理，则需要在 GOPATH 以外的目录创建工程。关于Go Mod的使用，可以自行Google一下，这里就不赘述了。

作者：Mr_Leung
链接：https://www.jianshu.com/p/c43ebab25484
来源：简书
著作权归作者所有。商业转载请联系作者获得授权，非商业转载请注明出处。



## vsCode技巧

https://geek-docs.com/vscode/vscode-tutorials/vscode-breadcrumb.html



### symbol跳转



