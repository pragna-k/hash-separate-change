# hash-separate-change
#include<stdio.h>
#include<stdlib.h>
struct hashtable
{
        int data;
        struct hashtable *next;
};
typedef struct hashtable node;
int hash(int x)
{
        return x/10;
}
void insert(node *t[10],int x)
{
        int i=hash(x);
        node *p;
        p=(node *)malloc(sizeof(node));
        p->data=x;
        p->next=NULL;
        if(t[i]->next==NULL)
        {
                t[i]->next=p;
        }
        else
        {
                p->next=t[i]->next;
                t[i]->next=p;
        }
}
void display(node *t[10])
{
        node *temp;
        int i;
        for(i=0;i<10;i++)
        {
                temp=t[i]->next;
                printf("\n|%d|",i);
                while(temp!=NULL)
                {
                        printf("%d->",temp->data);
                        temp=temp->next;
                }
                printf("NULL\n");
        }
}
void search(node *t[10],int x)
{
        int i=hash(x);
        int flag=0;
        node *temp=t[i]->next;
        while(temp!=NULL)
        {
                if(temp->data==x)
                {
                        flag=1;
                        break;
                }
 else
                {
                        temp=temp->next;
                }
        }
        if(flag==1)
        {
                if("ele %d is found",x);
        }
        else
        {
                printf("ele %d is not found",x);
        }
}
void delete(node *t[10],int x)
{
        int flag=0,i;
        i=hash(x);
        node *temp=t[i]->next,*temp1=t[i];
        while(temp!=NULL)
        {
                if(temp->data==x)
                {
                        flag=1;
                        break;
                }
                else
                {
                        temp1=temp;
                        temp=temp->next;
                }
        }
        if(flag==1)
        {
                temp1->next=temp->next;
                free(temp);
        }
        else
        {
                printf("ele %d is not found",x);
                }
}
int main ()
{
        node *t[10];
        int i,ch,x;
        for(i=0;i<10;i++)
        {
                t[i]=(node*)malloc(sizeof(node));
                t[i]->next=NULL;
        }
        while(1)
        {
                printf("1:insert\n 2:display\n 3:search\n 4:delete\n 5:exit\n");
                printf("enter choice");
                scanf("%d",&ch);
                switch(ch)
                {
                        case 1: printf("enter ele to be inserted");
                                scanf("%d",&x);
                                insert(t,x);
                                break;
                        case 2: printf("ele in hashtable are:\n");
                                display(t);
                                break;
                        case 3: printf("enter ele to be searched");
                                scanf("%d",&x);
                                search(t,x);
                                break;
                        case 4: printf("enter ele to be delete");
                                 scanf("%d",&x);
                                delete(t,x);
                                break;
                        case 5: exit(0);
                                break;
                }
        }
}
1:insert
 2:display
 3:search
 4:delete
 5:exit
enter choice1
enter ele to be inserted45
1:insert
 2:display
 3:search
 4:delete
 5:exit
enter choice1
enter ele to be inserted25
1:insert
 2:display
 3:search
 4:delete
 5:exit
enter choice2
ele in hashtable are:

|0|NULL

|1|NULL

|2|25->NULL

|3|NULL

|4|45->NULL

|5|NULL

|6|NULL

|7|NULL

|8|NULL

|9|NULL
1:insert
 2:display
 3:search
 4:delete
 5:exit
enter choice3
enter ele to be searched45
1:insert
 2:display
 3:search
 4:delete
 5:exit
enter choice4
enter ele to be delete3
ele 3 is not found1:insert
 2:display
 3:search
 4:delete
 5:exit
enter choice5
