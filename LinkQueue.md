```c
typedef struct LinkNode{
    ElemType data;
    struct LinkNode *next;
}LinkNode;
typedef struct{
    LinkNode *front,*rear;
}LinkQueue;
//带头节点
//初始化
void InitQueue(LinkQueue &Q){
    //两个指针都指向头结点
    Q.front=Q.rear=(LinkNode*)malloc(sizeof(LinkNode));
    Q.front->next=null;
}
void testLinkQueue(){
    LinkQueue Q;//声明一个队列
    InitQueue(Q);//初始化
}
//插入操作
void EnQueue(LinkQueue &Q,ElemType x){
    LinkNode *s=(Linknode *)malloc(sizeof(LinkNode));
    s->data=x;
    s->next=Null;
    Q.rear->next=s;//新节点插到rear之后
    Q.rear=s;//修改表尾指针
}
//出队操作
bool DeQueue(LinkQueue &Q,ElemType &x){
    if(Q.front==Q.rear)
        return false;
    LinkNode *p=Q.front->next;
    x=p->data;
    Q.front->next=p->next;
    if(Q.rear==p)
        Q.rear=Q.front;
    free(p);
    return true;
}


//不带头结点
void InitLinkQueue(LinkQueue &Q){
    //初始化时，两个指针都在null上
    Q.front=null;
    Q.rear=null;
}
//判断队列是否为空
bool IsEmpty(LinkQueue Q){
    if(Q.front==null)
        return true;
    else
        return false;
}
//插入
void EnQueue(LinkQueue &Q,ElemType x){
    LinkNode *s=(Linknode *)malloc(sizeof(LinkNode));
    s->data=x;
    s->next=Null;
    if(Q.front==Null){
        Q.front=s;//空队列插入元素
        Q.rear=s;
    }else{
        Q.rear->next=s;
        Q.rear=s;
    }
}
//出队操作
bool DeQueue(LinkQueue &Q,ElemType &x){
    if(Q.front==Q.rear)
        return false;//空对队
    LinkNode *p=Q.front;//指向此次出队的结点
    x=p->data;
    Q.front=p->next;
    if(Q.rear==p){
        Q.rear=Null;
        Q.front=Null;
}free(p);
    return true;
}
```

