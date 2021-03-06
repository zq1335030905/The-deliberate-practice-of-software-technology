## gdb 调试

使用 gdb 调试，编译器需要加入 -g 参数，如 `g++ -g xxx.c -o xxx`

启动 gdb 方法：

* gdb xxx  // xxx 为可执行文件
* gdb xxx core // gdb 同时调试一个运行程序和 core 文件
* gdb xxx ID  // 指定这个服务程序运行时的进程 ID

| 命令        | 解释   |
| --------   | :-----:  |
| l  | 显示源代码，并且可以看到对应的行号 |
| r     | 如果此前没有下过断点，则执行完整个程序；如果有断点，则程序暂停在第一个可用断点处 |
| c        |   继续执行被调试程序，直至下一个断点或程序结束 |  
| b <行号>  |    在代码行号处设置断点    | 
| b <函数名称>      | 在函数处设置断点 | 
| p <变量名称>       |   显示指定变量（临时变量或全局变量）的值。 |
| n          |    单条语句执行|
| s        | 执行下一条语句 |
| b <行号>    |    在代码行号处设置断点    |  
| bt     |查看函数的堆栈 | 
| info b |显示当前断点情况|
|delete breakpoints|删除所有断点|
| finish       |  退出函数 | 
|bt/where|当前运行的堆栈列表|
| q  |    结束调试    |  

## [应用 — gdb 分析和调试 coredump 文件](https://github.com/steveLauwh/The-deliberate-practice-of-software-technology/blob/master/Linux%20Shell/gdb%20%E5%88%86%E6%9E%90%E5%92%8C%E8%B0%83%E8%AF%95%20coredump%20%E6%96%87%E4%BB%B6.md)

core 又叫 coredump 文件，是指程序由于各种异常或者 bug 导致在运行过程中异常退出或者中止，并且在满足一定条件下会产生一个叫做 core 的文件。

coredump 文件含有当进程被终止时内存、CPU 寄存器和各种函数调用堆栈信息等。

## 参考

* [gdb 命令](http://man.linuxde.net/gdb)
* [详解 coredump](http://blog.csdn.net/tenfyguo/article/details/8159176/)
