

EXP NO 26: C PROGRAM TO DISPLAY STACK ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display stack elements using linked list.

Algorithm:
1.	Define a structure Node with two members: data to store the integer value and next to point to the next node in the linked list.
2.	Declare a global variable head representing the starting node of the linked list.
3.	Define a function display to print the elements of the linked list.
4.	Declare a pointer p and initialize it with the head of the linked list.
5.	Use a while loop to traverse the linked list:
6.	Print the data of the current node.
7.	Move to the next node using the next pointer.
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    struct Node {
        int data;
        struct Node *next;
    };
    struct Node *head = NULL;
    void display() {
        struct Node *p = head;
        while (p != NULL) {
            printf("%d ", p->data);
            p = p->next;
        }
        printf("\n");
    }
    void insert(int value) {
        struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
        newNode->data = value;
        newNode->next = NULL;
        if (head == NULL)
            head = newNode;
        else {
            struct Node *temp = head;
            while (temp->next != NULL)
                temp = temp->next;
            temp->next = newNode;
        }
    }
    int main() {
        insert(10);
        insert(20);
        insert(30);
        printf("Linked List elements are: ");
        display();
        return 0;
    }

Output:

<img width="1418" height="1110" alt="image" src="https://github.com/user-attachments/assets/45c3aa52-0ae5-4dab-bdb3-143c1fab9a05" />


Result:
Thus, the program to display stack elements using linked list is verified successfully. 



EXP.NO 27: C PROGRAM TO POP AN ELEMENT FROM THE GIVEN STACK USING 
LINKED LIST.
Aim:
To write a C program to pop an element from the given stack using liked list.

Algorithm:
1.	Check for Empty Stack
2.	If head is equal to NULL, Print "Stack is empty."
3.	Else Proceed to the next step.
4.	Set head to point to the next node in the stack.
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    struct Node {
        char data[50];
        struct Node *next;
    };
    struct Node *head = NULL;
    void pop() {
           if (head == NULL) {
           printf("Stack is empty.\n");
        } 
        else {
            struct Node *temp = head;
            head = head->next;   
            free(temp);
            printf("Element popped successfully.\n");
        }
    }
    
    int main() {
            pop(); 
    
        return 0;
    }

Output:

<img width="1414" height="1102" alt="image" src="https://github.com/user-attachments/assets/197aa331-5f35-4e44-a945-95bdbbab30cc" />


Result:
Thus, the program to pop an element from the given stack using liked list is verified successfully.

 
EXP NO:28 C PROGRAM TO DISPLAY QUEUE ELEMENTS USING LINKED LIST.
Aim:
To write a C program to display queue elements using linked list.
Algorithm:
1.	Check if Queue is Empty
2.	Display Queue Elements
3.	Print the data of the current node pointed to by front
4.	Update front to point to the next node.
5.	End the display function.
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    struct Node {
        int data;
        struct Node *next;
    };
    struct Node *front = NULL;
    struct Node *rear = NULL;
    void display() {
        struct Node *temp = front;
        if (front == NULL) {
            printf("Queue is empty.\n");
            return;
        }
        printf("Queue elements are:\n");
        while (temp != NULL) {
            printf("%d ", temp->data);
            temp = temp->next;
        }
        printf("\n");
    }
    void enqueue(int value) {
        struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
        newNode->data = value;
        newNode->next = NULL;
        if (rear == NULL) {
            front = rear = newNode;
        } else {
            rear->next = newNode;
            rear = newNode;
        }
    }
    int main() {
        enqueue(10);
        enqueue(20);
        enqueue(30);
        display();  
    
        return 0;
    }

Output:

<img width="1367" height="1101" alt="image" src="https://github.com/user-attachments/assets/d993193f-a858-48bc-86a2-d3f6de637ede" />


Result:
Thus, the program to display queue elements using linked list is verified successfully.


 
EXP NO:29 C PROGRAM TO INSERT ELEMENTS IN QUEUE USING LINKED LIST

Aim:
To write a C program to insert elements in queue using linked list

Algorithm:
1.	Allocate Memory for New Node
2.	Set Data and Next Pointer
3.	Check if Queue is Empty
4.	Set both front and rear to point to the new node p.
5.	Set the next pointer of the current rear to point to the new node p.
6.	End of Enqueue Operation
 
Program:

    #include <stdio.h>
        #include <stdlib.h>
        struct Node {
            int data;
            struct Node *next;
        };
        struct Node *front = NULL;
        struct Node *rear = NULL;
        void enqueue(int value) {
            struct Node *p = (struct Node*)malloc(sizeof(struct Node));
            p->data = value;
            p->next = NULL;
            if (front == NULL) {
                front = rear = p;
            } else {
                rear->next = p;
                rear = p;
            }
            printf("%d inserted into the queue.\n", value);
        }
        void display() {
            struct Node *temp = front;
            if (front == NULL) {
                printf("Queue is empty.\n");
                return;
            }
            printf("Queue elements: ");
            while (temp != NULL) {
                printf("%d ", temp->data);
                temp = temp->next;
            }
            printf("\n");
        }
    
    int main() {
        enqueue(10);
        enqueue(20);
        enqueue(30);
        display();  
        return 0;
    }

Output:

<img width="1416" height="1053" alt="image" src="https://github.com/user-attachments/assets/dc30bca8-88ab-4b19-88db-a5a2ad187fc9" />

Result:
Thus, the program to insert elements in queue using linked list is verified successfully.



EXP NO:30 C FUNCTION TO FIND THE PEEK OF QUEUE USING LINKED LIST.


Aim:

The aim of this function is to retrieve the "peek" (the front element) of a queue implemented using a linked list

Algorithm:

1.	Check if the queue is empty:
o	If the queue is empty (i.e., the front pointer is NULL), return an error or a message indicating that the queue is empty.
2.	Access the front element:
o	If the queue is not empty, return the data stored in the front node of the linked list (i.e., the element at the head of the queue).

Program:

    #include <stdio.h>
    #include <stdlib.h>
    struct Node {
        int data;
        struct Node *next;
    };
    struct Node *front = NULL;
    struct Node *rear = NULL;
    int peek() {
        if (front == NULL) {
            printf("Queue is empty.\n");
            return -1;  
        }
        return front->data;
    }
    void enqueue(int value) {
        struct Node *p = (struct Node*)malloc(sizeof(struct Node));
        p->data = value;
        p->next = NULL;

    if (front == NULL)
        front = rear = p;
    else {
        rear->next = p;
        rear = p;
    }
    }
    
    int main() {
        enqueue(10);
        enqueue(20);
        enqueue(30);

    int frontValue = peek();  // should return 10
    if (frontValue != -1)
        printf("Front: %d\n", frontValue);

    return 0;
    }
    

Output:

<img width="1353" height="1098" alt="image" src="https://github.com/user-attachments/assets/43f85522-d71d-46e7-ac12-34373d199aad" />

Result:

Thus, the program to retrieve the "peek" (the front element) of a queue implemented using a linked list is verified successfully.


