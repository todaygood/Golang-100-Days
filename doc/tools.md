
# go get 需要翻墙

有一些需要库在google服务器,所以也需要翻墙。


# go run 

go run 直接build，然后run *.go文件， 比较省事。

```bash
[margin@cloud-sz-kolla-b13-01 src]$ go run arg_flag.go  -id=2 -name="golang"  -port="8087"
ok: false
id: 2
port: 8087
name: golang

```

## IDE

学习一门语言，在开始做大项目之前不要使用IDE。 

目前golang最好的，免费的IDE就是 VScode, 感觉还是在Ubuntu图形界面下用VScode比较好一些，如调试k8s代码

https://colobu.com/2016/04/21/use-vscode-to-develop-go-programs/

https://code.visualstudio.com/docs/languages/go

## VScode中使用proxy

 settings.json
 // VSCode: Place your settings in this file to overwrite the default settings
 {
   "http.proxy": "http://user:pass@proxy.com:8080",
   "https.proxy": "http://user:pass@proxy.com:8080",
   "http.proxyStrictSSL": false
 }

# go debug 

delve 比gdb好，更理解goroutine

http://lday.me/2017/02/27/0005_gdb-vs-dlv/


