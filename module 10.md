EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:

     #include <stdio.h>
     #include <stdlib.h>
     struct Node {
     char data;
     struct Node* next;
     };
     struct Node* search(struct Node* head, char key) {
     struct Node* temp = head;
     while (temp != NULL) {
     if (temp->data == key) {
     return temp;  
    }
     temp = temp->next;
     }
     return NULL;
     }
     struct Node* createNode(char data) {
     struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
     newNode->data = data;
     newNode->next = NULL;
     return newNode;
     }
     int main() {
     struct Node* head = createNode('A');
     head->next = createNode('B');
     head->next->next = createNode('C');
     head->next->next->next = createNode('D');
     char key = 'C';
     struct Node* result = search(head, key);
     if (result != NULL) {
     printf("Character '%c' found in the list.\n", key);
     } else {
     printf("Character '%c' not found in the list.\n", key);
     }
     return 0;
     }

Output:

<img width="889" height="531" alt="image" src="https://github.com/user-attachments/assets/6595d777-b2af-4585-b77a-3d70d1572edc" />

Result:
Thus, the program to search a given element in the given linked list is verified successfully.


 
EXP NO:17  PROGRAM TO INSERT A NODE IN A LINKED LIST.
Aim:
To write a C program to insert a node in a linked list.
Algorithm:
1.	Define the structure for a node in a linked list
2.	Define the insert function to insert a new node with character data at the end of the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the insert function and perform other linked list operations as needed.
 
Program:

     #include <stdio.h>
     #include <stdlib.h>
     struct Node {
     char data;
     struct Node* next;
     };
     void insert(struct Node** head, char value) {
     struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
     newNode->data = value;
     newNode->next = NULL;
     if (*head == NULL) {
     *head = newNode;
     } else {
     struct Node* temp = *head;
     while (temp->next != NULL) {
     temp = temp->next;
     }
     temp->next = newNode; 
    }
     }
     void display(struct Node* head) {
     struct Node* temp = head;
     while (temp != NULL) {
     printf("%c -> ", temp->data);
     temp = temp->next;
      }
     printf("NULL\n");
     }
     int main() {
     struct Node* head = NULL;
     insert(&head, 'A');
     insert(&head, 'B');
     insert(&head, 'C');
     insert(&head, 'D');
     printf("Linked List: ");
     display(head);
     return 0;
     }

Output:

<img width="915" height="552" alt="image" src="https://github.com/user-attachments/assets/d52edc25-a06b-49ea-99ea-65d075dd78aa" />



Result:
Thus, the program to insert a node in a linked list is verified successfully.


 
EXP NO:18 C PROGRAM TO TRAVERSE A DOUBLY LINKED LIST
Aim:
To write a C program to traverse a doubly linked list.

Algorithm:
1.	Initialize a temporary pointer (temp) to the head of the list.
2.	Use a while loop to traverse the list until the end (temp == NULL) is reached.
3.	Inside the loop, print the data of the current node.
4.	Move to the next node by updating the temp pointer to point to the next node (temp = temp->next).
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    struct Node {
    char data;
    struct Node* next;
    };
     void display(struct Node* head) {
    struct Node* temp = head;
    while (temp != NULL) {
    printf("%c -> ", temp->data);
    temp = temp->next;
    }
    printf("NULL\n");
    }
    void insert(struct Node** head, char value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    if (*head == NULL) {
    *head = newNode;
    } else {
    struct Node* temp = *head;
    while (temp->next != NULL) {
    temp = temp->next;
    }
    temp->next = newNode;
    }
    }
    int main() {
    struct Node* head = NULL;
    insert(&head, 'A');
    insert(&head, 'B');
    insert(&head, 'C');
    printf("Linked List: ");
    display(head);
    return 0;
    }

Output:

<img width="944" height="604" alt="image" src="https://github.com/user-attachments/assets/3fb2efbd-c1eb-4a95-a37d-c4c082071ba8" />


Result:
Thus, the program to traverse a doubly linked list is verified successfully. 



EXP NO:19 C PROGRAM TO INSERT AN ELEMENT IN DOUBLY LINKED LIST
Aim:
To write a C program to insert an element in doubly linked list

Algorithm:
1.	Create a new node (newNode) and allocate memory for it.
2.	Set the data of the new node to the provided value.
3.	If the list is empty, set the new node as the head.
4.	If the list is not empty, traverse the list to find the last node.
5.	Set the new node's prev pointer to the last node and update the last node's next pointer to the new node.
 
Program:

    #include <stdio.h>
    #include <stdlib.h>
    struct Node {
    int data;
    struct Node* next;
    struct Node* prev;
    };
    void insertEnd(struct Node** head, int value) {
    struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = value;
    newNode->next = NULL;
    newNode->prev = NULL;
    if (*head == NULL) {
    *head = newNode;
    return;
    }
    struct Node* temp = *head;
    while (temp->next != NULL) {
    temp = temp->next;
    }
    temp->next = newNode;
    newNode->prev = temp;
    }
    void display(struct Node* head) 
    {
     struct Node* temp = head;
    while (temp != NULL) {
    printf("%d <-> ", temp->data);
    temp = temp->next;
    }
    printf("NULL\n");
    }
    int main() {
    struct Node* head = NULL;
    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);
    printf("Doubly Linked List: ");
    display(head);
    return 0;
    }

Output:

<img width="912" height="607" alt="image" src="https://github.com/user-attachments/assets/7b17f891-27d5-401a-9ddd-a353417e0990" />


Result:
Thus, the program to insert an element in doubly linked list is verified successfully.




EXP NO:20 C FUNCTION TO DELETE A GIVEN ELEMENT IN THE GIVEN LINKED LIST




Aim:
To write a C function that deletes a given element from a linked list.

Algorithm:
1.	Check if the Linked List is Empty:
o	If the head of the linked list is NULL, print a message indicating the list is empty and exit the function.
2.	Traverse the Linked List:
o	Start from the head node and iterate through the list to find the node that contains the given element (data).
3.	Handle Deletion of the First Node:
o	If the element to be deleted is found in the head node:
	Update the head of the linked list to point to the next node (i.e., head = head->next).
	Free the memory allocated to the node to be deleted.
	Exit the function.
4.	Traverse and Delete from the Middle or End:
o	If the element is not in the head node, continue traversing the list by checking each node’s next pointer.
o	When the node with the element is found, update the previous node’s next pointer to point to the next node of the node to be deleted (prev->next = current->next).
o	Free the memory allocated to the node to be deleted.
5.	Handle the Case when the Element is Not Found:
o	If the element is not found in any node, print a message indicating the element is not present in the list.
6.	End the Function.


Program:

     #include <stdio.h>
     #include <stdlib.h>
     struct Node {
     int data;
       struct Node* next;
     };
     void deleteNode(struct Node** head, int key) {
        if (*head == NULL) {
            printf("List is empty\n");
            return;
        }
        struct Node* temp = *head;
        struct Node* prev = NULL;
        if (temp != NULL && temp->data == key) {
            *head = temp->next; 
            free(temp);         
            printf("Element %d deleted from the list\n", key);
            return;
        }
           while (temp != NULL && temp->data != key) {
            prev = temp;
            temp = temp->next;
        }
        if (temp == NULL) {
            printf("Element %d not found in the list\n", key);
            return;
        }
        prev->next = temp->next;
        free(temp);
        printf("Element %d deleted from the list\n", key);
     }
     void insert(struct Node** head, int data) {
        struct Node* newNode = (struct Node*)malloc(sizeof(struct Node));
        newNode->data = data;
        newNode->next = NULL;
     if (*head == NULL) {
        *head = newNode;
        return;
     }
     struct Node* temp = *head;
     while (temp->next != NULL) {
        temp = temp->next;
     }
     temp->next = newNode;
     }
     void display(struct Node* head) {
        while (head != NULL) {
            printf("%d -> ", head->data);
            head = head->next;
        }
        printf("NULL\n");
     }
     int main() {
        struct Node* head = NULL;
         insert(&head, 10);
     insert(&head, 20);
     insert(&head, 30);
     insert(&head, 40);
     printf("Initial List: ");
     display(head);
     deleteNode(&head, 10);
     display(head);
     deleteNode(&head, 30); 
    display(head);
     deleteNode(&head, 50); 
    display(head);
     return 0;
     }

Output:

<img width="842" height="486" alt="image" src="https://github.com/user-attachments/assets/491083fa-3c06-4639-8f0b-1bf0a8420d7c" />


Result:
Thus, the function that deletes a given element from a linked list is verified successfully.





