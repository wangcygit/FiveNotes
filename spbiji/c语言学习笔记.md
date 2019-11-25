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



4、c语言指针的本质

指针本质上就是指向内存的地址



