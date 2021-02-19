my code on 19/02

#include<stdio.h> 
#include<string.h>
  int Mode;
struct Box
{ 
   int unique_id, length, breadth, height;
   char color[30];
   struct box*next;
   
}; 
struct*head;



void lastinsert ();  
void display();  
void search();
void count();
void Avg_Vol();
void Diff_Vol();
void Max_Height();
 void update_weight(); 
void delete_by_Id();
  
int main() 
{  
    
    printf("\nAvailable Operations\n");
    printf("\n1. Add_Boxes, , \n2. Display, \n3. Find_Box, \n4. Count, \n5. Avg_Vol, \n6. Min_Max_Vol_diff, \n7. Max_Height, \n8. Weight_Update, \n9. RemoveBoxBy_Id, \n10. EXIT");
    printf("\nEnter your choice\n");
    
     scanf("%d", &Mode);
     
     
      switch(Mode)
    {
             case 1:  
              lastinsert();  
            break;  
            case 2:  
                 display();          
            break;  
            case 3:  
                search();     
            break;  
            case 4:  
               count();       
            break;  
            case 5:  
             avg_vol();        
            break;  
            case 6:  
             diff_Vol();          
            break;  
            case 7: 
             max_height();
            break;  
            case 8:  
             update_weight();
            break;  
            case 9:  
               delete_by_Id();
            case 10;
            exit(0);  
            break;
        default:
            printf("Please enter valid choice..\n");
    }
    
    
    
    void lastinsert()  
{  
    struct node *ptr,*temp;  
    int item;     
    ptr = (struct node*)malloc(sizeof(struct node));      
    if(ptr == NULL)  
    {  
        printf("\nOVERFLOW");     
    }  
    else  
    {  
        printf("\nEnter value?\n");  
        scanf("%d",&item);  
        ptr->data = item;  
        if(head == NULL)  
        {  
            ptr -> next = NULL;  
            head = ptr;  
            printf("\nNode inserted");  
        }  
        else  
        {  
            temp = head;  
            while (temp -> next != NULL)  
            {  
                temp = temp -> next;  
            }  
            temp->next = ptr;  
            ptr->next = NULL;  
            printf("\nNode inserted");  
          
        }  
    }  
}  
     
    
    
    
    void display()  
{  
    struct node *ptr;  
    ptr = head;   
    if(ptr == NULL)  
    {  
        printf("Nothing to print");  
    }  
    else  
    {  
        printf("\nprinting values . . . . .\n");   
        while (ptr!=NULL)  
        {  
            printf("\n%d",ptr->data);  
            ptr = ptr -> next;  
        }  
    }  
}     



    void search()  
{  
    struct node *ptr;  
    int item,i=0,flag;  
    ptr = head;   
    if(ptr == NULL)  
    {  
        printf("\nEmpty List\n");  
    }  
    else  
    {   
        printf("\nEnter item which you want to search?\n");   
        scanf("%d",&item);  
        while (ptr!=NULL)  
        {  
            if(ptr->data == item)  
            {  
                printf("item found at location %d ",i+1);  
                flag=0;  
            }   
            else  
            {  
                flag=1;  
            }  
            i++;  
            ptr = ptr -> next;  
        }  
        if(flag==1)  
        {  
            printf("Item not found\n");  
        }  
    }     
          
}  
    
 
 
 void update_weight()  
{  
    int i,loc,item;   
    struct node *ptr, *temp;  
    ptr = (struct node *) malloc (sizeof(struct node));  
    if(ptr == NULL)  
    {  
        printf("\nOVERFLOW");  
    }  
    else  
    {  
        printf("\nEnter element value");  
        scanf("%d",&item);  
        ptr->data = item;  
        printf("\nEnter the location after which you want to insert ");  
        scanf("\n%d",&loc);  
        temp=head;  
        for(i=0;i<loc;i++)  
        {  
            temp = temp->next;  
            if(temp == NULL)  
            {  
                printf("\ncan't insert\n");  
                return;  
            }  
          
        }  
        ptr ->next = temp ->next;   
        temp ->next = ptr;   
        printf("\nNode inserted");  
    }  
}  
  
   printf ("unique_id = %d, length = %d, breadth = %d, height =%d\n, color = %s", p1.unique_id, p1.length, p1.breadth, p1.height, p1.color); 
  
   return 0; 
} 
