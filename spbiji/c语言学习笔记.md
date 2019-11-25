# c语言学习笔记

1、求最大值的c语言小程序

```c
#include <stdio.h>

int main()
{
    int a,b;
    scanf("%d,%d",&a,&b);
    if(a>b){
        printf("最大值是：%d",a);
        return a;
    }else{
        printf("最大值是：%d",b);
        return b;
    }   
    return 0;
}
```





2、最小值的小程序

```c
#include <stdio.h>

int main()
{
    int a,b;
    scanf("%d,%d",&a,&b);
    if(a<b){
        printf("最小值是：%d",a);
        return a;
    }else{
        printf("最小值是：%d",b);
        return b;
    }
    return 0;
}
```





3、求平均值的小程序

```c
#include <stdio.h>

int main()
{
    int s,n;
    scanf("%d,%d",&s,&n);
    float v=s/n;
    printf("v=%f\n",v);
    return 0;
}
```



前面我们对于:

- c语言的基本用法
- makeFile文件的使用
- main函数的详解
- 标准输入输出流以及错误流管道

### 工具与原理

- 指针
- 数组
- 字符串
- 堆内存与栈内存的差异
- gdb内存调试工具





安装gdb工具：

```
sudo apt install gdb
gdb -v12
```

gdb可以单步调试，打断点，查看内存中变量。但是即使生成了可调试版本，还是需要源代码`.c`的

gcc -g main0.c -o main0_debug.out生成可调试版本。
gdb ./main0_debug.out



l 全称list：查看源代码

回车：继续执行上条指令(此时的上条指令为l)
break 行数：设置断点
start ：单步调试
p a 全称print：查看a在内存中的情况
n：执行到下一条语句

- `bt`：查看函数堆栈(可以看到main函数和change函数)
- `f 1`：切换到1号函数(栈顶的是我们当前所在函数)
- `q`：退出调试