## 栈在括号匹配中的应用：

### ()匹配[]匹配{}匹配，

ex:（（]））显然不适合，直接return。

```C
#define MaxSize 10;
typedef struct{
    char data[MaxSize];
    int top;
}SqStack;
void InitStack(SqStack &S)
//初始化栈
bool StackEmpty(SqStack S)
//判栈空
bool Push(SqStack &S,char x)
//新元素入栈
bool Pop(SqStack &S,char &x)
//栈顶元素出栈，用x返回
bool bracketCheck(char str[],int length){
    SqStack S;
    InitStack(S);//初始化栈
    for(int i=0;i<length;i++){
        if(str[i]=='('||str[i]=='['||str(i)=='{'){
            Push(S,str[i]);//扫描入栈
        }else{
            if (StackEmpty(S))
                return false;//匹配失败
            char topElem;
            Pop(S,topElem);//栈顶元素出栈
            if(str[i]==')'&&topElem!='(')
                return false;
            if(str[i]==']'&&topElem!='[')
                return false;
            if(str[i]=='}'&&topElem!='{')
                return false;
        }
    }
    return StackEmpty(S);//检索完全部后栈空表示检索完成
}  
```

