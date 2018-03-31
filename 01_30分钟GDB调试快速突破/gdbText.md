#前言 gdb 调试开始上手
##1.开启core,采集程序崩溃的状态

    首先开启core崩溃状态采集,可以通过 ulimit -a 或者 ulimit -c 查看 core file size
如果是0表示没有开启. 可用命令 ulimit -c unlimited 做更改

    如何设置core文件名称,请自行搜索.
 
##2.简单接触 gdb, 开始调试r n p

    第一个演示代码 heoo.c