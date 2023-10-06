# go GUI 


## web html5 应用：使用energy

https://github.com/energye/energy


energy 是 Go 基于 CEF(Chromium Embedded Framework) 开发的框架，内嵌 CEF 二进制

使用 Go 和 Web 端技术 ( HTML + CSS + JavaScript ) 构建支持Windows, Linux, MacOS跨平台桌面应用

值得学习一下，貌似写web窗口程序挺好的。

https://energy.yanghy.cn/course/100/6350f94ca749ba0318943f25



python中也有类似的基于CEF的技术: cefpython3 
https://zhuanlan.zhihu.com/p/103112643

典型的代表：Electron

用 Django + Electron + Vue 写一个桌面文档客户端
https://cloud.tencent.com/developer/article/1909074


pyQT商用是收费的，商用必须用PySide，参见：https://zhuanlan.zhihu.com/p/444953634

对于桌面开发，天下武功那么多，PyQt 既是最正统的门派，同时又是一系列综合技术的组合，它进可以同 C++ Qt 无缝整合，解决性能相关的东西；退又有基于chromium 的 QtWebEngine ，能在适合跑页面的部分用 html/js 来写页面，并和 python 双向调用，实现类似 cef/Electron 的效果，但是 Electron这类单一解决方案就只能用 web 技术，想反过来同 native 界面混合开发，基本就傻了，碰到性能问题又不能像 PyQt 那样可以无缝切换 C++ Qt，所以庞然大物 Electron 只适合呆在自己的舒适区。

往左，QtWidgets 可以和传统 C# 的 WinForm pk，往右，Qt-Quick 可以同 WPF/XAML 看齐，因此你可以把 PyQt/Qt看成一系列界面解决方案的 “超集”，所以学习 PyQt 你学会的是综合格斗术，是名门正派的内功心法，而不是某方向单一的方案，比如 “螳螂拳”。                

PyQt 就是一扇门，它通往的是最专业的桌面解决方案的世界。



## golang native window:使用govcl 

https://github.com/ying32/govcl/tree/master/samples


govcl文档： https://gitee.com/ying32/govcl/wikis/pages?sort_id=1540640&doc_id=102420

lazarus 参见： https://www.zhihu.com/question/54905309

https://wiki.freepascal.org/Lazarus_Tutorial/zh_CN


## 比较

1.Fyne: 非常强大，支持多平台，和移动设备 要求Go 1.12 以后版本
参考链接：github.com/fyne-io/fyn…
2.QT库:QT是一个跨平台的C++应用程序开发框架。
参考链接：github.com/therecipe/q…
3.UI:非常小的基于webview的扩展库，优点是小，缺点也是小。 要求Go 1.8 以后版本
参考链接：github.com/andlabs/ui 4.Walk：只支持windows。 要求Go 1.11 以后版本
参考链接：github.com/lxn/walk

5.Go-astilectron：这是一个基于election的扩展库，可以使用css，js，html来进行界面的设计和开发。 参考链接： github.com/asticode/go…

6.Gotk3：gtk+3同样是一个使用广泛跨平台的GUI框架，它同样功能丰富。不过和Qt的规模相比还略显得小了一些，而且gtk+和python一样存在2和3两个版本的断桥式飞跃，从gtk+2迁移至3会遇到不少小麻烦，gtk+的文档也没有Qt那样详尽；以及gotk3的维护并不活跃。 参考链接： github.com/gotk3/gotk3

7.Go-sciter：这是一个基于sciter的绑定，sciter是非常流行的桌面客户端UI库，也是使用css，js，html来进行开发的，因此对于熟悉web开发的人上手并不难。 参考链接： github.com/sciter-sdk/…

8.GoGi：这个t图形库可以支持2D/3D 参考链接： github.com/goki/gi

9.Gowd：使用HTML, CSS and NW.js.来进行发开发的扩展库，它也是基于web的UI库。 参考链接： github.com/dtylman/gow…



