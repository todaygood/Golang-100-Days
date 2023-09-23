# import了一个github的package ，如何build程序？

如下，需要go module的知识，用到了go mod tidy 命令

```bash
PS G:\go_repo\src\cli> go build
greeting.go:5:2: no required module provides package github.com/urfave/cli; to add it:
        go get github.com/urfave/cli
PS G:\go_repo\src\cli> cat .\greeting.go
package main

import (
        "fmt"
        "github.com/urfave/cli"
)

func main() {
        app := cli.NewApp()
        app.Name = "boom"
        app.Usage = "make an explosive entrance"

        app.Action = func(c *cli.Context) error {
                fmt.Printf("hello,urfave cli,%q\n", c.Args().Get(0))
                return nil
        }

        err := app.Run(os.Args)
        if err != nil {
                log.Fatal(err)
        }

}
PS G:\go_repo\src\cli> go mod tidy 
go: finding module for package github.com/urfave/cli
go: found github.com/urfave/cli in github.com/urfave/cli v1.22.10
go: downloading github.com/pmezard/go-difflib v1.0.0
PS G:\go_repo\src\cli>
PS G:\go_repo\src\cli>
PS G:\go_repo\src\cli> cat go.mod
module cli

go 1.18

require github.com/urfave/cli v1.22.10

require (
        github.com/cpuguy83/go-md2man/v2 v2.0.0-20190314233015-f79a8a8ca69d // indirect
        github.com/russross/blackfriday/v2 v2.0.1 // indirect
        github.com/shurcooL/sanitized_anchor_name v1.0.0 // indirect
)
PS G:\go_repo\src\cli> go build
PS G:\go_repo\src\cli> ls


    目录: G:\go_repo\src\cli


Mode                 LastWriteTime         Length Name
----                 -------------         ------ ----
-a----          2023/1/1     11:23        4321280 cli.exe
-a----          2023/1/1     11:23            271 go.mod
-a----          2023/1/1     11:23           1245 go.sum
-a----          2021/1/3      6:53            348 greeting.go
```

## 结果在pkg目录中含有了所有依赖的代码

```bash
PS G:\go_repo\pkg> tree mod 
卷 JinDong 的文件夹 PATH 列表
卷序列号为 000000CF 644B:F0EF
G:\GO_REPO\PKG\MOD
├─cache
│  └─download
│      ├─github.com
│      │  ├─!burnt!sushi
│      │  │  └─toml
│      │  │      └─@v
│      │  ├─cpuguy83
│      │  │  └─go-md2man
│      │  │      └─v2
│      │  │          └─@v
│      │  ├─pmezard
│      │  │  └─go-difflib
│      │  │      └─@v
│      │  ├─russross
│      │  │  └─blackfriday
│      │  │      └─v2
│      │  │          └─@v
│      │  ├─shurcoo!l
│      │  │  └─sanitized_anchor_name
│      │  │      └─@v
│      │  └─urfave
│      │      └─cli
│      │          └─@v
│      ├─golang.org
│      │  └─x
│      │      └─tools
│      │          └─gopls
│      │              └─@v
│      ├─gopkg.in
│      │  ├─check.v1
│      │  │  └─@v
│      │  └─yaml.v2
│      │      └─@v
│      └─sumdb
│          └─sum.golang.org
│              ├─lookup
│              │  ├─github.com
│              │  │  ├─!burnt!sushi
│              │  │  ├─cpuguy83
│              │  │  │  └─go-md2man
│              │  │  ├─pmezard
│              │  │  ├─russross
│              │  │  │  └─blackfriday
│              │  │  ├─shurcoo!l
│              │  │  └─urfave
│              │  ├─golang.org
│              │  │  └─x
│              │  │      └─tools
│              │  └─gopkg.in
│              └─tile
│                  └─8
│                      ├─0
│                      │  ├─x047
│                      │  └─x056
│                      │      └─968.p
│                      ├─1
│                      │  └─222.p
│                      └─2
│                          └─000.p
└─github.com
    ├─cpuguy83
    │  └─go-md2man
    │      └─v2@v2.0.0-20190314233015-f79a8a8ca69d
    │          ├─hack
    │          │  └─ci
    │          ├─md2man
    │          └─vendor
    ├─pmezard
    │  └─go-difflib@v1.0.0
    │      └─difflib
    ├─russross
    │  └─blackfriday
    │      └─v2@v2.0.1
    │          └─testdata
    ├─shurcoo!l
    │  └─sanitized_anchor_name@v1.0.0
    └─urfave
        └─cli@v1.22.10
            ├─.github
            │  └─workflows
            ├─altsrc
            ├─autocomplete
            ├─docs
            │  ├─v1
            │  └─v2
            └─testdata

```
