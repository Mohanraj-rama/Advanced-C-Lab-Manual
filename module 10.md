EXP NO:16 C PROGRAM TO SEARCH A GIVEN ELEMENT IN THE GIVEN LINKED LIST.
Aim:
To write a C program to search a given element in the given linked list.

Algorithm:
1.	Define the structure for a node in a linked list.
2.	Define the search function to find a specific character in the linked list.
3.	Initialize the head of the linked list as needed.
4.	Call the search function and perform other linked list operations as needed.
 
Program:
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

struct Node* create(int data) {
    struct Node* newnode = (struct Node*)malloc(sizeof(struct Node));
    newnode->data = data;
    newnode->next = NULL;
    return newnode;
}

int search(struct Node* head, int key) {
    struct Node* temp = head;
    while (temp != NULL) {
        if (temp->data == key)
            return 1;
        temp = temp->next;
    }
    return 0;
}

int main() {
    struct Node* head = create(10);
    head->next = create(20);
    head->next->next = create(30);

    int key = 20;

    if (search(head, key))
        printf("Element found");
    else
        printf("Element not found");

    return 0;
}

```

Output:

<img width="1140" height="975" alt="image" src="https://github.com/user-attachments/assets/79a9df1a-fa2a-4760-8929-8a4dc6009528" />


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
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    char data;
    struct Node *next;
};

void insert(struct Node **head, char data) {
    struct Node *newnode = (struct Node*)malloc(sizeof(struct Node));
    newnode->data = data;
    newnode->next = NULL;

    if (*head == NULL) {
        *head = newnode;
        return;
    }

    struct Node *temp = *head;
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newnode;
}

void display(struct Node *head) {
    while (head != NULL) {
        printf("%c ", head->data);
        head = head->next;
    }
}

int main() {
    struct Node *head = NULL;

    insert(&head, 'A');
    insert(&head, 'B');
    insert(&head, 'C');

    display(head);
    return 0;
}

```
Output:

<img width="1135" height="939" alt="image" src="https://github.com/user-attachments/assets/930a4c51-a73c-4212-9c8e-a7dd205758f3" />


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
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *prev;
    struct Node *next;
};

void traverse(struct Node *head) {
    struct Node *temp = head;
    while (temp != NULL) {
        printf("%d ", temp->data);
        temp = temp->next;
    }
}

struct Node* create(int data) {
    struct Node *newnode = (struct Node*)malloc(sizeof(struct Node));
    newnode->data = data;
    newnode->prev = NULL;
    newnode->next = NULL;
    return newnode;
}

int main() {
    struct Node *head = create(10);
    struct Node *node2 = create(20);
    struct Node *node3 = create(30);

    head->next = node2;
    node2->prev = head;
    node2->next = node3;
    node3->prev = node2;

    traverse(head);
    return 0;
}

```
Output:

<img width="1144" height="906" alt="image" src="https://github.com/user-attachments/assets/4e56475c-6391-4403-9d12-42ad1520a281" />


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
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *prev;
    struct Node *next;
};

void insertEnd(struct Node **head, int data) {
    struct Node *newNode = (struct Node*)malloc(sizeof(struct Node));
    newNode->data = data;
    newNode->prev = NULL;
    newNode->next = NULL;

    if (*head == NULL) {
        *head = newNode;
        return;
    }

    struct Node *temp = *head;
    while (temp->next != NULL)
        temp = temp->next;

    temp->next = newNode;
    newNode->prev = temp;
}

void traverse(struct Node *head) {
    while (head != NULL) {
        printf("%d ", head->data);
        head = head->next;
    }
}

int main() {
    struct Node *head = NULL;

    insertEnd(&head, 10);
    insertEnd(&head, 20);
    insertEnd(&head, 30);

    traverse(head);
    return 0;
}

```
Output:

<img width="1134" height="956" alt="image" src="https://github.com/user-attachments/assets/512e2ecc-9d26-4988-a789-f346bd76d56a" />


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
```
#include <stdio.h>
#include <stdlib.h>

struct Node {
    int data;
    struct Node *next;
};

void deleteElement(struct Node **head, int key) {
    if (*head == NULL) {
        printf("List is empty");
        return;
    }

    struct Node *temp = *head;

    if (temp->data == key) {
        *head = temp->next;
        free(temp);
        return;
    }

    struct Node *prev = NULL;
    while (temp != NULL && temp->data != key) {
        prev = temp;
        temp = temp->next;
    }

    if (temp == NULL) {
        printf("Element not found");
        return;
    }

    prev->next = temp->next;
    free(temp);
}

struct Node* create(int data) {
    struct Node* newnode = (struct Node*)malloc(sizeof(struct Node));
    newnode->data = data;
    newnode->next = NULL;
    return newnode;
}

void display(struct Node *head) {
    while (head != NULL) {
        printf("%d ", head->data);
        head = head->next;
    }
}

int main() {
    struct Node *head = create(10);
    head->next = create(20);
    head->next->next = create(30);

    deleteElement(&head, 20);
    display(head);

    return 0;
}

```
Output:

<img width="1149" height="901" alt="image" src="https://github.com/user-attachments/assets/66de9366-966b-496a-8d5c-65a4278dd8cf" />


Result:

Thus, the function that deletes a given element from a linked list is verified successfully.





