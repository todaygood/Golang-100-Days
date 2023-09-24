# 调试golang程序

参见https://blog.csdn.net/why444216978/article/details/110249558


## gdb golang语言的程序

golang程序的调试工具，有两个，为gdb或者dlv, gdb对goroutine支持不好，而dlv很好用。 
可参见： https://www.cnblogs.com/sunsky303/p/11571367.html

即使不加断点，也可以进入runtime内核代码

使用 -gcflags=all="-N -l" 禁用内联优化方便后面调试


如果不加 -ldflags='-compressdwarf=false' 在调试时可能会提示 No symbol table is loaded. Use the "file" command.


可参见https://blog.csdn.net/why444216978/article/details/110249558

https://xiazemin.github.io/golang/2020/01/09/symbols.html


```bash
[root@pcentos if]# gdb ./if_assignment
GNU gdb (GDB) Red Hat Enterprise Linux 7.6.1-119.el7
Copyright (C) 2013 Free Software Foundation, Inc.
License GPLv3+: GNU GPL version 3 or later <http://gnu.org/licenses/gpl.html>
This is free software: you are free to change and redistribute it.
There is NO WARRANTY, to the extent permitted by law.  Type "show copying"
and "show warranty" for details.
This GDB was configured as "x86_64-redhat-linux-gnu".
For bug reporting instructions, please see:
<http://www.gnu.org/software/gdb/bugs/>...
Reading symbols from /root/go_repo/if/if_assignment...done.
Loading Go Runtime support.
(gdb) b main.main
Breakpoint 1 at 0x499080: file /root/go_repo/if/if_assignment.go, line 5.
(gdb) 
```

有时发布时我们想隐藏所有代码实现相关的信息，使用 go build -ldflags 参数可以实现相关要求。
设置编译参数-ldflags "-w -s",其中-w为去掉调试信息（无法使用gdb调试），-s为去掉符号表（暂未清楚具体作用）。

```bash
[root@pcentos if]# go build -ldflags "-w -s"  if_assignment.go 
[root@pcentos if]# ls
if_assignment  if_assignment.debug  if_assignment.go
[root@pcentos if]# gdb if_assignment
For bug reporting instructions, please see:
<http://www.gnu.org/software/gdb/bugs/>...
Reading symbols from /root/go_repo/if/if_assignment...(no debugging symbols found)...done.
```

## dlv 调试笔记

dlv是最好的调试工具， 参见https://zhuanlan.zhihu.com/p/425645473

```bash
[root@pcentos if]# dlv debug if_assignment.go 
Type 'help' for list of commands.
(dlv) l 
> _rt0_amd64_linux() /usr/local/go/src/runtime/rt0_linux_amd64.s:8 (PC: 0x46eec0)
Warning: debugging optimized function
     3: // license that can be found in the LICENSE file.
     4:
     5: #include "textflag.h"
     6:
     7: TEXT _rt0_amd64_linux(SB),NOSPLIT,$-8
=>   8:         JMP     _rt0_amd64(SB)
     9:
    10: TEXT _rt0_amd64_linux_lib(SB),NOSPLIT,$0
    11:         JMP     _rt0_amd64_lib(SB)
(dlv) break  if_assignment.go:7
Breakpoint 1 set at 0x4b86a1 for main.main() ./if_assignment.go:7
(dlv) help 
The following commands are available:

Running the program:
    call ------------------------ Resumes process, injecting a function call (EXPERIMENTAL!!!)
    continue (alias: c) --------- Run until breakpoint or program termination.
    next (alias: n) ------------- Step over to next source line.
    rebuild --------------------- Rebuild the target executable and restarts it. It does not work if the executable was not built by delve.
    restart (alias: r) ---------- Restart process.
    step (alias: s) ------------- Single step through program.
    step-instruction (alias: si)  Single step a single cpu instruction.
    stepout (alias: so) --------- Step out of the current function.

Manipulating breakpoints:
    break (alias: b) ------- Sets a breakpoint.
    breakpoints (alias: bp)  Print out info for active breakpoints.
    clear ------------------ Deletes breakpoint.
    clearall --------------- Deletes multiple breakpoints.
    condition (alias: cond)  Set breakpoint condition.
    on --------------------- Executes a command when a breakpoint is hit.
    trace (alias: t) ------- Set tracepoint.

Viewing program variables and memory:
    args ----------------- Print function arguments.
    display -------------- Print value of an expression every time the program stops.
    examinemem (alias: x)  Examine memory:
    locals --------------- Print local variables.
    print (alias: p) ----- Evaluate an expression.
    regs ----------------- Print contents of CPU registers.
    set ------------------ Changes the value of a variable.
    vars ----------------- Print package variables.
    whatis --------------- Prints type of an expression.

Listing and switching between threads and goroutines:
    goroutine (alias: gr) -- Shows or changes current goroutine
    goroutines (alias: grs)  List program goroutines.
    thread (alias: tr) ----- Switch to the specified thread.
    threads ---------------- Print out info for every traced thread.

Viewing the call stack and selecting frames:
    deferred --------- Executes command in the context of a deferred call.
    down ------------- Move the current frame down.
    frame ------------ Set the current frame, or execute command on a different frame.
    stack (alias: bt)  Print stack trace.
    up --------------- Move the current frame up.

Other commands:
    config --------------------- Changes configuration parameters.
    disassemble (alias: disass)  Disassembler.
    edit (alias: ed) ----------- Open where you are in $DELVE_EDITOR or $EDITOR
    exit (alias: quit | q) ----- Exit the debugger.
    funcs ---------------------- Print list of functions.
    help (alias: h) ------------ Prints the help message.
    libraries ------------------ List loaded dynamic libraries
    list (alias: ls | l) ------- Show source code.
    source --------------------- Executes a file containing a list of delve commands
    sources -------------------- Print list of source files.
    types ---------------------- Print list of types

Type help followed by a command for full documentation.
(dlv) r
Process restarted with PID 3469
(dlv) c
> main.main() ./if_assignment.go:7 (hits goroutine(1):1 total:1) (PC: 0x4b86a1)
     2:
     3: import "fmt"
     4:
     5: func main() {
     6:
=>   7:         if a := 5; a < 6 {
     8:                 fmt.Println("a is less than 6")
     9:         }
    10: }
(dlv) n
> main.main() ./if_assignment.go:8 (PC: 0x4b86ac)
     3: import "fmt"
     4:
     5: func main() {
     6:
     7:         if a := 5; a < 6 {
=>   8:                 fmt.Println("a is less than 6")
     9:         }
    10: }
(dlv) n
a is less than 6
> runtime.main() /usr/local/go/src/runtime/proc.go:213 (PC: 0x43b40f)
Warning: debugging optimized function
Values returned:

   208:
   209:         // Make racy client program work: if panicking on
   210:         // another goroutine at the same time as main returns,
   211:         // let the other goroutine finish printing the panic trace.
   212:         // Once it does, it will exit. See issues 3934 and 20018.
=> 213:         if atomic.Load(&runningPanicDefers) != 0 {
   214:                 // Running deferred functions should not take long.
   215:                 for c := 0; c < 1000; c++ {
   216:                         if atomic.Load(&runningPanicDefers) == 0 {
   217:                                 break
   218:                         }
(dlv) n
> runtime.main() /usr/local/go/src/runtime/proc.go:222 (PC: 0x43b444)
Warning: debugging optimized function
   217:                                 break
   218:                         }
   219:                         Gosched()
   220:                 }
   221:         }
=> 222:         if atomic.Load(&panicking) != 0 {
   223:                 gopark(nil, nil, waitReasonPanicWait, traceEvGoStop, 1)
   224:         }
   225:
   226:         exit(0)
   227:         for {
(dlv) n
> runtime.main() /usr/local/go/src/runtime/proc.go:226 (PC: 0x43b44e)
Warning: debugging optimized function
   221:         }
   222:         if atomic.Load(&panicking) != 0 {
   223:                 gopark(nil, nil, waitReasonPanicWait, traceEvGoStop, 1)
   224:         }
   225:
=> 226:         exit(0)
   227:         for {
   228:                 var x *int32
   229:                 *x = 0
   230:         }
   231: }
(dlv) n
Process has exited with status 0
(dlv) 
Process 3469 has exited with status 0
(dlv) quit
[root@pcentos if]# 
```

## 不适用调试器

如果你不想使用调试器，你可以按照下面的一些有用的方法来达到基本调试的目的：

    在合适的位置使用打印语句输出相关变量的值（print/println 和 fmt.Print/fmt.Println/fmt.Printf）。

    在 fmt.Printf 中使用下面的说明符来打印有关变量的相关信息：
        %+v 打印包括字段在内的实例的完整信息
        %#v 打印包括字段和限定类型名称在内的实例的完整信息
        %T 打印某个类型的完整说明

    使用 panic 语句（第 13.2 节）来获取栈跟踪信息（直到 panic 时所有被调用函数的列表）。

    使用关键字 defer 来跟踪代码执行过程（第 6.4 节）。
 