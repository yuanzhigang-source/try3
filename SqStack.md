# 顺序栈的实现

## 初始化栈

```c
#define MaxSize 10
typedef struct{
  ElemType data[MaxSize];
  int top;//栈顶指针
}SqStack;
void InitStack(SqStack &S){
    S.top=-1;
}
void testStack(){
    SqStack S;
    InitStack(S);
}
bool StackEmpty(SqStack S){
    if(S.top==-1)
        return true;//栈空
    else
        return false;
}
bool Push(SqStack &S,ElemType x){
    if(S.top==MaxSize-1)
      return false;
    S.top=S.top+1;
    S.data[S.top]=x;//新元素入栈
    return true;
}//栈满条件：top==MaxSize



//共享栈
#define MaxSize 10
typedef struce{
    ElemType data[MaxSiza];
    int top0;
    int top1;
}ShStack;
void InitStack(ShStack &S){
    S.top0=-1;
    S.top1=MaxSize;
}//栈满条件：top1=top0+1
```

