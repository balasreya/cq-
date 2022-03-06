# cq-
#include<stdio.h>
#include<stdlib.h>
#define max 10
int front=-1,rear=-1,cq[max];
void enqueue(int k)
{
    if((rear==max-1)&&(front=0))
    {
        printf("stack is full");
    }
    else
    {
        if(front==-1)
        {
            front=0;
            rear=0;
        }
        else if(rear==max-1)
        {
            rear=0;
        }
        else
        {
            rear++;
        }
        cq[rear]=k;
    }
}
void dequeue(int x)
{
    if(front==-1)
    {
     return -1;
    }
    else
    {
        x=cq[front];
        if(front==rear)
        {
            front=-1;
            rear=-1;
        }
        else if(front=max-1)
        {
            front=0;
        }
        else
        {
            front++;
        }
    }return x;
}
void display()
{
    int i;
    if(front<+rear)
    {
        for(i=front;i<=rear;i++)
        {
            printf("%d",cq[i]);
        }
    }
    else
    {
        for(i=front;i<=max-1;i++)
        {
            printf("%d",cq[i]);
        }
        for(i=0;i<=max-1;i++)
        {
            printf("%d",cq[i]);
        }
    }
}
void main()
{
    int choice=0,k,x;
    do{
    printf("operations on cq is:");
    printf("enter 1-enqueur\n");
    printf("enter 2-dequeue\n,3-display\n");
    printf("enter your choice");
    scanf("%d",&choice);
    switch(choice)
    {
        case 1:
               printf("enter the value k");
               scanf("%d",&k);
               enqueue(k);
               break;
        case 2:
               printf("enter the value of x");
               scanf("%d",&x);
               dequeue(x);
               break;
        case 3:
              display();
              break;
        default:
              printf("wrong choice");
              break;
    }
}while(choice!=4);
}
