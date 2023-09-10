# 程序如何run?

## Step1: 打造vscode 

0. 安装golang 1.18.9 , 设置环境变量set GOPATH
 GOPATH =G:/go_repo/

1. 以上环境变量很多，这里仅设置下面这两个就足够了,widows设置方法：

一个是GO111MODULE 设置为 on，表示使用 go modules 模式

$ go env -w GO111MODULE=on
一个是开启代理，防止下载包失败（前面可能你已经设置过）

$ go env -w GOPROXY=https://goproxy.cn,direct

版权声明：本文为CSDN博主「有蝉」的原创文章，遵循CC 4.0 BY-SA版权协议，转载请附上原文出处链接及本声明。
原文链接：https://blog.csdn.net/qq_37899792/article/details/123375662

2. 在vscode中install/update tools ，将生成的dlv.exe,gopls.exe等拷贝到go安装路径的bin目录下，目的是vscode能找到即可，方便代码目录push到代码库。

```bash
PS E:\Program Files\Go\bin> ls


    目录: E:\Program Files\Go\bin


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----          2023/1/1      9:25       16183808 dlv.exe
-a----         2022/12/1     18:21       14481408 go.exe
-a----         2022/12/1     18:21        3540480 gofmt.exe
-a----          2023/1/1      9:24        3466240 gomodifytags.exe
-a----          2023/1/1      9:25        6726656 goplay.exe
-a----          2023/1/1      9:25       26146304 gopls.exe
-a----          2023/1/1      9:24       10113024 gotests.exe
-a----          2023/1/1      9:24        5934080 impl.exe
-a----          2023/1/1      9:25       12478464 staticcheck.exe
```

参见[Golang开发环境搭建vscode篇](https://juejin.cn/post/7175722688558678076)

按ctrl+shift+p 调出命令面板，输入`go install tools` 选Go: `Install/Update Tools`



## Step2: 建立go项目目录树

1. 构建目录树，按上面的go项目目录树路径为G:\go_repo\   
   go代码文件放在该目录下面，如：G:\go_repo\HelloWorld\hello.go 

2. 在HelloWorld目录下面go mod init hello， 然后运行`go build` 生成.exe文件


## Step3:在vscode中调试程序

参见： https://zhuanlan.zhihu.com/p/26473355

1. 生成lauch.json文件,方法是 Vscode ->Open configuration

```launch.json
{
 
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Launch Package",
            "type": "go",
            "request": "launch",
            "mode": "auto",
            "program": "HelloWorld"
        }
    ]
}
```

注意这个program字段， 当你调试 G:\go_repo\string\multi_line_string.go 程序时，这个program的值要写为 "string"


## 

[{
	"resource": "/g:/go_repo/src/regexp/main.go",
	"owner": "_generated_diagnostic_collection_name_#3",
	"severity": 4,
	"message": "This file is within module \"regexp\", which is not included in your workspace.\nTo fix this problem, you can add a go.work file that uses this directory.\nSee the documentation for more information on setting up your workspace:\nhttps://github.com/golang/tools/blob/master/gopls/doc/workspace.md.",
	"source": "go list",
	"startLineNumber": 1,
	"startColumn": 9,
	"endLineNumber": 1,
	"endColumn": 13
}]


gopls（Go Language Server）是一个为Go 语言开发的语言服务器。 它可以为Go 程序提供编辑器或其他工具集成时使用的语言特性，如类型检查、自动完成、快速修复和跳转至定义。 gopls 是由Google 开发的，并且是Go 语言的官方语言服务器。




## issue

### issue 1: go mod init 在初始化时出现 cannot determine module path for source directory (outside GOPATH

https://blog.csdn.net/ciel_yu/article/details/107847578


### issue 2: gopls 找不到workspace 

在一个.go文件上，vscode的"PROBLEMS"窗口中出现错误提示：

```log
[{
	"resource": "/g:/go_repo/cli/greeting.go",
	"owner": "_generated_diagnostic_collection_name_#0",
	"severity": 8,
	"message": "gopls was not able to find modules in your workspace.\nWhen outside of GOPATH, gopls needs to know which modules you are working on.\nYou can fix this by opening your workspace to a folder inside a Go module, or\nby using a go.work file to specify multiple modules.\nSee the documentation for more information on setting up your workspace:\nhttps://github.com/golang/tools/blob/master/gopls/doc/workspace.md.",
	"source": "go list",
	"startLineNumber": 1,
	"startColumn": 1,
	"endLineNumber": 1,
	"endColumn": 13
}]
```


使用下面的办法生成go.work文件之后，就不报这个错误了。

```powershell
PS G:\go_repo> go work init
PS G:\go_repo> go work use -r ./src/
PS G:\go_repo> ls


    目录: G:\go_repo


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
d-----          2023/1/1     10:06                .vscode
d-----          2023/1/1     11:25                doc
d-----          2023/1/1     11:19                pkg
d-----          2023/1/1     11:03                src
-a----          2023/1/1     11:10            269 .gitignore
-a----          2023/1/1     11:37            170 go.work
-a----          2023/1/1     11:10          11357 LICENSE
-a----          2023/1/1     11:00           3102 Readme.md


PS G:\go_repo> cat .\go.work
go 1.18

use (
        ./src/HelloWorld
        ./src/cli
        ./src/function
        ./src/json
        ./src/my_array
        ./src/os-package
        ./src/string
        ./src/struct-tag
        ./src/time
        ./src/use-detect
)
```

参见：

[官方博文：Go 1.18工作区模式最佳实践](https://www.modb.pro/db/434264)

[多模块工作区]( https://github.com/link1st/link1st/tree/master/workspaces)

使用这个go.work之后，发现又有新问题了，就是之前go build 可以成功的，现在不行了，不知为何，先不用go.work

后来又发现不使用gopath的src路径之后，go.work又没有问题了。

`go work use -r . ` 命令会自动将有go.mod文件的文件夹加入进来。

```bash
[root@pcentos hello-go]# cat go.work 
go 1.18

use (
        ./HelloWorld
        ./cli
        ./containerlist
        ./containerof
        ./function
        ./if
        ./json
        ./my_array
        ./os-package
        ./pkg/mod/github.com/cpuguy83/go-md2man/v2@v2.0.0-20190314233015-f79a8a8ca69d
        ./pkg/mod/github.com/russross/blackfriday/v2@v2.0.1
        ./pkg/mod/github.com/shurcoo!l/sanitized_anchor_name@v1.0.0
        ./pkg/mod/github.com/todaygood/detect-kernel@v0.0.0-20210101114202-3cfcfb02f5dd
        ./pkg/mod/github.com/urfave/cli@v1.22.10
        ./pkg/mod/golang.org/x/sys@v0.0.0-20201231184435-2d18734c6014
        ./pkg/mod/gopkg.in/yaml.v2@v2.2.2
        ./string
        ./strings
        ./struct-tag
        ./time
        ./use-detect
)
```

注意新增了某个module之后，要再次运行`go work use -r . ` 命令。 


### issue 3:  报错no required module provides package github.com/xx的解决方案

https://blog.csdn.net/counsellor/article/details/123031707


### issue 4: vscode 报没有git respository , 但实际上有

运行 git config --global --add safe.directory "*"  解决了。

```powershell
PS G:\go_repo> git status 
fatal: unsafe repository ('G:/go_repo' is owned by someone else)

        git config --global --add safe.directory G:/go_repo

Set the environment variable GIT_TEST_DEBUG_UNSAFE_DIRECTORIES=true and run
again for more information.
PS G:\go_repo> git version
git version 2.37.0.windows.1
PS G:\go_repo> git config --global --add safe.directory "*"
PS G:\go_repo> git status 
On branch master
Your branch is up to date with 'origin/master'.

nothing to commit, working tree clean
PS G:\go_repo> 
```
确认问题解决。 

### issue 5: 无法调试stdin 

发现在debug console 中无法输入

https://github.com/golang/vscode-go/issues/2053

1. 启用remote debuging , 须要使用extension: go nightly , go不行，默认不启用remote debuging
2. 配置使用console 

```launch.json
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Launch Package",
            "type": "go",
            "request": "launch",
            "mode": "auto",
            "console": "integratedTerminal",
            "program": "containerlist"
        }
    ]
}
```
3. 调试，可以发现在terminal上出现：

```powershell
PS G:\go_repo>  ${env:http_proxy}='http://127.0.0.1:58591'; ${env:HTTP_PROXY}='http://127.0.0.1:58591'; ${env:https_proxy}='http://127.0.0.1:58591'; ${env:HTTPS_PROXY}='http://127.0.0.1:58591'; ${env:GOPATH}='G:\go_repo\'; & 'E:\Program Files\Go\bin\dlv.exe' 'dap' '--client-addr=:3559'
hello,iLRU
abc kldkldfslkabdfklsjafjkldsakljdfklsa
0.000000        0.457000        0.003000        454.000000      4096000.000000  306192.000000   3309568.000000  0.000000     306192.000000   306192.000000   6705360.000000  0.000000        0.000000        4194304.000000  0.000000
jkdlfsajkldfklsa
1.000000        0.475000        0.008000        467.000000      4096000.000000  307168.000000   3293184.000000  0.000000        307168.000000  307168.000000   6705360.000000  0.000000        0.000000        4194304.000000  0.000000

```

### issue 6： terminal窗口中无法显示git log中的中文

```powershell
hujun469@Taishiji MINGW64 /g/go_repo (master)
$ git log 
commit 70d7b4744116659e9f986437124eb12b2a10a99d (HEAD -> master, origin/master, origin/HEAD)
Author: hujun-taishiji <hujun469@taishiji>
Date:   Sun Jan 1 19:54:14 2023 +0800

    <E6><90><9E><E5><AE><9A>stdin<E8><B0><83><E8><AF><95>
```
修改winterm 的local 从zh_CN 修改为zh_CN.utf-8 之后

```powershell
PS G:\go_repo> git log
commit 70d7b4744116659e9f986437124eb12b2a10a99d (HEAD -> master, origin/master, origin/HEAD)
Author: hujun-taishiji <hujun469@taishiji>
Date:   Sun Jan 1 19:54:14 2023 +0800

    搞定stdin调试
```

### issue 7: 修改Readme.md文件，git不显示文件变化，push到gitee 之后显示也是之前的文件内容

本地文件名字是Readme.md ，远程文件名字是README.md， 导致了这个莫名其妙的问题

是我在linux上git clone后发现这个现象的，以前也出现过，这次再次记录一下，不要再踩坑， windows文件名不区分大小写太坑了。 







### How to publish your code? 

https://golang.org/doc/code.html

### golang语法速查手册

https://www.yiibai.com/go/go_start.html
