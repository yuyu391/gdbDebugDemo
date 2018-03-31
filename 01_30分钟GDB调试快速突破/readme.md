#前言 gdb 调试开始上手
##1.开启core,采集程序崩溃的状态

    首先开启core崩溃状态采集,可以通过 ulimit -a 或者 ulimit -c 查看 core file size
如果是0表示没有开启. 可用命令 ulimit -c unlimited 做更改

    如何设置core文件名称,请自行搜索.
 
##2.简单接触 gdb, 开始调试r n p

    第一个演示代码 heoo.c
    
    ```c
    #include <stdio.h>
    
    int g_var = 0;
    
    static int _add(int a, int b) {
        printf("_add called, a:%d, b:%d\n", a, b);
        return a+b;
    }
    
    int main(void) {
        int n = 1;
        
        printf("one n=%d, g_var=%d\n", n, g_var);
        ++n;
        --n;
        
        g_var += 20;
        g_var -= 20;
        n = _add(1, g_var);
        printf("two n=%d\n, g_var=%d\n", n, g_var);
        
        return 0;
    }
    ```