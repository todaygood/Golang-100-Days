# Golang basic kb

## build

http://c.biancheng.net/view/120.html

go build 在编译开始时，会搜索当前目录的 go 源码。这个例子中，go build 会找到 lib.go 和 main.go 两个文件。编译这两个文件后，生成当前目录名的可执行文件并放置于当前目录下，这里的可执行文件是 go build。

go build -o myexec main.go lib.go

```bash
G:\go_repo\if# ls
go.mod  if_assignment.go

G:\go_repo\if# go build

G:\go_repo\if# ls
go.mod  if_assignment.go  study_if.exe
```

## comment 

/* this is a comment */

// comment too

## 理解type和interface的作用


type很好地实现了一人千面，而interface很好地支持了千人一面。
http://blog.sina.com.cn/s/blog_9be3b8f10101ccpu.html


## fmt %

golang fmt格式“占位符” 
https://studygolang.com/articles/2644



## go module 


当modules功能启用时，依赖包的存放位置变更为$GOPATH/pkg，允许同一个package多个版本并存，且多个项目可以共享缓存的 module

go module 安装 package 的原則是先拉最新的 release tag，若无tag则拉最新的commit

go 会自动生成一个 go.sum 文件来记录 dependency tree