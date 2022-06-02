# 顺序表

## 顺序表的初始化和内存分配

```c
//静态分配
#include <stdio.h>
#define MaxSize 10
typedef struct{
    int data[MaxSize];//静态数组存放数据
    int length;
}SqList;
//初始化顺序表
void InitList(sqList,&L){
    for(int i=0;i<MaxSize;i++)
        L.data[i]=0;
    L.length=0;
}
int main(){
    SqList L;//声名一个顺序表
    InitList(L);
    return 0;
}


//动态分配
#define InitSize 10
typedef struct{
    ElemType *data;
    int MaxSize;
    int Length;
}SeqList;
//malloc的用法：L.data=(ElemType *)malloc(sizeof(ElemType)*InitSize);
void InitList(SeqList &L){
    //申请空间
    L.data=(int *)malloc(InitSize*sizeof(int));
    L.Length=0;
    L.MaxSize=InitSize;
}
void IncreaseSize(SeqList &L,int len){
    int *p=L.data;
    L.data=(int *)malloc((L.MaxSize+len)*sizeof(int));
    for(int i=0;i<L.Length;i++){
        L.data[i]=p[i];//复制数据到新区域
    }
    L.MaxSize=L.MaxSize+len;//最大长度增加len
    free(p)
}
int main(){
    SeqList L;
    InitList(L);
    IncreaseSize(L,5);
    return 0;
}
```

### 特点：

1. 随机访问
2. 存储密度高
3. 拓展容量不方便
4. 插入，删除元素不方便